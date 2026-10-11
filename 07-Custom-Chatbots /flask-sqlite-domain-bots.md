# 🤖 Flask & SQLite Domain Bots

Building a custom domain-specific chatbot requires a lightweight backend and a reliable database to store chat histories or domain knowledge. Python's Flask paired with SQLite is an excellent, highly efficient architecture for this.

## 1. Project Setup
First, install the necessary dependencies:
```bash
pip install Flask 
```

## 2. Flask Backend with SQLite Integration
Here is a basic structure for a chatbot API endpoint that logs conversations into an SQLite database. This architecture pairs perfectly with a Next.js frontend and local embedding models (like Sentence-BERT).

```python
from flask import Flask, request, jsonify
import sqlite3

app = Flask(__name__)

# Initialize SQLite Database
def init_db():
    conn = sqlite3.connect('chatbot.db')
    c = conn.cursor()
    c.execute('''CREATE TABLE IF NOT EXISTS chat_history
                 (id INTEGER PRIMARY KEY AUTOINCREMENT, user_message TEXT, bot_response TEXT)''')
    conn.commit()
    conn.close()

@app.route('/chat', methods=['POST'])
def chat():
    data = request.json
    user_message = data.get("message", "")
    
    # Here you would normally pass the message to your LLM or RAG pipeline
    bot_response = f"This is a simulated AI response to: {user_message}"
    
    # Save to SQLite
    conn = sqlite3.connect('chatbot.db')
    c = conn.cursor()
    c.execute("INSERT INTO chat_history (user_message, bot_response) VALUES (?, ?)", 
              (user_message, bot_response))
    conn.commit()
    conn.close()
    
    return jsonify({"response": bot_response})

if __name__ == '__main__':
    init_db()
    app.run(port=5000, debug=True)
```
