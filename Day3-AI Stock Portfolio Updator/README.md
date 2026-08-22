# 🚀 AI-Powered Stock Portfolio Updater with n8n

> **Day 3 of my AI Automation Journey**

An AI-powered automation workflow built with **n8n** that connects an AI Agent with **Google Sheets** and **Marketstack** to automatically retrieve and update stock market information in a portfolio spreadsheet.

---

## 📌 Overview

This project demonstrates how an AI Agent can use multiple external tools to perform a real-world automation task.

The AI Agent can:

* Read stock information from a Google Sheet
* Identify stock tickers in the portfolio
* Retrieve market data using Marketstack
* Extract the latest Price, Day High, and Day Low
* Automatically update the corresponding rows in Google Sheets
* Respond to natural-language instructions

Instead of manually checking market data and updating a spreadsheet, the AI Agent handles the process using connected tools.

---

## 🎯 Objective

The objective of this project was to learn how to:

* Connect an AI Agent with Google Sheets
* Give an AI Agent access to external tools
* Retrieve data from an external API
* Use multiple tools within a single AI Agent workflow
* Read and update structured data
* Understand tool inputs and outputs
* Work with JSON and structured data in n8n

---

## 🛠️ Tools & Technologies

* **n8n** — Workflow automation
* **Google Gemini** — Chat Model for the AI Agent
* **Google Sheets** — Portfolio data storage
* **Marketstack** — Stock market data
* **Simple Memory** — Maintains conversation context
* **JSON** — Structured tool input/output

---

# 🔄 Workflow

The complete workflow follows this process:

```text
User
  ↓
AI Agent
  ↓
Google Sheets — Get Rows
  ↓
Identify Stock Tickers
  ↓
Marketstack — Get EOD Market Data
  ↓
Retrieve Price / Day High / Day Low
  ↓
AI Agent Processes the Data
  ↓
Google Sheets — Update Row
  ↓
Updated Portfolio
```

### 📸 Workflow Screenshot

<img width="400" height="300" alt="Workflow" src="https://github.com/user-attachments/assets/30b41110-94c9-4bb3-99b6-897b0c47bff8" />

Use:

```markdown
<img width="400" height="300" alt="Workflow" src="https://github.com/user-attachments/assets/30b41110-94c9-4bb3-99b6-897b0c47bff8" />
```

This screenshot shows the complete n8n workflow, including the AI Agent, Google Gemini Chat Model, Simple Memory, Google Sheets tools, and Marketstack.

---

# ⚙️ How It Works

## 1. User sends a request

The workflow starts when the user sends a natural-language instruction to the AI Agent.

Example:

> "Please update the Price, Day High, and Day Low in my equity portfolio sheet to reflect the latest market updates."

---

## 2. AI Agent reads the portfolio

The AI Agent uses the **Google Sheets — Get Rows** tool to read the portfolio.

The spreadsheet initially contains:

<img width="300" height="100" alt="image" src="https://github.com/user-attachments/assets/cfa715db-d23b-42d4-bde5-78efe4a75aaf" />


Use:

```markdown
<img width="300" height="100" alt="image" src="https://github.com/user-attachments/assets/cfa715db-d23b-42d4-bde5-78efe4a75aaf" />
```

This shows the portfolio before the automation runs.

---

## 3. Market data is retrieved

The AI Agent uses the **Marketstack** tool to retrieve end-of-day market data for the stock tickers.

The returned data contains information such as:

* Open
* High
* Low
* Close
* Volume
* Symbol
* Exchange
* Date

### 📸 Marketstack Output

<img width="350" height="500" alt="Marketstack Output" src="https://github.com/user-attachments/assets/16c5b909-0593-4022-9588-6aea1481bbe6" />

Use:

```markdown
<img width="350" height="500" alt="Marketstack Output" src="https://github.com/user-attachments/assets/16c5b909-0593-4022-9588-6aea1481bbe6" />
```

This screenshot shows the structured market data returned by Marketstack.

---

## 4. AI Agent processes the information

The AI Agent identifies the required values from the market data:

* Price
* Day High
* Day Low

