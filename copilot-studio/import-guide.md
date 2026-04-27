# 📦 Step 3 (Path A): Import the Copilot Studio Solution

This guide explains how to import the pre-built Copilot Studio solution and configure it to connect to your Fabric Data Agent.

> 💡 **Prefer to build it yourself?** See the **[💬 Manual Guide (Path B)](../docs/03-create-copilot-studio.md)** instead.

---

## 📁 What the Solution Contains

The solution package (`ContosoDataAgent_1_0_0_13.zip`) includes:

- The **Contoso Sales Assistant** agent definition
- Configured **topics**, **instructions**, and **conversation flows**
- Two **environment variables** for connecting to your Fabric Data Agent:
  - `Data Agent Id` — the unique ID of your published Fabric Data Agent
  - `Workspace Id` — the ID of the Fabric workspace containing the Data Agent

---

## ✅ Prerequisites

Before importing, make sure you have:

1. ✅ **[Step 1: Create the Lakehouse & Sample Data](../docs/01-run-notebook.md)**
2. ✅ **[Step 2: Create the Fabric Data Agent](../docs/02-create-data-agent.md)** (must be **published**)
3. ✅ A **Microsoft 365 Copilot** license **or** a **Copilot Studio metered (PAYG)** plan — [Licensing](https://learn.microsoft.com/en-us/microsoft-copilot-studio/billing-licensing) · [Set up PAYG](https://learn.microsoft.com/en-us/microsoft-365/copilot/pay-as-you-go/setup)

You will need the **Data Agent ID** and **Workspace ID** — instructions to find them are below.

---

## 📝 How to Import

### 1️⃣ Find Your Workspace ID and Data Agent ID

You'll need these values during import. Here's how to find them:

**Workspace ID:**

1. Open the [Fabric portal](https://app.fabric.microsoft.com)
2. Navigate to your workspace (where you created the Lakehouse and Data Agent)
3. Look at the browser URL — it will look like:
   ```
   https://app.fabric.microsoft.com/groups/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/...
   ```
4. The GUID after `/groups/` is your **Workspace ID** — copy it

**Data Agent ID:**

1. In the same workspace, open your **`contoso_sales_agent`** Data Agent
2. Look at the browser URL — it will look like:
   ```
   https://app.fabric.microsoft.com/groups/.../dataagents/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
   ```
3. The GUID after `/dataagents/` is your **Data Agent ID** — copy it

> 💡 **Tip:** Save both IDs in a notepad — you'll need them in Step 3.

---

### 2️⃣ Import the Solution in Copilot Studio

1. Go to [https://copilotstudio.microsoft.com](https://copilotstudio.microsoft.com)
2. Select your **environment** (top-right picker)
3. In the left navigation, go to **Solutions**
4. Click **Import solution**
5. Click **Browse** and select `ContosoDataAgent_1_0_0_13.zip` from this folder
6. Click **Next** and follow the on-screen prompts

---

### 3️⃣ Configure the Environment Variables

During (or after) import, you'll be prompted to set two environment variables:

| Variable | Value | Where to Find It |
|----------|-------|-------------------|
| **Data Agent Id** | `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` | URL of the Data Agent in Fabric portal (after `/dataagents/`) |
| **Workspace Id** | `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` | URL of the workspace in Fabric portal (after `/groups/`) |

**If prompted during import:**
- Paste the values when asked and click **Next**

**If you need to update them after import:**
1. Go to **Solutions** → open the imported **Contoso Data Agent** solution
2. Find the **Environment Variables** section
3. Click each variable and set the **Current Value** with the IDs you copied
4. **Save** and **Publish All Customizations**

---

### 4️⃣ Test the Agent

1. In Copilot Studio, open the **Contoso Sales Assistant** agent
2. Use the **Test pane** (right side) to verify:
   - 🟢 `"What are the top 5 products by revenue?"` — should return data from your Lakehouse
   - 🟢 `"Show me sales by region"` — should return a regional breakdown
3. If the agent doesn't return data, double-check the environment variable values

---

### 5️⃣ Publish to Teams

1. Go to the **Channels** section of your agent
2. Enable **Microsoft Teams**
3. Click **Publish**
4. Users can now find **"Contoso Sales Assistant"** in Teams

> 💡 It may take a few minutes for the agent to appear in Teams after publishing.

---

## ❓ When to Use This vs. the Manual Guide

| Approach | Best For |
|----------|----------|
| **Import solution** (.zip) | Quick setup — just configure 2 environment variables |
| **[Manual guide](../docs/03-create-copilot-studio.md)** | Learning the process, customizing the agent from scratch |

---

## 🔧 Troubleshooting

| Issue | Solution |
|-------|----------|
| **Import fails** | Ensure you have System Administrator or System Customizer role in the Power Platform environment |
| **Agent doesn't return data** | Verify the Data Agent ID and Workspace ID environment variables are correct |
| **Can't find the Data Agent** | Make sure the Data Agent is **published** in Fabric and you're in the same tenant |
| **Environment variables not visible** | Open the solution → look under "Environment Variables" → update Current Value |
