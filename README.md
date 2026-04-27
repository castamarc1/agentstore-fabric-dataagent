# 🏪 Contoso Sales Analytics Agent

> **A low-code agentic solution that lets business users query sales data using natural language — powered by Microsoft Fabric and Copilot Studio.**

[![Solution Type](https://img.shields.io/badge/Solution-Low--Code-green)]()
[![Industry](https://img.shields.io/badge/Industry-Cross--industry-blue)]()
[![Time to Deploy](https://img.shields.io/badge/Time-~30%20min-orange)]()

---

## 🎯 What Is This?

This repository contains everything you need to build a **conversational AI agent** that answers business questions about sales data — no coding required.

A business user simply opens **Microsoft Teams** and asks:

> *"What were our top 5 products by revenue last quarter?"*

...and gets an instant, data-driven answer.

---

## 🏗️ Architecture

```
┌──────────────────┐     ┌───────────────────┐     ┌──────────────────────┐
│  Copilot Studio  │────▶│  Fabric Data      │────▶│  Fabric Lakehouse    │
│  Agent (Teams)   │◀────│  Agent            │◀────│  (Products + Sales)  │
└──────────────────┘     └───────────────────┘     └──────────────────────┘
                                                      ▲
                                                      │
                                                 PySpark Notebook
                                                 (one-click setup)
```

| Component | What It Does |
|-----------|-------------|
| **Fabric Lakehouse** | Stores the sample data (2 Delta tables) |
| **PySpark Notebook** | Creates the Lakehouse data in one click — 50 products, 500 transactions |
| **Fabric Data Agent** | Translates natural language questions into SQL and returns insights |
| **Copilot Studio Agent** | Conversational UI deployed to Microsoft Teams |

---

## ⚡ Quick Start (~30 minutes)

### Prerequisites

- A **Microsoft Fabric workspace** with capacity (F2+ or trial) — [Create a workspace](https://learn.microsoft.com/en-us/fabric/fundamentals/create-workspaces) · [Start a free trial](https://learn.microsoft.com/en-us/fabric/fundamentals/fabric-trial)
- **Data Agent (preview)** enabled in tenant settings — [Configure tenant settings](https://learn.microsoft.com/en-us/fabric/data-science/data-agent-tenant-settings)
- A **Microsoft 365 Copilot** license **or** a **Copilot Studio metered (PAYG)** plan linked to an Azure subscription — [Copilot Studio licensing](https://learn.microsoft.com/en-us/microsoft-copilot-studio/billing-licensing) · [Set up PAYG](https://learn.microsoft.com/en-us/microsoft-365/copilot/pay-as-you-go/setup)
- **Member** or **Admin** role in the Fabric workspace
- Access to **Copilot Studio** ([copilotstudio.microsoft.com](https://copilotstudio.microsoft.com))

### Steps 1–2: Set up the data layer (both paths)

These two steps are required regardless of which path you choose for the Copilot Studio agent:

| Step | Guide | Time | What You'll Build |
|------|-------|------|-------------------|
| **1** | [📓 Create Lakehouse & Sample Data](docs/01-run-notebook.md) | ~10 min | A Lakehouse with Products and SalesTransactions tables |
| **2** | [🤖 Create the Data Agent](docs/02-create-data-agent.md) | ~10 min | A Fabric Data Agent answering NLQ over your data |

### Step 3: Create the Copilot Studio Agent — choose your path

After completing Steps 1 and 2, you have **two options** for the Copilot Studio agent:

| Path | Guide | Time | Best For |
|------|-------|------|----------|
| **🅰️ Import solution** (recommended) | [📦 Import Guide](copilot-studio/import-guide.md) | ~5 min | Quick setup — import the `.zip`, set 2 environment variables, done |
| **🅱️ Build manually** | [💬 Manual Guide](docs/03-create-copilot-studio.md) | ~10 min | Learning the process or customizing the agent from scratch |

> **💡 We recommend Path A** if you want to get up and running quickly. Choose Path B if you want to understand how the Copilot Studio agent is built or need to customize it.

---

## 📂 Repository Structure

```
agentstore-fabric-dataagent/
├── README.md                              ← You are here
├── fabric/
│   └── contoso_sales_setup.ipynb          ← PySpark notebook (creates Lakehouse data)
├── docs/
│   ├── 01-run-notebook.md                 ← Guide: Lakehouse & data setup
│   ├── 02-create-data-agent.md            ← Guide: Fabric Data Agent
│   ├── 03-create-copilot-studio.md        ← Guide: Copilot Studio agent
│   └── images/                            ← Screenshots (add your own)
├── copilot-studio/
│   ├── import-guide.md                    ← How to import & configure the solution
│   └── ContosoDataAgent_1_0_0_13.zip      ← Copilot Studio solution (ready to import)
```

---

## 🗂️ Sample Data

The notebook generates realistic sample data:

**Products** (50 rows)

| Column | Type | Example |
|--------|------|---------|
| ProductID | int | 1 |
| ProductName | string | Wireless Headphones |
| Category | string | Electronics |
| UnitPrice | decimal | 79.99 |

**SalesTransactions** (500 rows)

| Column | Type | Example |
|--------|------|---------|
| TransactionID | int | 1 |
| ProductID | int | 12 |
| SalesRep | string | Alice Johnson |
| Region | string | North America |
| Quantity | int | 3 |
| TotalAmount | decimal | 239.97 |
| TransactionDate | date | 2024-06-15 |

**Categories:** Electronics, Clothing, Home & Garden, Sports, Food & Beverages, Books, Health & Beauty, Toys

**Regions:** North America, Europe, Asia Pacific, Latin America, Middle East & Africa

---

## 💡 Sample Questions to Ask the Agent

Once everything is set up, try these:

- *"What are the top 5 products by total revenue?"*
- *"Show me sales by region for last year"*
- *"Which sales rep had the highest growth?"*
- *"What is the average order value by product category?"*
- *"Compare Electronics vs Clothing sales"*
- *"How many transactions happened in Q4 2024?"*

---

## 🔧 Troubleshooting

| Issue | Solution |
|-------|----------|
| **Notebook fails to run** | Make sure a Lakehouse is attached to the notebook (left panel → Add Lakehouse) |
| **Data Agent can't find tables** | Verify the Lakehouse has been refreshed — open the SQL analytics endpoint and check tables |
| **Data Agent not appearing in Copilot Studio** | Ensure the Data Agent is **published** and you're using the same tenant for both Fabric and Copilot Studio |
| **Copilot Studio can't connect to Fabric** | Check that you have an F2+ capacity and a Microsoft 365 Copilot license |
| **Teams agent not responding** | Allow a few minutes after publishing for the agent to become available in Teams |

---

## 📋 Agent Store Entry

See [`agent-store/catalogue-entry.md`](agent-store/catalogue-entry.md) for the complete Agent Store metadata and a 5-minute demo script.

| Field | Value |
|-------|-------|
| **Name** | Contoso Sales Analytics Agent |
| **Solution Type** | Low-code |
| **Industry** | Cross-industry (Retail / Sales) |
| **Department** | Sales & Analytics |
| **Time to Replicate** | ~30 minutes |

---

## 📚 Useful Links

| Resource | Link |
|----------|------|
| **Create a Fabric workspace** | [learn.microsoft.com](https://learn.microsoft.com/en-us/fabric/fundamentals/create-workspaces) |
| **Start a Fabric free trial** | [learn.microsoft.com](https://learn.microsoft.com/en-us/fabric/fundamentals/fabric-trial) |
| **Create a Lakehouse** | [learn.microsoft.com](https://learn.microsoft.com/en-us/fabric/data-engineering/create-lakehouse) |
| **Configure Data Agent tenant settings** | [learn.microsoft.com](https://learn.microsoft.com/en-us/fabric/data-science/data-agent-tenant-settings) |
| **Create a Fabric Data Agent** | [learn.microsoft.com](https://learn.microsoft.com/en-us/fabric/data-science/how-to-create-data-agent) |
| **Data Agent end-to-end tutorial** | [learn.microsoft.com](https://learn.microsoft.com/en-us/fabric/data-science/data-agent-end-to-end-tutorial) |
| **Copilot Studio licensing** | [learn.microsoft.com](https://learn.microsoft.com/en-us/microsoft-copilot-studio/billing-licensing) |
| **Set up Copilot Studio PAYG** | [learn.microsoft.com](https://learn.microsoft.com/en-us/microsoft-365/copilot/pay-as-you-go/setup) |
| **Connect Data Agent to Copilot Studio** | [learn.microsoft.com](https://learn.microsoft.com/en-us/microsoft-copilot-studio/add-agent-fabric-data-agent) |
| **Consume Data Agent in Copilot Studio** | [learn.microsoft.com](https://learn.microsoft.com/en-us/fabric/data-science/data-agent-microsoft-copilot-studio) |

---

## 🤝 Contributing

Found a bug or want to improve the guides? Open an issue or submit a PR. Screenshots for the `docs/images/` folder are especially welcome!

---

## 📄 License

This project is provided as-is for internal use. See your organization's policies for redistribution.
