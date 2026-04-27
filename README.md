# 🏪 Contoso Sales Analytics Agent

> **A low-code agentic solution that lets business users query sales data using natural language — powered by Microsoft Fabric and M365 Copilot.**

[![Solution Type](https://img.shields.io/badge/Solution-Low--Code-green)]()
[![Industry](https://img.shields.io/badge/Industry-Cross--industry-blue)]()
[![Time to Deploy](https://img.shields.io/badge/Time-~20%20min-orange)]()

---

## 🎯 What Is This?

This repository contains everything you need to build a **conversational AI agent** that answers business questions about sales data — no coding required.

A business user simply opens **M365 Copilot** (in Teams or BizChat) and asks:

> *"What were our top 5 products by revenue last quarter?"*

...and gets an instant, data-driven answer.

---

## 🏗️ Architecture

```
┌──────────────────────┐     ┌──────────────────────┐
│  M365 Copilot        │────▶│  Fabric Data         │────▶  Fabric Lakehouse
│  (Teams / BizChat)   │◀────│  Agent               │◀────  (Products + Sales)
└──────────────────────┘     └──────────────────────┘
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
| **M365 Copilot Agent Store** | Makes the agent available to business users in Teams & BizChat |

---

## ⚡ Quick Start (~20 minutes)

### Prerequisites

- A **Microsoft Fabric workspace** with capacity (F2+ or trial) — [Create a workspace](https://learn.microsoft.com/en-us/fabric/fundamentals/create-workspaces) · [Start a free trial](https://learn.microsoft.com/en-us/fabric/fundamentals/fabric-trial)
- **Data Agent (preview)** enabled in tenant settings — [Configure tenant settings](https://learn.microsoft.com/en-us/fabric/data-science/data-agent-tenant-settings)
- A **Microsoft 365 Copilot** license — [M365 Copilot licensing](https://learn.microsoft.com/en-us/microsoft-365-copilot/microsoft-365-copilot-licensing)
- **Copilot extensibility** enabled by your M365 admin — [Manage Copilot agents](https://learn.microsoft.com/en-us/microsoft-365/admin/manage/manage-plugins-for-copilot-in-integrated-apps)
- **Member** or **Admin** role in the Fabric workspace

### Steps

| Step | Guide | Time | What You'll Build |
|------|-------|------|-------------------|
| **1** | [📓 Create Lakehouse & Sample Data](docs/01-run-notebook.md) | ~10 min | A Lakehouse with Products and SalesTransactions tables |
| **2** | [🤖 Create the Data Agent](docs/02-create-data-agent.md) | ~5 min | A Fabric Data Agent (Contoso Sales Analyst) answering NLQ over your data |
| **3** | [🏪 Publish to M365 Copilot Agent Store](docs/03-publish-to-agent-store.md) | ~5 min | Your agent available to business users in Teams & BizChat |

---

## 📂 Repository Structure

```
agentstore-fabric-dataagent/
├── README.md                              ← You are here
├── source/
│   └── Contoso Sales Setup.ipynb          ← PySpark notebook (creates Lakehouse data)
├── docs/
│   ├── 01-run-notebook.md                 ← Guide: Lakehouse & data setup
│   ├── 02-create-data-agent.md            ← Guide: Fabric Data Agent
│   ├── 03-publish-to-agent-store.md       ← Guide: Publish to M365 Copilot Agent Store
│   └── images/                            ← Screenshots (add your own)
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

Once everything is set up, try these in M365 Copilot:

- *"What are the top 5 products by total revenue?"*
- *"Show me sales by region for last year"*
- *"Which sales rep had the highest growth?"*
- *"What is the average order value by product category?"*
- *"Compare Electronics vs Clothing sales"*
- *"How many transactions happened in Q4 2024?"*

> 💡 **Tip:** You can ask M365 Copilot to generate charts and visualizations from the agent's results using the built-in code interpreter.

---

## 🔧 Troubleshooting

| Issue | Solution |
|-------|----------|
| **Notebook fails to run** | Make sure a Lakehouse is attached to the notebook (left panel → Add Lakehouse) |
| **Data Agent can't find tables** | Verify the Lakehouse has been refreshed — open the SQL analytics endpoint and check tables |
| **Agent not appearing in M365 Copilot** | Wait a few seconds and refresh. If still missing, confirm Copilot extensibility is enabled by your M365 admin |
| **Agent doesn't return data** | Re-test the agent in the Fabric portal first. Ensure both tables are selected and instructions are saved |
| **Colleagues can't use shared agent** | Ensure they have access to both the Data Agent and the underlying Lakehouse data |
| **Response is paraphrased** | Update the publishing description to ask M365 Copilot to return results as-is |

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
| **Publish Data Agent to M365 Copilot** | [learn.microsoft.com](https://learn.microsoft.com/en-us/fabric/data-science/data-agent-microsoft-365-copilot) |
| **Manage Copilot agents (extensibility)** | [learn.microsoft.com](https://learn.microsoft.com/en-us/microsoft-365/admin/manage/manage-plugins-for-copilot-in-integrated-apps) |

---

## 🤝 Contributing

Found a bug or want to improve the guides? Open an issue or submit a PR. Screenshots for the `docs/images/` folder are especially welcome!

---

## 📄 License

This project is provided as-is for internal use. See your organization's policies for redistribution.
