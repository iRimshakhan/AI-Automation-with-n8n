# Day 5 – AI Agent with Pushover Push Notifications

## 📌 Overview

As part of my **AI Automation Journey with n8n**, I explored how an AI Agent can interact with an external service and trigger real-world actions.

For Day 5, I built an **n8n AI Agent integrated with Pushover** to send push notifications directly to a mobile device.

The workflow allows the AI Agent to understand a user's request, retrieve the current date using the Date & Time tool, and send a customized notification through Pushover.

---

## 🔄 Workflow
```text
When Chat Message Received
  ↓
AI Agent
  ↓
Google Gemini Chat Model + Simple Memory
  ↓
Tools
  ↓
Pushover + Date & Time
  ↓
Push Notification to Mobile Device
```
---

## 🧩 Components Used

### 1. When Chat Message Received

Acts as the trigger for the workflow.

The workflow starts when a user sends a message to the n8n chat interface.

### 2. AI Agent

The AI Agent is responsible for understanding the user's request and deciding which tools it needs to use.

Instead of manually defining every action, the agent can select the appropriate tool based on the user's instruction.

### 3. Google Gemini Chat Model

Gemini provides the language model used by the AI Agent to understand and process the user's request.

### 4. Simple Memory

Simple Memory allows the AI Agent to maintain conversational context during the interaction.

### 5. Pushover

Pushover is used as an external notification service.

The Pushover integration was authenticated using:

* **Application API Token** – application-level credential
* **User Key** – user-level credential

The important distinction is that the application token and user key serve different purposes during authentication.

### 6. Date & Time

The Date & Time tool allows the AI Agent to retrieve the current date.

This makes it possible for the agent to provide dynamic information instead of relying on a manually entered date.

---

## 🔐 API Authentication

One of the main concepts I learned was connecting an external service to n8n using API credentials.

Pushover requires two important credentials:

| Credential            | Purpose                                |
| --------------------- | -------------------------------------- |
| Application API Token | Authenticates the Pushover application |
| User Key              | Identifies the Pushover user           |

The credentials were added securely through n8n's credential system rather than being directly exposed inside the workflow.

---

## 🤖 Dynamic Tool Parameters

A particularly useful concept was allowing the **AI Agent to define the notification message dynamically**.

Instead of hardcoding a message such as:

`Today's date is...`

the Pushover tool was configured so that the **model can define the message parameter**.

This means the AI Agent can determine what should be sent based on the user's request.

---

## 🧪 Test

I tested the workflow with the request:

> "Please send me a Pushover notification with today's date."

The AI Agent:

1. Understood the request.
2. Used the Date & Time tool to retrieve the current date.
3. Used the Pushover tool.
4. Generated the notification message.
5. Sent the notification to my phone.

### Complete Workflow

<img width="600" height="378" alt="workflow" src="https://github.com/user-attachments/assets/e8274797-2d47-4ee3-8a9f-a08ac9b78965" />

### Notification Result

<img width="300" height="150" alt="result" src="https://github.com/user-attachments/assets/08386780-0c78-4081-b6c3-991e84402b6a" />

---

## 💡 Key Learning

The biggest takeaway from this workflow was understanding how an **AI Agent can move beyond generating text and actually perform actions using external tools**.

The workflow demonstrates the basic pattern:

**User Request → AI Reasoning → Tool Selection → External Action → Real-World Result**

This is an important concept in AI automation because the AI Agent is not limited to answering questions—it can interact with external services and trigger useful actions.

---

## 🚀 What I Learned

* How to integrate Pushover with n8n
* How API-based authentication works
* Difference between application-level and user-level credentials
* How to connect external services as AI Agent tools
* How an AI Agent can dynamically select and use tools
* How to retrieve real-time information using the Date & Time tool
* How to allow the model to define tool parameters
* How AI automation can trigger real-world notifications

---

## 🛠️ Tech Stack

* **n8n**
* **Google Gemini**
* **Pushover**
* **AI Agents**
* **API Authentication**
* **Simple Memory**
* **Date & Time Tool**

---

## 🎯 Outcome

Successfully built and tested an AI-powered notification workflow where an n8n AI Agent receives a natural-language request, retrieves the current date, and sends a personalized push notification to a mobile device through Pushover.

**Day 5 complete! 🚀**

