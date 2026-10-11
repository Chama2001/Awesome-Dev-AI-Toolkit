# 🚀 Microsoft Copilot Studio Agents

Microsoft Copilot Studio allows developers to create custom AI agents using a low-code graphical interface, backed by powerful LLMs.

## 1. Core Components of a Copilot Agent
When designing an agent in Copilot Studio, focus on these three pillars:
1. **Topics:** The distinct conversational paths (e.g., "Reset Password", "Order Status"). Use the generative AI capabilities to dynamically handle unscripted variations of these topics.
2. **Knowledge:** Upload your enterprise documents (PDFs, Word docs) or link public websites. The agent will use this as a grounding dataset for Retrieval-Augmented Generation (RAG).
3. **Actions:** Connect your agent to external APIs (like a MySQL database or external REST APIs) via Power Automate flows to perform real-world tasks.
