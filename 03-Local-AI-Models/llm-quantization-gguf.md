# 🗜️ LLM Quantization & GGUF

Large Language Models (LLMs) are often too massive to run on standard consumer hardware. Quantization reduces the precision of the model's weights (e.g., from 16-bit to 4-bit), drastically lowering RAM and VRAM requirements while maintaining near-original accuracy.

## 1. The GGUF Format
GGUF is the standard file format for quantized local models, specifically designed for fast CPU and Apple Metal/GPU inference.

## 2. Running Quantized Models with Python
You can efficiently run GGUF models in Python using `llama-cpp-python`.

First, install the library:
```bash
pip install llama-cpp-python
```

Here is a basic script to load and query a 4-bit quantized model:

```python
from llama_cpp import Llama

# Load a 4-bit quantized model (You need to download the .gguf file first)
# Example: Llama-3-8B-Instruct.Q4_K_M.gguf
llm = Llama(
    model_path="./models/Llama-3-8B-Instruct.Q4_K_M.gguf",
    n_ctx=2048,      # Context window size
    n_gpu_layers=-1  # Offload all layers to GPU (if available)
)

# Generate text
output = llm(
    "Explain the concept of neural networks in one simple sentence.",
    max_tokens=50,
    stop=["Q:", "\n"]
)

print("AI Response:", output['choices'][0]['text'].strip())
```
