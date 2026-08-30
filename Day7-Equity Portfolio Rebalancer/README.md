# Day 8 – Building an AI-Powered Equity Portfolio Rebalancer with n8n

## 📌 Overview

On Day 8, I built a more sophisticated **AI-powered business automation workflow** using **n8n**.

The project simulates an **Equity Portfolio Rebalancer** that receives a portfolio rebalancing objective through a web form and uses an AI Agent to:

- Read portfolio data from Google Sheets
- Retrieve market prices
- Update portfolio prices
- Make portfolio rebalancing decisions
- Update the new portfolio quantities
- Verify whether the target allocation was achieved
- Send notifications and an email with the results
- Apply traditional workflow logic using an IF node
- Deploy the workflow into production

This project demonstrated how **Agentic AI and traditional workflow automation can work together** to automate a real-world business process.

> **Important:** This project is an educational automation exercise based on a simulated portfolio. It should not be considered financial advice or used as the sole basis for real investment decisions.

---

## 🎯 Objective

The objective of this project was to create an AI-powered workflow capable of receiving a portfolio allocation goal such as:

> Ensure the portfolio is 60% equity and 40% fixed income.

The AI Agent then uses the available tools and portfolio data to work toward that goal and communicate the results.

---

## 🚀 What I Built

I built an automated workflow called:

**Equity Portfolio Rebalancer**

The workflow includes:

1. A Form Submission trigger
2. An AI Agent
3. An AI Chat Model
4. Google Sheets tools
5. MarketStack market data
6. Portfolio price updates
7. Portfolio quantity updates
8. Portfolio verification and iteration
9. Pushover notifications
10. Gmail email notifications
11. IF logic for workflow validation
12. Send Success or Failure notification
13. Production deployment using the live form URL

The workflow combines the flexibility of an AI Agent with the reliability of traditional workflow logic.

---

## Workflow Architecture

### Main Workflow

**Form Submission Trigger**

↓

**AI Agent**

Connected to:

- AI Chat Model
- Google Sheets – Get Rows
- MarketStack – Get Market Data
- Google Sheets – Update Price
- Google Sheets – Update Quantity After Rebalancing
- Pushover Tool
- Gmail Tool

↓

**IF Node**

If AI Agent output equals `OK`

- True → Success Pushover notification
- False → Failure Pushover notification

---

#  AI Agent Tools

##  Tool 1 – Google Sheets: Get Portfolio Rows

The first Google Sheets tool allows the AI Agent to retrieve the portfolio data.

### Configuration

- Document: Portfolio
- Sheet: Sheet 1
- Operation: Get Rows
- Filters: None

The Agent can retrieve the entire portfolio and examine:

- Positions
- Quantities
- Equity allocation
- Fixed income allocation
- Prices
- Rebalancing information

---

## 📝 Improving the Tool Description

The default tool description was too generic.

The tool description was manually improved so that the AI model understands the purpose of the tool.

The description explains that the tool:

- Provides details of the user's portfolio
- Includes positions and equity/fixed income breakdown
- Should be used before making rebalancing decisions
- Should also be used after rebalancing
- Helps the Agent verify whether the goal was achieved
- Supports iteration if the objective has not been reached

---

## Tool 2 – MarketStack

MarketStack was added to retrieve market data.

The AI Agent can use the tool to obtain end-of-day market data for portfolio tickers.

### Purpose

The tool helps the Agent:

- Retrieve market prices
- Understand the current value of positions
- Update portfolio price information before rebalancing

The model can decide which ticker requires market data.

---

## Tool 3 – Google Sheets: Update Price

A second Google Sheets operation was configured to update portfolio prices.

### Logic

The tool:

- Matches the correct row using the ticker
- Updates the Price column

The AI Agent can determine:

- Which ticker to update
- Which price to insert

---

## Tool 4 – Google Sheets: Update New Quantity

Another Google Sheets operation was configured for portfolio rebalancing decisions.

### Logic

The tool:

