# 🦙 Local LLM Guide

**A comprehensive guide and template collection for running local LLMs.**

## 📖 Introduction
This repository provides practical, copy-pasteable guides for deploying Large Language Models locally. Whether you are prototyping on a laptop, running edge deployments, or serving high-concurrency production workloads, you'll find the right tools, configurations, and best practices here.

## 📚 Full Guide

| Tool | Best For | Hardware Focus | Model Format |
| :--- | :--- | :--- | :--- |
| **[Ollama](docs/ollama.md)** | Local Dev / Prototyping | Apple Silicon / Consumer GPU | GGUF |
| **[llama.cpp](docs/llama-cpp.md)** | Edge / CPU / Custom Apps | CPU / Any GPU | GGUF |
| **[vLLM](docs/vllm.md)** | Production / High Scale | NVIDIA Multi-GPU | HuggingFace |

## ✨ What's Inside
- **Step-by-step setups:** From zero to running your first chat or API endpoint.
- **Hardware cheat sheets:** VRAM calculations and quantization guides (Q4, Q8, FP16).
- **API integration:** Examples for OpenAI-compatible endpoints and Python/JS clients.
- **Performance tuning:** Context window management, batching, and memory optimization.

## 🤝 Contributing
Contributions are welcome! Please open an issue or submit a pull request if you'd like to improve these guides, add new inference engines, or fix typos.
