# Guide to Using Ollama

A practical guide for running Ollama locally, accessing it over the network, using Cloud models, and integrating via API.

---

## 1. Installation

```bash
# Linux / macOS
curl -fsSL https://ollama.com/install.sh | sh
```

```bash
# After installation, start the service
ollama serve
```

Or just run any command (`ollama run`, `ollama pull`) and it will start automatically.

---

## 2. Local Usage (Default)

Ollama runs on `http://localhost:11434`

```bash
# Chat with a model
ollama run llama3.2

# Pull a model
ollama pull qwen2.5:7b
```

---

## 3. Access Ollama from Other Devices (Internal Network)

By default, Ollama only listens on `localhost` (127.0.0.1).

### Step 1: Set OLLAMA_HOST

**Temporary (current terminal):**
```bash
export OLLAMA_HOST=0.0.0.0:11434
ollama serve
```

**Permanent (recommended for servers):**

- **Linux systemd:**
  ```bash
  sudo systemctl edit ollama.service
  ```
  Add under `[Service]`:
  ```
  Environment="OLLAMA_HOST=0.0.0.0:11434"
  ```
  Then:
  ```bash
  sudo systemctl daemon-reload
  sudo systemctl restart ollama
  ```

- **macOS:**
  ```bash
  launchctl setenv OLLAMA_HOST "0.0.0.0:11434"
  ```

Now you can access it from other devices using your machine’s **internal IP**:

```
http://192.168.1.XXX:11434
```

> **Security Note**: Only use on trusted networks. Ollama has no built-in authentication.

---

## 4. Using Cloud Models (Ollama Cloud)

Some large models are available as **cloud-hosted** versions.

1. Login to your Ollama account:
   ```bash
   ollama signin
   ```

2. Run a cloud model:
   ```bash
   ollama run gpt-oss:120b-cloud
   # or any other -cloud model
   ```

---

## 5. Using Ollama via API

### Local API (No Key Needed)

```bash
curl http://localhost:11434/api/chat -d '{
  "model": "llama3.2",
  "messages": [
    { "role": "user", "content": "Hello!" }
  ],
  "stream": false
}'
```

Using internal IP from another device:
```bash
curl http://192.168.1.105:11434/api/generate -d '{"model": "qwen2.5:7b", "prompt": "Why is the sky blue?"}'
```

### Cloud API (Requires API Key)

1. Go to [https://ollama.com/settings/keys](https://ollama.com/settings/keys) and create an API key.

2. Use it:

```bash
curl https://ollama.com/api/chat \
  -H "Authorization: Bearer YOUR_API_KEY_HERE" \
  -d '{
    "model": "gpt-oss:120b-cloud",
    "messages": [{"role": "user", "content": "Hello"}]
  }'
```

Or set environment variable:
```bash
export OLLAMA_API_KEY=your_key_here
```

---

## Useful Commands

```bash
ollama list              # List downloaded models
ollama ps                # Show running models
ollama stop llama3.2     # Stop a running model
ollama rm modelname      # Remove model
ollama serve             # Start server manually
```

---

**Next Steps**

- Connect Open WebUI or other frontends to your Ollama instance
- Use with LangChain, LlamaIndex, or custom applications

For more details, visit the [official Ollama Documentation](https://docs.ollama.com).

---

**Happy local inferencing!** 🦙
```

You can copy the entire content above and save it as `guide_to_use_ollama.md` in your `docs/` folder. Let me know if you want any section expanded or modified!