- Matches the row using the ticker
- Updates the New Quantity After Rebalancing column

The AI Agent uses this tool to write its rebalancing decisions into the spreadsheet.

---

## Tool 5 – Pushover

Pushover was configured as an AI Agent tool.

The AI Agent can send a push notification containing a concise summary of the portfolio rebalancing result.

The model can determine the message content when Pushover is used as an AI tool.

A user key is required for the Pushover integration.

---

## Tool 6 – Gmail

Gmail was added as an AI Agent tool.

The workflow sends an email containing the portfolio rebalancing decisions.

### Example Fixed Subject

**Equity Rebalancer Trading Decisions**

The AI Agent can generate the message content.

The email is configured as HTML.

---
# Adding Traditional Workflow Logic

The final part of the project added traditional workflow logic to the AI-powered workflow.

One of the strengths of n8n is that it can combine:

- AI Agents
- AI tools
- APIs
- Traditional workflow automation
- Visual logic

An **IF node** was added after the AI Agent.

The AI Agent was instructed to respond with:

`OK`

only when its mission was successfully completed.

---

## 🔀 IF Node Configuration

The IF node checks the AI Agent output.

### Condition

The workflow checks whether:

`$json.output`

is equal to:

`OK`

### True Branch

If the Agent successfully completes the task and returns `OK`:

- A success Pushover notification is sent
- Message: `Rebalancing Successful`
- Priority: Low

### False Branch

If the Agent does not return `OK`:

- A failure notification is sent
- Message: `Rebalancer Failed`
- Priority: Emergency

This adds deterministic business logic after the AI Agent.

---

# Core Node vs AI Tool

A major concept from this project was understanding the difference between a node used as a **workflow step** and a node used as an **AI Agent tool**.

## Pushover as an AI Tool

When Pushover is connected to the AI Agent as a tool:

- The tool description is provided to the AI model
- The AI model decides whether to use it
- The AI model can optionally generate inputs such as the message
- The tool is used at the discretion of the AI Agent

This makes it an Agent-controlled action.

---

## Pushover as a Core Workflow Node

When Pushover is placed directly on the workflow canvas:

- It is a fixed workflow step
- It does not depend on AI reasoning
- The workflow controls when it runs
- The configured action is performed with the specified data

In this project, the IF node determines which Pushover node should run.

### Key Difference

**AI Tool:** The AI model decides whether to call it.

**Core Node:** The workflow logic determines when it runs.

This distinction is important when designing AI-powered automations.

---

# 🧪 Final Workflow Test

The portfolio was cleared and the complete workflow was executed again.

The process successfully:

- Triggered from the form
- Retrieved portfolio information
- Updated prices
- Performed rebalancing
- Updated portfolio quantities
- Verified the result
- Sent notifications
- Sent an email
- Returned `okay`
- Passed through the IF node
- Triggered the success branch

The failure notification was not triggered.

The IF node visually confirmed that the output matched the expected value.

---

# 🌐 Deploying to Production

After testing the workflow successfully, it was deployed into production.

The Form Submission trigger provides a production URL.

The deployment process involved:

1. Saving the workflow
2. Opening the Form Submission node
3. Copying the Production URL
4. Publishing the workflow
5. Opening the production form
6. Submitting the portfolio request
7. Allowing the live workflow to execute

The production form acts like a live webpage that users can access and submit.

<img width="693" height="419" alt="image" src="https://github.com/user-attachments/assets/da90b7cc-2121-4b4c-b45b-bcb7ebea6a0a" />

---

# 📲 Production Results

The workflow successfully executed in production.

The production run demonstrated that the system could:

- Receive the live form submission
- Trigger the deployed workflow
- Retrieve and update prices
- Perform portfolio rebalancing
- Update quantities
- Send notifications
- Send an email
- Record the execution in n8n

The workflow was therefore demonstrated as a complete deployed automation rather than only a development experiment.

---

# 🧰 Tools and Technologies Used

