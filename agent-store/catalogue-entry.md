# 📋 Agent Store Catalogue Entry

## Metadata

| Field | Value |
|-------|-------|
| **Name** | Contoso Sales Analytics Agent |
| **Description** | A low-code agentic solution that lets business users query sales data using natural language. Combines a Fabric Lakehouse (sample data via notebook), a Fabric Data Agent (NLQ over data), and direct publishing to the M365 Copilot Agent Store. Fully replicable in ~20 minutes. |
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

- Open the **`Contoso Sales`** Lakehouse in the Fabric workspace
- Click into the **SQL analytics endpoint**
- Show both tables and preview a few rows

---

### 2️⃣ Open the Data Agent & Ask a Question Live (~2 min)

> *"Now here's where it gets interesting. We created a Fabric Data Agent on top of this Lakehouse. It understands the data model and can answer questions in plain English."*

- Open the **`Contoso Sales Analyst`** Data Agent
- In the chat pane, type: **"What are the top 5 products by total revenue?"**
- Show the results and highlight that **SQL was generated automatically**
- Ask a follow-up: **"Now break that down by region"**

---

### 3️⃣ Switch to M365 Copilot & Chat with the Agent (~1.5 min)

> *"But we don't want users going to the Fabric portal. We published this agent directly to the M365 Copilot Agent Store — no Copilot Studio needed. Users find it right where they already work — in Teams or BizChat."*

- Open **M365 Copilot** (Teams or BizChat)
- Find the **Contoso Sales Analyst** in the Agent Store
- Type: **"How are our sales doing this quarter?"**
- Show the conversational response with data
- (Optional) Ask M365 Copilot to **generate a chart** from the results using code interpreter

---

### 4️⃣ The Punchline (~30 sec)

> *"This entire solution — from data to conversational AI in M365 Copilot — took **20 minutes to set up**. **Zero code.** A Lakehouse for data, a Data Agent for intelligence, and one click to publish to the Agent Store. All connected, all low-code, no extra tools required."*

**Key takeaways to emphasize:**

- ⏱️ **20 minutes** from start to finish
- 🚫 **Zero code** — entirely low-code / no-code
- 💬 **Meets users where they are** — M365 Copilot (Teams & BizChat)
- 🔗 **End-to-end Microsoft stack** — Fabric + M365 Copilot
- 📈 **Instantly replicable** with any customer's data
- 🔒 **Security built in** — RLS/CLS fully respected
