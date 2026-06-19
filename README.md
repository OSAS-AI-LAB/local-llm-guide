# 🦙 Local LLM Guide

**A comprehensive guide and template collection for running local LLMs.**

Covers **llama.cpp**, **vLLM**, **Ollama**, and more — from quick local setup to production serving.

---

## 🚀 Quick Start

```bash
# Ollama (easiest)
curl -fsSL https://ollama.com/install.sh | sh
ollama pull qwen2.5:7b
ollama run qwen2.5:7b
```

```bash
# llama.cpp (high performance)
git clone https://github.com/ggerganov/llama.cpp
cd llama.cpp && make LLAMA_CUDA=1
./llama-server -m models/llama-3.1-8b.Q5_K_M.gguf --port 8080
```

See `docs/` for detailed guides.

---

## ✨ What's Inside

- **Setup guides**: Ollama, llama.cpp, vLLM
- **Hardware recommendations** & quantization
- **Templates**: Docker, systemd, API servers, Modelfiles
- **Advanced**: RAG, function calling, multi-GPU, Open WebUI
- **Scripts**: Hardware detection, benchmarks, deployment helpers

---

## 📁 Structure

- `docs/` — Full documentation (setup, tools, best practices)
- `templates/` — Ready-to-use configs and scripts
- `scripts/` — Automation helpers

---

## 📖 Next Steps

Explore the [`docs/`](docs/) folder for in-depth guides.

**Star the repo** if this helps you run local models! 

Contributions welcome — PRs for new tools, hardware reports, or templates.
```

This is intentionally short and to-the-point, with the bulk of content in `docs/` as requested. It highlights the main tools you mentioned. You can copy-paste directly into `README.md`.
