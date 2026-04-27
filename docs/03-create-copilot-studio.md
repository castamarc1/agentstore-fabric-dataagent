# 💬 Step 3: Create the Copilot Studio Agent

This guide walks you through creating a Copilot Studio agent that connects to your Fabric Data Agent and is accessible via Microsoft Teams.

---

## ✅ Prerequisites

- Completed **[Step 2: Create the Fabric Data Agent](02-create-data-agent.md)** (published)
- **Microsoft 365 Copilot** license
- Access to **Copilot Studio** — [https://copilotstudio.microsoft.com](https://copilotstudio.microsoft.com)

---

## 📝 Steps

### 1️⃣ Open Copilot Studio

1. Go to [https://copilotstudio.microsoft.com](https://copilotstudio.microsoft.com)
2. Select your **environment** from the environment picker (top-right)

---

### 2️⃣ Create a New Agent

1. Click **"Create"** → **"New agent"**
2. Set the following:
   - **Name:** `Contoso Sales Assistant`
   - **Description:**
     > I help business users analyze Contoso sales data using natural language. Ask me about products, revenue, sales reps, and regional performance.
3. Click **Create**

---

### 3️⃣ Add Instructions

In the agent's **Instructions** section, paste the following:

```text
You are the Contoso Sales Assistant. Your role is to help business users get quick insights from sales data.

When users ask data questions, use the connected Fabric Data Agent to query the data.
When greeting users, briefly explain what you can help with.
If users ask questions outside of sales data, politely redirect them.

Example topics you can help with:
- Product performance and revenue analysis
- Regional sales comparisons
- Sales representative performance
- Time-based trends and seasonality
- Average order values and quantities
```

---

### 4️⃣ Connect the Fabric Data Agent

1. Go to the **"Actions"** or **"Agents"** tab in your Copilot Studio agent
2. Click **"Add an agent"**
3. Select **"Microsoft Fabric"**
4. **Authenticate** with your Fabric credentials
5. Select **`contoso_sales_agent`** from the list
6. Click **Confirm** to complete the connection

> ⚠️ **Important:** Make sure your Fabric Data Agent is **published** (Step 2, Step 5) before attempting this connection.

---

### 5️⃣ Test the Agent

Use the **Test pane** (right side) to verify everything works:

- 🟢 `"Hi, what can you help me with?"`
  — Should return a friendly greeting with capabilities
- 🟢 `"What were our top selling products?"`
  — Should query the Fabric Data Agent and return product data
- 🟢 `"Compare sales across regions"`
  — Should return a regional breakdown

> 💡 **Tip:** If the agent doesn't return data, check that the Fabric Data Agent connection is active in the Actions tab.

---

### 6️⃣ Publish to Teams

1. Go to the **"Channels"** section
2. Enable **"Microsoft Teams"**
3. Click **Publish**
4. Users can now find the agent in **Teams** by searching for **"Contoso Sales Assistant"**

> 💡 **Tip:** It may take a few minutes for the agent to appear in Teams after publishing.

---

## 🎉 What You've Built

You now have a **complete conversational AI agent** that:

- 💬 Business users can **chat with in Microsoft Teams**
- 📊 Provides **instant sales insights** from natural language questions
- 🔗 Connects to your **Fabric Lakehouse** data via the Data Agent
- 🚫 Requires **no SQL knowledge** — just ask in plain English!

**The entire solution — from data to conversational AI — was built without writing a single line of code.**

---

## 🏁 You're Done!

You have successfully built the complete Contoso Sales Analytics Agent:

| Component | What It Does |
|-----------|-------------|
| **Fabric Lakehouse** | Stores the sample sales data |
| **Fabric Data Agent** | Translates natural language → SQL → results |
| **Copilot Studio Agent** | Conversational UI in Teams |

> 📦 **Optional:** If you'd like to export/import the Copilot Studio solution, see the **[Import Guide](../copilot-studio/import-guide.md)**.
