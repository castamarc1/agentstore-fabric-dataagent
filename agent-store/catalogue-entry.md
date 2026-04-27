# 📋 Agent Store Catalogue Entry

## Metadata

| Field | Value |
|-------|-------|
| **Name** | Contoso Sales Analytics Agent |
| **Description** | A low-code agentic solution that lets business users query sales data using natural language. Combines a Fabric Lakehouse (sample data via notebook), a Fabric Data Agent (NLQ over data), and a Copilot Studio agent (conversational UI in Teams). Fully replicable in ~30 minutes. |
| **Author** | `<Your Name>` |
| **Solution Type** | Low-code |
| **Industry** | Cross-industry (Retail / Sales demo) |
| **Department** | Sales & Analytics |
| **Attachments** | Repository: [https://github.com/castamarc1/agentstore-fabric-dataagent](https://github.com/castamarc1/agentstore-fabric-dataagent) |

---

## 🎤 Demo Script (5 Minutes)

Use this narrative to walk through the solution in a live demo or customer conversation.

---

### 1️⃣ Show the Lakehouse (~1 min)

> *"Let's start with the data layer. Here's our Fabric Lakehouse — `contoso_sales` — with two tables: **products** and **sales_transactions**. This was populated by running a single notebook with sample data — 50 products and 500 transactions. No data engineering required."*

- Open the **`contoso_sales`** Lakehouse in the Fabric workspace
- Click into the **SQL analytics endpoint**
- Show both tables and preview a few rows

---

### 2️⃣ Open the Data Agent & Ask a Question Live (~2 min)

> *"Now here's where it gets interesting. We created a Fabric Data Agent on top of this Lakehouse. It understands the data model and can answer questions in plain English."*

- Open the **`contoso_sales_agent`** Data Agent
- In the chat pane, type: **"What are the top 5 products by total revenue?"**
- Show the results and highlight that **SQL was generated automatically**
- Ask a follow-up: **"Now break that down by region"**

---

### 3️⃣ Switch to Teams & Chat with the Agent (~1.5 min)

> *"But we don't want users going to the Fabric portal. We brought this into Teams — where they already work. Here's the Copilot Studio agent connected to that same Data Agent."*

- Open **Microsoft Teams**
- Find the **Contoso Sales Assistant** agent
- Type: **"How are our sales doing this quarter?"**
- Show the conversational response with data

---

### 4️⃣ The Punchline (~30 sec)

> *"This entire solution — from data to conversational AI in Teams — took **30 minutes to set up**. **Zero code.** A Lakehouse for data, a Data Agent for intelligence, and Copilot Studio for the conversational experience. All connected, all low-code."*

**Key takeaways to emphasize:**

- ⏱️ **30 minutes** from start to finish
- 🚫 **Zero code** — entirely low-code / no-code
- 💬 **Meets users where they are** — Microsoft Teams
- 🔗 **End-to-end Microsoft stack** — Fabric + Copilot Studio + Teams
- 📈 **Instantly replicable** with any customer's data
