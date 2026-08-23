#  AI Gmail Assistant: Read Emails & Create Drafts

> **Day 4 of my AI Automation Journey with n8n**

An AI-powered Gmail assistant built using **n8n**, **Google Gemini**, and the **Gmail API**.

This workflow allows an AI Agent to interact with Gmail through natural-language instructions. The agent can retrieve recent emails and create email drafts using connected Gmail tools.

---

## 📌 Overview

In this project, I built an AI Agent that can interact with my Gmail account using external tools.

The AI Agent can:

- Retrieve recent emails
- Read and summarize email information
- Retrieve a list of recent emails
- Create an email draft
- Understand natural-language instructions
- Maintain conversation context using memory

Instead of manually navigating Gmail for every task, I can give the AI Agent a natural-language instruction and allow it to use the appropriate Gmail tool.

---

## 🎯 Objective

The objective of this project was to learn how to:

- Connect an AI Agent with Gmail
- Integrate Gmail tools into an n8n workflow
- Retrieve recent emails
- Use filters while retrieving Gmail messages
- Create Gmail drafts through an AI Agent
- Use natural-language instructions to perform email-related tasks
- Understand AI Agent tool permissions
- Give an AI Agent controlled access to external tools

---

## 🛠️ Tools & Technologies

- **n8n** — Workflow automation
- **Google Gemini** — Chat Model for the AI Agent
- **Gmail** — Email integration
- **Gmail API** — Accessing Gmail messages and drafts
- **Simple Memory** — Maintains conversation context
- **Expressions** — Dynamic values and filtering inside n8n

---

# 🔄 Workflow Architecture

The workflow follows this structure:
```text
User
↓
When Chat Message Received
↓
AI Agent
├── Google Gemini Chat Model
├── Simple Memory
├── Gmail — Get Many Messages
└── Gmail — Create Draft
↓
Response / Action Completed
```
The AI Agent decides which Gmail tool to use based on the user's request.

---

## 📸 Complete Workflow

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/81c92079-17cb-406c-9ef0-af55a873300d" />

The workflow includes:

- Chat trigger
- AI Agent
- Google Gemini Chat Model
- Simple Memory
- Gmail tool for retrieving messages
- Gmail tool for creating drafts

---

# ⚙️ How It Works

## 1. AI Agent retrieves Gmail messages

The workflow starts when a user sends a message to the AI Agent.
The AI Agent understands the request and selects the appropriate Gmail tool.

<img width="350" height="150" alt="image" src="https://github.com/user-attachments/assets/6888565a-d35a-4571-8faa-a5828b2789ab" />

In this example, the AI Agent was asked:

> "Hello, give me a list of my top 5 emails."

The Agent successfully retrieved and displayed recent email information.

---

## 3. AI Agent creates an email draft

The second Gmail tool allows the AI Agent to create an email draft.

The Agent can use the information provided in a natural-language instruction to determine:

- Recipient
- Subject
- Email message

The workflow creates a **draft** instead of directly sending the email, providing more control over the final email before it is sent.

---

<img width="350" height="150" alt="image" src="https://github.com/user-attachments/assets/839343eb-b8cb-4da3-af77-ef982850e4ed" />

In this example, I asked the AI Agent to create a draft email with a specific message.

The AI Agent successfully processed the request and created the Gmail draft.

---

## 4. Draft appears in Gmail

After the AI Agent completes the workflow, the email is created as a draft in Gmail.

This allows the user to review the email before manually sending it.

---

<img width="350" height="459" alt="image" src="https://github.com/user-attachments/assets/8d20979a-90b7-43f4-8c2d-3834db79a0d2" />

This screenshot shows the final email draft created through the AI Agent workflow.

---

# 🤖 AI Agent Tools

The AI Agent has access to two Gmail tools.

## 📥 Gmail — Get Many Messages

This tool allows the Agent to retrieve recent emails.

It can be used for requests such as:

> "Show me my recent emails."

> "Give me a list of my top 5 emails."

> "Read my latest email."

---

## ✍️ Gmail — Create Draft

This tool allows the Agent to create an email draft based on the user's instructions.

It can determine the required email details from the user's request and create the draft without directly sending the email.

Example:

> "Draft an email saying I very much agree with this sentiment. This is HUGE news."

The transcript demonstrates this controlled approach: the agent was configured to create a draft, with the recipient restricted rather than giving unrestricted sending capability. :contentReference[oaicite:3]{index=3}

---

# 🧠 AI Agent Architecture

The AI Agent combines an LLM, memory, and external Gmail tools:
```text
Google Gemini Chat Model
+
Simple Memory
+
Gmail — Get Many Messages
+
Gmail — Create Draft
```

This enables the Agent to:

**Understand → Decide → Select Tool → Perform Action → Respond**

---

# 🔐 Controlled AI Agent Access

One important concept I learned in this project was **controlling the tools available to an AI Agent**.

Rather than giving an Agent unrestricted access, tools and actions should be selected carefully based on what the Agent needs to perform its task.

For this workflow, the Agent was given capabilities to:

- Read Gmail messages
- Retrieve recent emails
- Create drafts

Creating a draft instead of automatically sending an email provides an additional level of user control. The lesson explicitly emphasized choosing only the tools and permissions you are comfortable allowing the model to use. :contentReference[oaicite:4]{index=4}

---

# 📚 What I Learned

Through this project, I practiced:

- Building AI Agent workflows in n8n
- Connecting an AI Agent with Gmail
- Working with Gmail tools
- Retrieving multiple Gmail messages
- Filtering recent emails
- Using expressions for dynamic values
- Creating email drafts using AI
- Using natural-language instructions to trigger actions
- Connecting AI Agents with external APIs
- Understanding controlled tool access
- Using Simple Memory for conversation context

---

# 🚀 Future Improvements

Possible improvements for this workflow include:

- Summarize unread emails automatically
- Search emails by sender or subject
- Categorize emails by importance
- Create drafts based on incoming emails
- Add approval before performing actions
- Add email scheduling
- Connect with Google Calendar
- Create a complete AI personal assistant

---

# 📁 Project Structure
```text
Day-04-AI-Gmail-Assistant/
│
├── README.md
├── workflow.json
│
└── screenshots/
    ├── workflow.png
    ├── read-emails.png
    ├── create-email-draft.png
    └── gmail-draft-result.png
```

---

# 🌱 AI Automation Journey

This project is part of my ongoing **AI Automation Journey with n8n**.

I am learning by building practical AI workflows and gradually connecting AI Agents with real-world tools and services.

### Day 4 Completed! 🚀

---

# ⭐ Key Takeaway

This project helped me understand that AI Agents can go beyond answering questions.

By connecting an AI Agent with external tools, it can:

**Understand → Choose a Tool → Retrieve Information → Perform an Action → Return a Response**

In this project, the AI Agent was able to interact with Gmail by reading recent emails and creating email drafts through natural-language instructions.
