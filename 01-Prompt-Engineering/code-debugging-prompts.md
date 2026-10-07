# 🐛 Code Debugging Prompts

When you encounter errors in your code, providing the right context to an AI (like Gemini, ChatGPT, or Claude) is crucial. Use these templates to get accurate fixes quickly.

## 1. General Error Debugging
**Prompt:**
> "I am getting the following error in my [Language/Framework] application: `[Paste Error Message]`. 
> Here is the relevant code snippet: 
> ```[language]
> [Paste Code Here]
> ```
> Please explain why this error is happening and provide the corrected code. Keep the explanation brief and highlight the exact line that caused the issue."

## 2. Next.js & React Specific 
**Prompt:**
> "I am building a Next.js 15 application using React 19. I am facing a [hydration error / client-side routing issue / server component error]. 
> Here is my component code: 
> ```tsx
> [Paste Code]
> ```
> How can I resolve this while adhering to Next.js App Router best practices?"

## 3. Python Flask Backend Debugging
**Prompt:**
> "I have a Python Flask backend serving a REST API. When I send a [GET/POST] request to `[Endpoint URL]` with this JSON payload: `[Paste Payload]`, I get a [500 Internal Server Error / 400 Bad Request]. 
> Here is my route handling code:
> ```python
> [Paste Code]
> ```
> Please identify the bug in the data parsing or database query logic."

## 4. CSS/Tailwind Layout Issues
**Prompt:**
> "I am using Tailwind CSS v4. I am trying to achieve [describe the layout, e.g., a centered flex container with 3 columns on desktop and 1 on mobile], but it looks like [describe the current wrong appearance]. 
> Here is my HTML/JSX structure:
> ```html
> [Paste Code]
> ```
> Provide the corrected Tailwind classes to fix this responsive layout."
