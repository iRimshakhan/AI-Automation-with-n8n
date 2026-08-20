# 🤖 Day 1 — AI Financial Assistant using n8n

My first AI Agent automation workflow built using **n8n and Google Gemini**.

## 🚀 What I Built

This workflow creates a conversational AI Agent that can:

* Receive messages through a chat interface.
* Understand user questions using Google Gemini.
* Maintain conversation context using Simple Memory.
* Use an external market-data tool when required.
* Return the requested information to the user.

## 🧩 Workflow

```text
Chat Trigger
     ↓
  AI Agent
   ↙  ↓  ↘
Gemini  Memory  Market Data Tool
     ↓
   Response
```

## 🛠️ Technologies Used

* n8n
* Google Gemini
* AI Agent
* Simple Memory
* Market Data Tool

## 💡 Example

The workflow was tested with a financial-market query about TCS.

The AI Agent identified that external market information was required, used the connected tool, and returned the retrieved information to the user.

## 📸 Workflow Preview

<img width="300" height="500" alt="image" src="https://github.com/user-attachments/assets/e209e86f-59c4-4b73-a9ca-3a7f65fbf4cf" />

## 🔐 Credentials

API keys and private credentials are **not included** in this repository.

To run this workflow, configure your own Gemini/API credentials in n8n.

## 🎯 Learning Objective

This project helped me understand the fundamentals of:

* AI Agents
* LLM integration
* Memory
* Tool calling
* Workflow automation
* AI-powered decision making

## 📈 Learning Journey

This is **Day 1** of my AI Automation learning journey.

More workflows and progressively complex AI Agent projects will be added as I continue learning.
