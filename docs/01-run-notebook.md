# 📓 Step 1: Create the Lakehouse & Sample Data

This guide walks you through creating a Fabric Lakehouse and populating it with sample Contoso sales data using a notebook.

---

## ✅ Prerequisites

- A **Microsoft Fabric workspace** with capacity (F2+ or trial)
  - Don't have one? → [Create a workspace](https://learn.microsoft.com/en-us/fabric/fundamentals/create-workspaces)
  - Need a trial? → [Start a Fabric trial](https://learn.microsoft.com/en-us/fabric/fundamentals/fabric-trial)
- **Member** or **Admin** role in the workspace

> 📖 **New to Fabric?** See the [Lakehouse tutorial](https://learn.microsoft.com/en-us/fabric/data-engineering/tutorial-build-lakehouse) on Microsoft Learn for an end-to-end walkthrough.

---

## 📝 Steps

### 1️⃣ Create a Lakehouse

1. Go to your **Fabric workspace**
2. Click **+ New Item**
3. Select **Lakehouse**
4. Name it **`contoso_sales`**
5. Click **Create**

---

### 2️⃣ Create a Notebook

1. Go to your **Fabric workspace**
2. Click **+ New Item**
3. Select **Notebook**

---

### 3️⃣ Attach the Lakehouse

1. In the notebook, look at the **left panel**
2. Click **"Add Lakehouse"**
3. Select **`contoso_sales`** from the list
4. The Lakehouse is now connected and ready to use in your notebook code

---

### 4️⃣ Import the Notebook Content

You have two options:

**Option A — Copy-paste cells:**

1. Open the notebook you just created
2. Open the file `fabric/contoso_sales_setup.ipynb` from this repository
3. Copy-paste the cells from the setup notebook into your Fabric notebook

**Option B — Direct import (if supported):**

1. In your Fabric workspace, click **+ New Item** → **Import** → **Notebook**
2. Upload the file `fabric/contoso_sales_setup.ipynb` from this repository
3. Once imported, open the notebook and attach the `contoso_sales` Lakehouse (see Step 3)

---

### 5️⃣ Run All

1. Click **"Run All"** in the notebook toolbar
2. Wait **~1–2 minutes** for all cells to complete
3. You should see ✅ green checkmarks next to each cell

---

### 6️⃣ Verify

1. Go back to your **Fabric workspace**
2. Open the **`contoso_sales`** Lakehouse
3. Click on the **SQL analytics endpoint**
4. Confirm you see these two tables:
   - ✅ **`products`**
   - ✅ **`sales_transactions`**

> 💡 **Tip:** You can click on each table and preview the data to make sure it looks correct.

---

## 🎉 What You've Built

You now have a **Fabric Lakehouse** loaded with:

| Table | Records | Description |
|-------|---------|-------------|
| `products` | 50 | Product catalog with categories, prices, and descriptions |
| `sales_transactions` | 500 | Sales transactions with regions, reps, quantities, and amounts |

This sample data is ready for the **Data Agent** to query using natural language!

---

## ➡️ Next Step

Continue to **[Step 2: Create the Fabric Data Agent →](02-create-data-agent.md)**
