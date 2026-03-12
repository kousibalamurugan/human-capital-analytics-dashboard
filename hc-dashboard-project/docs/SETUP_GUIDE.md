# 🖥️ Power BI Setup Guide — Human Capital Dashboard

Complete step-by-step instructions to build the dashboard in Power BI Desktop.

---

## Prerequisites

- Microsoft Excel file: `data/Human_Capital_Dashboard.xlsx`
- Power BI Desktop installed (free): https://powerbi.microsoft.com/downloads
- Microsoft account (free or Office 365)

---

## Step 1 — Install Power BI Desktop

1. Go to **https://powerbi.microsoft.com/downloads**
2. Click **"Download free"**
3. Run the `.msi` installer → Accept license → Click Install
4. Launch Power BI Desktop
5. Sign in with Microsoft account (top-right corner)

---

## Step 2 — Load the Excel File

1. Click **Home tab → Get Data → Excel Workbook**
2. Browse to `data/Human_Capital_Dashboard.xlsx` → click **Open**
3. The **Navigator panel** opens — check these sheets:
   - ✅ Employee_Data
   - ✅ Summary_KPI
   - ✅ Headcount_Trend
   - ✅ Regional_Distribution
   - ✅ Position_Salary
4. Click **"Transform Data"** (opens Power Query Editor)

---

## Step 3 — Power Query Transformations

Inside Power Query Editor:

| Column | Step |
|--------|------|
| `Join_Date` | Click column → Transform → **Data Type → Date** |
| `Salary` | Click column → Transform → **Data Type → Whole Number** |
| `Age` | Click column → Transform → **Data Type → Whole Number** |
| `Tenure_Years` | Click column → Transform → **Data Type → Whole Number** |
| `Performance_Score` | Click column → Transform → **Data Type → Decimal Number** |

Click **Home → Close & Apply** when done.

---

## Step 4 — Create DAX Measures

1. In the Fields pane (right), right-click `Employee_Data` → **New Measure**
2. Paste each formula from [DAX_MEASURES.md](DAX_MEASURES.md) and press Enter
3. Repeat for all measures

---

## Step 5 — Build the Dashboard Page

### Page 1: Executive Summary

| Visual | Insert From | Configuration |
|--------|-------------|---------------|
| Card – Total Employees | Visualizations pane → Card | Value: `Total Employees` measure |
| Card – Active Employees | Visualizations pane → Card | Value: `Active Employees` measure |
| Card – Avg Salary | Visualizations pane → Card | Value: `Avg Salary` measure |
| Card – Avg Performance | Visualizations pane → Card | Value: `Avg Performance` measure |
| Clustered Bar – By Dept | Visualizations pane → Clustered Bar | Axis: Department, Value: Total Employees |
| Pie – Gender | Visualizations pane → Pie | Legend: Gender, Values: Total Employees |
| Line – Trend | Visualizations pane → Line | X-Axis: Join_Date (year level), Y: Total Employees |
| Map – Region | Visualizations pane → Map | Location: Region, Size: Total Employees |

### Page 2: Workforce Details

| Visual | Configuration |
|--------|---------------|
| Matrix / Table | Rows: Department, Columns: Position_Level, Values: Total Employees |
| Bar – Education | Axis: Education, Value: Total Employees |
| Scatter Plot | X: Avg Salary, Y: Avg Performance, Details: Department |
| Stacked Bar – Employment Type | Axis: Region, Values: Full-Time/Part-Time/Contract |

---

## Step 6 — Add Slicers

1. Insert → **Slicer** visual
2. Add slicers for: `Department` · `Region` · `Gender` · `Employment_Type`
3. For year: use `Join_Date` → **Hierarchy → Year** → change slicer style to "Between" for date range

---

## Step 7 — Format & Theme

1. **View tab → Themes → Executive** (or choose any theme)
2. Recommended brand colors:
   - Primary: `#1F3864` (navy)
   - Accent: `#2E75B6` (blue)
   - Highlight: `#C9A84C` (gold)
3. **View → Page view → Fit to page**
4. Right-click page tab → **Rename** to "Executive Summary"

---

## Step 8 — Publish to Power BI Service

1. **Home → Publish**
2. Select your workspace (e.g., "My Workspace")
3. Wait for upload → click the link to open in browser
4. Go to **app.powerbi.com** to see the live dashboard

### Set Up Scheduled Refresh

1. In Power BI Service, go to **Datasets**
2. Click **"..." → Settings** on your dataset
3. Expand **Scheduled Refresh → toggle ON**
4. Set frequency: Daily or Weekly
5. Click **Apply**

### Share With Team

1. Open your report → click **Share** (top right)
2. Enter colleague email addresses
3. Toggle **"Allow recipients to share"** if needed
4. Click **Send**

---

*Human Capital Dashboard v1.0 — Power BI Setup Guide*