It then prepares the information to update the appropriate rows in the portfolio.

---

## 5. Google Sheets is updated

The AI Agent uses the **Google Sheets — Update Row** tool.

The **Ticker** is used to identify the correct stock row, while the market values are written into the corresponding columns.

<img width="350" height="220" alt="image" src="https://github.com/user-attachments/assets/7ccafea7-794a-48c6-80eb-3c5f94a2ce05" />

Use:

```markdown
<img width="350" height="220" alt="image" src="https://github.com/user-attachments/assets/7ccafea7-794a-48c6-80eb-3c5f94a2ce05" />
```

This screenshot shows the values being passed to the Google Sheets update operation.

---

## 6. Portfolio is automatically updated

After the workflow finishes, the spreadsheet contains the updated market information.

<img width="300" height="100" alt="image" src="https://github.com/user-attachments/assets/6c029233-28d9-4760-ad51-1127f3ea0164" />

Use:

```markdown
<img width="300" height="100" alt="image" src="https://github.com/user-attachments/assets/6c029233-28d9-4760-ad51-1127f3ea0164" />
```

This is the final result of the automation.

---

# 🤖 AI Agent in Action

The AI Agent can understand a natural-language instruction and use its connected tools to complete the task.

### Example instruction

> "Please update the Price, Day High, and Day Low in my equity portfolio sheet to reflect the latest market updates."

The Agent then reads the portfolio, retrieves market data, and updates the spreadsheet.

### 📸 AI Agent Conversation

<img width="400" height="400" alt="AI Agent Conversation" src="https://github.com/user-attachments/assets/c055704a-f1ef-4688-ae88-0bce67e9aa30" />

Use:

```markdown
<img width="400" height="400" alt="AI Agent Conversation" src="https://github.com/user-attachments/assets/c055704a-f1ef-4688-ae88-0bce67e9aa30" />
```

---

# 🧰 AI Agent Tools

The AI Agent uses three main tools.

### 1. Google Sheets — Get Rows

Reads the existing portfolio information from the spreadsheet.

### 2. Marketstack — Get EOD Data

Retrieves market information for the stock tickers.

### 3. Google Sheets — Update Row

Updates the corresponding portfolio rows with the retrieved market information.

---

# 🧠 AI Agent Architecture

The AI Agent is connected to:

```text
Google Gemini Chat Model
        +
Simple Memory
        +
Google Sheets Tools
        +
Marketstack Tool
```

This allows the Agent to understand the user's request, access external information, and perform actions using multiple tools.

---

# 📚 What I Learned

Through this project, I practiced:

* Building AI Agent workflows in n8n
* Connecting AI Agents with external tools
* Google Sheets integration
* API integration
* Retrieving structured market data
* Updating spreadsheet rows dynamically
* Multi-tool AI Agent workflows
* Tool inputs and outputs
* JSON and structured data
* Using natural-language instructions to trigger automation
* Inspecting workflow executions for debugging

---

# 🚀 Future Improvements

Possible improvements for this project include:

* Add percentage change calculations
* Add portfolio value calculation
* Add profit/loss tracking
* Add more market indicators
* Add scheduled automatic updates
* Add email or messaging notifications
* Support larger portfolios
* Add additional financial data sources

---

# 📁 Project Structure

```text
Day-03-AI-Stock-Portfolio-Updater/
│
├── README.md
├── workflow.json
│
└── screenshots/
    ├── workflow.png
    ├── Before Google Sheet.png
    ├── After Google Sheet.png
    ├── AI Agent Response.jpeg
    ├── Marketstack output.png
    └── Update Row output.png
```

---

# 🌱 AI Automation Journey

This project is part of my ongoing **AI Automation Journey with n8n**, where I am learning by building practical automation workflows and gradually connecting AI Agents with real-world tools and services.

**Day 3 completed. 🚀**

---

# ⭐ Key Takeaway

This project helped me understand that an AI Agent can do more than generate text.

By connecting it with external tools, the Agent can:

**Understand → Decide → Retrieve → Process → Update**

and perform an end-to-end automation task.
