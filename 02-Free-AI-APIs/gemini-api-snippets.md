# ✨ Google Gemini API Snippets

A quick reference for integrating the Google Gemini API into your applications.

## 1. Basic Text Generation (Python)
Make sure to install the SDK: `pip install google-generativeai`

```python
import google.generativeai as genai
import os

# Configure the API key
genai.configure(api_key=os.environ["GEMINI_API_KEY"])

# Initialize the model
model = genai.GenerativeModel('gemini-1.5-flash')

# Generate content
response = model.generate_content("Explain the concept of Retrieval-Augmented Generation (RAG).")
print(response.text)
