# 🧠 RAG (Retrieval-Augmented Generation) Basics

Retrieval-Augmented Generation (RAG) improves Large Language Models (LLMs) by providing them with external, domain-specific knowledge before generating a response. 

## 1. The Core Concept
A standard RAG pipeline consists of three main steps:
1. **Retrieve:** Search a database (usually a Vector DB or SQLite) for documents relevant to the user's query.
2. **Augment:** Combine the retrieved documents with the original prompt to give the LLM context.
3. **Generate:** The LLM generates a factual answer based on the augmented prompt.

## 2. Generating Embeddings with Sentence-BERT
When building custom AI assistants, local embedding models are highly efficient. Here is how to generate text embeddings using Sentence-BERT:

```bash
pip install sentence-transformers
```

```python
from sentence_transformers import SentenceTransformer

# Load a pre-trained Sentence-BERT model
model = SentenceTransformer('all-MiniLM-L6-v2')

# Documents to be indexed in your database
documents = [
    "Next.js 15 introduces the new React Compiler.",
    "Tailwind CSS v4 brings a new high-performance engine."
]

# Generate embeddings (vectors)
embeddings = model.encode(documents)

print(f"Generated {len(embeddings)} embeddings.")
print(f"Embedding dimension: {len(embeddings[0])}")
```
