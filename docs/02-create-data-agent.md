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
3. Name it **`contoso_sales_agent`**
4. Click **Create**

---

### 2️⃣ Add Data Source

1. In the Data Agent configuration, click **"Add data source"**
2. Select your **`contoso_sales`** Lakehouse
3. Select **both tables**:
   - ✅ **`products`**
   - ✅ **`sales_transactions`**

---

### 3️⃣ Add Instructions

1. In the **"Instructions"** section of the Data Agent, paste the following meta-prompt:

```text
You are a sales analytics assistant for Contoso. You help business users understand sales performance by querying the products and sales_transactions tables.

Key relationships:
- sales_transactions.ProductID joins to products.ProductID
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

### 5️⃣ Publish the Agent

1. Click **"Publish"** to make the Data Agent available
2. This makes it connectable from **Copilot Studio** in the next step

> ⚠️ **Important:** The agent must be published before it can be used as a connector in Copilot Studio.

---

## 🎉 What You've Built

You now have a **Fabric Data Agent** that can:

- 🗣️ Answer **natural language questions** about your sales data
- 🔍 Automatically generate **SQL queries** behind the scenes
- 📊 Return **business-friendly results** with numbers and context

No SQL knowledge required — just ask questions in plain English!

---

## ➡️ Next Step: Create the Copilot Studio Agent

You have **two options** — choose the one that fits your needs:

| Path | Guide | Time | Best For |
|------|-------|------|----------|
| **🅰️ Import solution** (recommended) | [📦 Import Guide](../copilot-studio/import-guide.md) | ~5 min | Quick setup — import the `.zip`, set 2 environment variables, done |
| **🅱️ Build manually** | [💬 Manual Guide](03-create-copilot-studio.md) | ~10 min | Learning the process or customizing the agent from scratch |
