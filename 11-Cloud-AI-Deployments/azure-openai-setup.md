# ☁️ Azure OpenAI Deployment Basics

Deploying AI models on the cloud is essential for scalable, enterprise-grade applications. Microsoft Azure provides a highly secure environment for deploying and managing AI models.

## 1. Setup Instructions
First, ensure you have an active Azure subscription and have deployed an OpenAI model via the Azure portal. 

Install the required library:
```bash
pip install openai
```

## 2. Connecting to Azure OpenAI (Python)
Here is a standard template to connect your Python backend (like Flask or FastAPI) to an Azure OpenAI deployment:

```python
import os
from openai import AzureOpenAI

# Initialize the Azure OpenAI client
client = AzureOpenAI(
    azure_endpoint=os.getenv("AZURE_OPENAI_ENDPOINT"), 
    api_key=os.getenv("AZURE_OPENAI_API_KEY"),  
    api_version="2024-02-01"
)

# Make a request to your deployed model
response = client.chat.completions.create(
    model="your-deployment-name", # Replace with your actual Azure deployment name
    messages=[
        {"role": "system", "content": "You are a helpful AI assistant."},
        {"role": "user", "content": "What are the main benefits of cloud AI deployments?"}
    ]
)

print(response.choices[0].message.content)
```
