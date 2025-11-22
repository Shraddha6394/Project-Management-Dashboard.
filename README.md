# Project Performance Dashboard (Excel)

This repository contains an interactive **Project Performance Dashboard** built in Microsoft Excel.  
The dashboard provides real-time visibility into task progress, deadlines, ownership, and remaining project duration—designed from a Business Analyst perspective.

---

## 📂 Project Files Included

| File | Description |
|---|---|
| `step-3-Project-Dashboard-prep.xlsx` | Main Excel file containing raw data, calculations, tables, and dashboard visuals |
| `activities` Table | Structured data source used across formulas and charts |

---

## 🎯 Objective

The goal of this dashboard is to help stakeholders:

- Track project activities  
- View task statuses and deadlines  
- Monitor overall project performance  
- Quickly identify delays and risks  
- Get a real-time KPI like “Days Remaining” based on current project status

---

## 🧾 Data Used

The dataset includes:

- Activity / Task  
- Responsible Owner  
- Category  
- Start Date  
- End Date  
- % Completion

All data is stored in a structured Excel Table named `activities`.

---

## 📊 Features of the Dashboard

### ⭐ Key Highlights

- Real-time dynamic metrics  
- Days Remaining KPI  
- Automatic evaluation based on Today’s Date  
- No negative KPI values  
- Color-coded visual indicators  
- Fully formula-driven (no VBA required)

### 📌 KPIs Included

- **Days Remaining until next upcoming task**
- **Number of completed tasks**
- **Total activities**
- **Task progress snapshot**
- **Upcoming vs overdue milestones**

---

## 🔢 Formula Logic

### **Days Remaining KPI**
To avoid negative KPI outputs and show meaningful results:

```excel
=IFERROR(
 MIN(FILTER(activities[End Date], activities[End Date] >= TODAY())) - TODAY(),
 0
)

