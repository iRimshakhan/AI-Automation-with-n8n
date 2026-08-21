# 🧠 Day 2 — AI Financial Market Agent with System Message

This is **Day 2** of my AI Automation learning journey with **n8n**.

On Day 1, I built my first AI Agent that could assist me with conversations, remember context, and retrieve financial market data using Marketstack.

On Day 2, I took the same Agent one step further by adding a **System Message** to control its personality and behavior.

---

## 🚀 What I Built

An AI Financial Market Assistant that combines:

* 🤖 AI Agent
* 🧠 Google Gemini Chat Model
* 💾 Simple Memory
* 📈 Marketstack API
* 📝 System Message
* 💬 Chat-based interaction

The System Message instructs the Agent to behave as a **snarky and humorous assistant** while still answering the user's questions and using its connected tools when required.

---

## 🧩 Workflow

```text
                 System Message
                       ↓
Chat Trigger →     AI Agent
                  ↙    ↓    ↘
             Gemini  Memory  Marketstack
                       ↓
                 AI Response
```

### Main Components

| Component          | Purpose                                      |
| ------------------ | -------------------------------------------- |
| **Chat Trigger**   | Receives messages from the user              |
| **AI Agent**       | Processes the request and decides what to do |
| **Google Gemini**  | Provides the language-model capabilities     |
| **Simple Memory**  | Maintains conversation context               |
| **Marketstack**    | Provides financial market data               |
| **System Message** | Defines the Agent's personality and behavior |

---

## 🎯 System Message

For this experiment, I added the following System Message:

> **"You are a snarky, humorous assistant that makes fun of whoever you are chatting with."**

The purpose was to test how a System Message can influence the way an AI Agent communicates and responds.

---

## 🧪 Testing the Agent

### 1️⃣ Testing the Personality

I introduced myself to the Agent:

```text
Hello, Rimsha is here
```

The Agent responded using the humorous personality defined in the System Message.

This demonstrated that the Agent was following the custom behavioral instructions.

---

### 2️⃣ Testing Memory

I then asked:

```text
Well, you know my name?
```

The Agent remembered that my name was **Rimsha**.

This demonstrated how **Simple Memory** can maintain context across messages within the conversation.

---

### 3️⃣ Testing Previous Information

I asked:

```text
What's the recent stock price you told me about?
```

The Agent remembered the previous TCS stock-price information and responded with the value it had previously provided.

This helped me understand how conversational memory allows an Agent to use information from earlier messages.

---

### 4️⃣ Testing the Marketstack Tool

I asked:

```text
Stock price of Google??
```

The Agent used the connected **Marketstack** tool to retrieve financial market information and returned the result while maintaining the personality defined by the System Message.

---

## 📸 Workflow Preview

<img width="350" height="470" alt="Workflow Preview" src="https://github.com/user-attachments/assets/689beefc-ca95-4796-b82c-a8124255896a" />

The workflow shows the connection between:

**Chat Trigger → AI Agent → Gemini + Simple Memory + Marketstack**

It also shows the System Message used to control the Agent's behavior.

---

## 💬 Agent Response & Testing

<img width="350" height="500" alt="Agent Response" src="https://github.com/user-attachments/assets/61a73e3f-452d-44ca-b8b0-ec9134892772" />

This screenshot shows the Agent's behavior during testing, including:

* Remembering my name
* Maintaining conversation context
* Recalling previously provided information
* Retrieving financial market data
* Following the humorous personality defined by the System Message

---

## 🛠️ Technologies Used

* **n8n** — Workflow automation
* **Google Gemini** — Large Language Model
* **AI Agent** — Agent orchestration
* **Simple Memory** — Conversation memory
* **Marketstack API** — Financial market data
* **System Message** — Agent behavior and personality instructions

---

## 🧠 What I Learned

This experiment helped me understand:

* How System Messages influence AI Agent behavior
* How to define an Agent's personality and response style
* How conversational memory works
* How AI Agents can use external tools
* How APIs can provide additional information to an AI Agent
* How an Agent can combine an LLM, memory, instructions, and tools in one workflow

---

## 🔐 Credentials & Security

API keys, tokens, and private credentials are **not included** in this repository.

To run this workflow, configure your own credentials in n8n for:

* Google Gemini
* Marketstack

**Never commit API keys or private credentials to GitHub.**

---

## 📈 Learning Journey

### Day 1

🤖 **Built my first AI Financial Market Assistant**

Learned about:

* AI Agents
* Google Gemini
* Simple Memory
* Tool Calling
* Marketstack API

### Day 2

🧠 **Added System Instructions**

Learned about:

* System Messages
* Controlling Agent behavior
* AI personality
* Memory and context
* Combining instructions with tools

---

## 🔗 Project

This project is part of my **AI Automation with n8n** learning journey.

More AI Agent and automation workflows will be added as I continue learning and building.

**GitHub Repository:**
https://github.com/iRimshakhan/AI-Automation-with-n8n

---

⭐ If you found this project interesting, feel free to explore the repository and follow my AI Automation learning journey.
