# 🤖 Step 2: Create the Fabric Data Agent

This guide walks you through creating a Fabric Data Agent that can answer natural language questions about your Contoso sales data.

---

## ✅ Prerequisites

- Completed **[Step 1: Create the Lakehouse & Sample Data](01-run-notebook.md)**
- Same **Fabric workspace** where you created the Lakehouse
- **Fabric Data Agent (preview)** must be enabled in your tenant
  - Your admin must enable **Copilot and Azure OpenAI features** in Tenant Settings → [Configure Data Agent tenant settings](https://learn.microsoft.com/en-us/fabric/data-science/data-agent-tenant-settings)
- Paid **F2+ capacity** (or P1+ with Fabric enabled) — the Data Agent is not available on trial capacity

> 📖 **Learn more:** [Create a Fabric Data Agent](https://learn.microsoft.com/en-us/fabric/data-science/how-to-create-data-agent) · [Data Agent end-to-end tutorial](https://learn.microsoft.com/en-us/fabric/data-science/data-agent-end-to-end-tutorial)

---

## 📝 Steps

### 1️⃣ Navigate to Data Agent

1. In your **Fabric workspace**, click **+ New Item**
2. Search for **"Data Agent"** (found under the **AI** section)
3. Name it **`Contoso Sales Analyst`**
4. Click **Create**

---

### 2️⃣ Add Data Source

1. In the Data Agent configuration, click **"Add data source"**
2. Select your **`ContosoSales`** Lakehouse
3. Select **both tables**:
   - ✅ **`Products`**
   - ✅ **`SalesTransactions`**

---

### 3️⃣ Add Instructions

1. In the **"Instructions"** section of the Data Agent, paste the following meta-prompt:

```text
You are a sales analytics assistant for Contoso. You help business users understand sales performance by querying the Products and SalesTransactions tables.

Key relationships:
- SalesTransactions.ProductID joins to Products.ProductID
- TotalAmount = Quantity × UnitPrice

When answering questions:
- Always use clear, business-friendly language
- Include specific numbers and percentages when possible
- If asked about trends, compare across time periods
- Common dimensions: Region, Category, SalesRep, TransactionDate
```

> 💡 **Tip:** These instructions help the Data Agent understand your data model and respond in a business-friendly way.

---

### 4️⃣ Test the Agent

Use the **built-in chat** pane to test the Data Agent with these sample questions:

- 🟢 `"What are the top 5 products by total revenue?"`
- 🟢 `"Show me sales by region"`
- 🟢 `"Which sales rep had the most transactions?"`
- 🟢 `"What is the average order value by product category?"`

> 💡 **Tip:** If results don't look right, double-check that both tables are selected and your instructions are saved.

---

### 5️⃣ Verify the Agent Works

Make sure the agent returns accurate results before publishing. Try a few different question types (aggregations, filters, comparisons) to confirm it handles your data well.

> 💡 **Tip:** Fix any issues now — once published to the M365 Copilot Agent Store, users will interact with the agent directly.

---

## 🎉 What You've Built

You now have a **Fabric Data Agent** that can:

- 🗣️ Answer **natural language questions** about your sales data
- 🔍 Automatically generate **SQL queries** behind the scenes
- 📊 Return **business-friendly results** with numbers and context

No SQL knowledge required — just ask questions in plain English!

---

## ➡️ Next Step

Continue to **[Step 3: Publish to the M365 Copilot Agent Store →](03-publish-to-agent-store.md)**
