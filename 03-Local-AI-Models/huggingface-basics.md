# 🤗 HuggingFace Local Models Basics

Running models locally is great for privacy and avoiding API costs. Here is a basic setup for running a smaller HuggingFace model on your local machine using Python.

## 1. Setup & Installation
First, install the required PyTorch and Transformers libraries:

```bash
pip install transformers torch



from transformers import pipeline

# Load the text generation pipeline
# Note: This will download the model to your local machine on the first run
generator = pipeline('text-generation', model='gpt2')

# Generate text
prompt = "Artificial Intelligence is transforming software engineering by"
result = generator(prompt, max_length=50, num_return_sequences=1)

print(result[0]['generated_text'])
