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

### 2️⃣ Import the Notebook

1. Download the file **`fabric/contoso_sales_setup.ipynb`** from this repository to your computer
2. In your **Fabric workspace**, click **+ New Item** → **Import** → **Notebook**
3. Select the downloaded `contoso_sales_setup.ipynb` file and upload it
4. Once imported, the notebook will appear in your workspace — **open it**

> 💡 **Alternative:** If you prefer, you can create a blank notebook and copy-paste the cell contents from `contoso_sales_setup.ipynb` manually.

---

### 3️⃣ Attach the Lakehouse to the Notebook

1. In the opened notebook, look at the **left panel** (Explorer)
2. Click **"Add"** → **"Existing Lakehouse"**
3. Select **`contoso_sales`** from the list and confirm
4. You should now see the Lakehouse name in the left panel — this means the notebook will write data to it

---

### 4️⃣ Run All

1. Click **"Run All"** in the notebook toolbar
2. Wait **~1–2 minutes** for all cells to complete
3. You should see ✅ green checkmarks next to each cell

---

### 5️⃣ Verify

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