| Tool | Purpose |
|---|---|
| n8n | Workflow automation and orchestration |
| AI Agent | Autonomous decision-making |
| AI Chat Model | Reasoning and tool selection |
| Google Sheets | Portfolio data storage and updates |
| MarketStack | Market data retrieval |
| Pushover | Push notifications |
| Gmail | Email notifications |
| Form Submission | User input and workflow trigger |
| IF Node | Traditional conditional workflow logic |

---

# 📸 Screenshots

The following screenshots can be added to document the project.

### 1. Complete n8n Workflow

<img width="700" height="353" alt="image" src="https://github.com/user-attachments/assets/0f962451-e161-42df-a442-3ec19679a357" />

### 2. Portfolio Rebalancer Form

<img width="693" height="419" alt="image" src="https://github.com/user-attachments/assets/a16ef4b3-7ca4-4428-942d-4cca2206d61f" />

### 3. Google Sheets Portfolio

<img width="1090" height="171" alt="image" src="https://github.com/user-attachments/assets/b6565076-0adf-4f0f-9e06-dcfc10a98d7b" />

### 4. AI Agent Configuration

<img width="800" height="481" alt="image" src="https://github.com/user-attachments/assets/48555148-af1e-49f0-80e3-519e9cf3ac0a" />

### 5. Pushover Notifications

<img width="550" height="245" alt="image" src="https://github.com/user-attachments/assets/e3cfee4d-e01e-4901-ac2c-fdd032018593" />

### 6. Email Result

<img width="550" height="245" alt="image" src="https://github.com/user-attachments/assets/96669bdf-8159-4b00-86d3-aa1fabffa5e9" />

---

# 🏆 Final Outcome

By the end of Day 8, I had built and deployed an AI-powered business automation workflow that can:

✅ Accept a portfolio objective through a web form

✅ Read portfolio data from Google Sheets

✅ Retrieve market prices

✅ Update portfolio prices

✅ Make AI-driven rebalancing decisions

✅ Update portfolio quantities

✅ Verify whether the target allocation was achieved

✅ Iterate when additional changes are needed

✅ Send AI-generated notifications

✅ Send portfolio decisions by email

✅ Apply deterministic IF logic

✅ Send different notifications for success and failure

✅ Run as a deployed production workflow

---

# 📚 Key Learnings

The biggest lesson from this project was that building reliable AI agents is not only about selecting a powerful model.

The quality of an Agent depends heavily on:

- The context it receives
- The tools available to it
- Tool descriptions
- Prompt instructions
- Workflow design
- Verification logic
- Iterative testing

I also learned how AI Agents and traditional workflow automation can complement each other.

The AI Agent provides flexibility and autonomous decision-making, while traditional nodes such as the IF node provide predictable and deterministic business logic.

This project demonstrated a practical example of automating a real-world business process using **AI Agents, APIs, tools, workflow logic, notifications, and production deployment**.

---

# 🎯 Conclusion

This project was a major step in understanding how to build complete AI-powered automations.

The Equity Portfolio Rebalancer combines:

**Agentic AI + Context Engineering + External Tools + APIs + Google Sheets + Conditional Logic + Notifications + Production Deployment**

Rather than building only a chatbot, this project demonstrated how an AI Agent can interact with external systems and participate in an end-to-end automated business process.

The workflow can be further improved for larger portfolios by improving calculations, spreadsheet context, prompts, and tool design.

Overall, this project provided hands-on experience with designing, testing, debugging, validating, and deploying a sophisticated AI automation workflow in n8n.

---

## 👤 Author

**Khan Rimsha Fatima Mohammed Naim**

🎓 Master's in Information Technology (Artificial Intelligence)

🤖 Interested in Artificial Intelligence, Generative AI, AI Agents, Machine Learning, Data Science, and AI Automation

🔗 GitHub: https://github.com/iRimshakhan

💼 LinkedIn: https://linkedin.com/in/rimshafatimakhan

---

⭐ If you found this project interesting, feel free to explore the workflow, learn from the architecture, and experiment with ways to make the AI Agent more reliable and scalable.
