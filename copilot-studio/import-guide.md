# 📦 Importing the Copilot Studio Solution

This guide explains how to import a pre-built Copilot Studio solution instead of creating the agent manually.

---

## 📁 What the Solution .zip Contains

The Copilot Studio solution package includes:

- The **Contoso Sales Assistant** agent definition
- Configured **topics**, **instructions**, and **conversation flows**
- Placeholder connection reference for the **Fabric Data Agent**

> ⚠️ **Note:** The `.zip` file will be added to this folder once the solution is built. If you're following the **step-by-step guide**, you can skip this and **[build manually instead](../docs/03-create-copilot-studio.md)**.

---

## 📝 How to Import

### 1️⃣ Open Copilot Studio

1. Go to [https://copilotstudio.microsoft.com](https://copilotstudio.microsoft.com)
2. Select your **environment**

### 2️⃣ Import the Solution

1. Go to **Solutions** (left navigation)
2. Click **Import**
3. Select the **`.zip`** file from this folder
4. Follow the on-screen prompts to complete the import

### 3️⃣ Reconnect the Fabric Data Agent

The Fabric Data Agent connection is **environment-specific** and will not carry over from the export. You need to reconnect it manually:

1. Open the imported **Contoso Sales Assistant** agent
2. Follow **[Step 4 of the Copilot Studio guide](../docs/03-create-copilot-studio.md)** to connect your Fabric Data Agent

> 💡 **Tip:** Make sure you have already completed **[Step 1](../docs/01-run-notebook.md)** (Lakehouse) and **[Step 2](../docs/02-create-data-agent.md)** (Data Agent) before reconnecting.

### 4️⃣ Test & Publish

1. Use the **Test pane** to verify the agent works correctly
2. **Publish** to Teams when ready

---

## ❓ When to Use This vs. the Manual Guide

| Approach | Best For |
|----------|----------|
| **Import solution** | Quick setup when you already have the `.zip` file |
| **Manual guide** | Learning the process, customizing the agent, or when no `.zip` is available |

For the full manual walkthrough, start at **[Step 1: Create the Lakehouse & Sample Data](../docs/01-run-notebook.md)**.
