# 🦙 Ollama Local Setup Guide

Ollama is the easiest way to get up and running with large language models (like Llama 3, Mistral, and Gemma) locally on your own machine.

## 1. Installation
Download and install Ollama from [ollama.com](https://ollama.com/).

## 2. Running Your First Model
Open your terminal or command prompt and run:
```bash
ollama run llama3
```
This command will automatically download the Llama 3 model weights (if not already downloaded) and start an interactive chat session right in your terminal.

## 3. Using the Local API
Ollama provides a local API on port `11434`. You can test it with `curl`:
```bash
curl -X POST http://localhost:11434/api/generate -d '{
  "model": "llama3",
  "prompt": "Why is the sky blue?",
  "stream": false
}'
```
