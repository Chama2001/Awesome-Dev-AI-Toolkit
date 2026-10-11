# 🤖 Autonomous AI Agents (Agentic Workflows)

Instead of just answering questions, AI Agents can use tools, run code, and execute tasks autonomously. Here is a basic example of building an agent using LangChain and Google Gemini.

## 1. Install Dependencies
```bash
pip install langchain langchain-google-genai
```

## 2. Simple LangChain Agent
This agent uses the ReAct (Reasoning and Acting) framework to think step-by-step and use a tool to find the answer.

```python
from langchain_google_genai import ChatGoogleGenerativeAI
from langchain.agents import initialize_agent, AgentType
from langchain.tools import Tool
import os

# 1. Initialize the LLM (Gemini)
llm = ChatGoogleGenerativeAI(model="gemini-1.5-pro", google_api_key=os.environ["GEMINI_API_KEY"])

# 2. Define a custom tool (e.g., a simple calculator)
def simple_calculator(query):
    try:
        return str(eval(query))
    except Exception as e:
        return str(e)

tools = [
    Tool(
        name="Calculator",
        func=simple_calculator,
        description="Useful for when you need to calculate mathematical expressions."
    )
]

# 3. Initialize the Agent
agent = initialize_agent(
    tools, 
    llm, 
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION, 
    verbose=True
)

# 4. Run the Agent
response = agent.run("What is 15 multiplied by 4 and then divided by 2?")
print("Final Answer:", response)
```
