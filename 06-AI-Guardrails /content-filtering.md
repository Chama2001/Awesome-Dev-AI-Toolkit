# 🛡️ AI Content Filtering & Guardrails

When building AI applications, it is crucial to ensure that the model does not generate harmful, offensive, or inappropriate content. 

## 1. Gemini API Safety Settings
Google's Gemini API allows you to configure safety settings to block unsafe content across various categories.

```python
import google.generativeai as genai
from google.generativeai.types import HarmCategory, HarmBlockThreshold
import os

genai.configure(api_key=os.environ["GEMINI_API_KEY"])

# Define strict safety settings
safety_settings = {
    HarmCategory.HARM_CATEGORY_HARASSMENT: HarmBlockThreshold.BLOCK_LOW_AND_ABOVE,
    HarmCategory.HARM_CATEGORY_HATE_SPEECH: HarmBlockThreshold.BLOCK_LOW_AND_ABOVE,
    HarmCategory.HARM_CATEGORY_SEXUALLY_EXPLICIT: HarmBlockThreshold.BLOCK_LOW_AND_ABOVE,
    HarmCategory.HARM_CATEGORY_DANGEROUS_CONTENT: HarmBlockThreshold.BLOCK_LOW_AND_ABOVE,
}

model = genai.GenerativeModel('gemini-1.5-flash')

# Generate content with guardrails applied
response = model.generate_content(
    "Your prompt goes here",
    safety_settings=safety_settings
)

print(response.text)
```
