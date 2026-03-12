# 📊 Human Capital Analytics Dashboard

> A comprehensive workforce monitoring system built with **Microsoft Excel** and **Power BI** to help HR teams and management understand workforce composition, employee trends, and workforce distribution.

---

## 🗂️ Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Quick Start](#quick-start)
- [Excel Workbook Guide](#excel-workbook-guide)
- [Power BI Setup](#power-bi-setup)
- [Data Dictionary](#data-dictionary)
- [DAX Measures Reference](#dax-measures-reference)
- [Dashboard Screenshots](#dashboard-screenshots)
- [Contributing](#contributing)
- [License](#license)

---

## 📌 Project Overview

The **Human Capital Analytics Dashboard** is a data-driven HR reporting solution designed to:

| Goal | Description |
|------|-------------|
| 👥 Monitor Workforce | Track active headcount, gender mix, employment type |
| 📈 Analyze Trends | Visualize year-over-year headcount growth and attrition |
| 🗺️ Regional View | Understand workforce distribution across office regions |
| 🏢 Org Structure | Breakdown by department, position level, and education |
| 💡 HR Decisions | Support data-driven workforce planning with KPIs |

**Tools Used:** Microsoft Excel 2016+ · Power BI Desktop (Free) · Git / GitHub

---

## ✨ Features

- ✅ 200-record sample employee dataset (fully editable)
- ✅ Auto-calculated KPI cards (Total Employees, Active, Avg Salary, etc.)
- ✅ Department summary with headcount, salary, and performance
- ✅ Headcount trend table (2015–2024) with embedded line chart
- ✅ Regional distribution with gender and employment-type breakdown
- ✅ Position-level salary range and age bracket analysis
- ✅ Built-in Power BI step-by-step setup guide (inside the Excel file)
- ✅ Full data dictionary / field glossary sheet

---

## 📁 Project Structure

```
human-capital-dashboard/
│
├── README.md                         ← You are here
├── .gitignore                        ← Excludes temp/lock files
│
├── data/
│   └── Human_Capital_Dashboard.xlsx  ← Main Excel workbook (all sheets)
│
├── powerbi/
│   └── HC_Dashboard.pbix             ← Power BI report file (after build)
│
├── docs/
│   ├── SETUP_GUIDE.md               ← Detailed Power BI setup instructions
│   ├── DATA_DICTIONARY.md           ← All field definitions
│   └── DAX_MEASURES.md              ← All DAX formulas reference
│
└── assets/
    └── screenshots/                  ← Dashboard preview images
```

---

## 🚀 Quick Start

### Prerequisites

| Tool | Version | Download |
|------|---------|----------|
| Microsoft Excel | 2016 or newer | office.com |
| Power BI Desktop | Latest (Free) | powerbi.microsoft.com/downloads |
| Git | Any | git-scm.com |
| GitHub Account | Free | github.com |

### 1. Clone This Repository

```bash
# Clone via HTTPS
git clone https://github.com/YOUR-USERNAME/human-capital-dashboard.git

# Navigate into the project
cd human-capital-dashboard
```

### 2. Open the Excel File

```
data/Human_Capital_Dashboard.xlsx
```

Open in Excel → replace sample data in `Employee_Data` sheet with your real HR data.

### 3. Connect to Power BI

See full instructions in [Power BI Setup](#power-bi-setup) below, or open the `PowerBI_Setup_Guide` sheet inside the Excel workbook.

---

## 📗 Excel Workbook Guide

The workbook contains **7 color-coded sheets**:

| Sheet Tab | Color | Purpose |
|-----------|-------|---------|
| `Employee_Data` | 🔵 Navy | Raw employee records — **edit your data here** |
| `Summary_KPI` | 🔵 Blue | Auto-calculated KPIs & department summary |
| `Headcount_Trend` | 🟢 Green | Year-by-year headcount growth (2015–2024) |
| `Regional_Distribution` | 🟣 Purple | Workforce breakdown by office region |
| `Position_Salary` | 🟡 Gold | Salary bands by level & age bracket analysis |
| `PowerBI_Setup_Guide` | 🔴 Red | Click-by-click Power BI instructions |
| `Documentation` | ⚫ Gray | Field glossary / data dictionary |

### Replacing Sample Data

1. Open `Employee_Data` sheet
2. Delete rows 2–201 (keep row 1 headers!)
3. Paste your real employee data, matching the column order:

```
Emp_ID | Full_Name | Gender | Department | Position_Level |
Employment_Type | Join_Date | Age | Education | Region |
Salary | Performance_Score | Tenure_Years | Status
```

4. All `Summary_KPI`, `Regional_Distribution`, and other formula sheets **update automatically**.

---

## 📊 Power BI Setup

### Step 1 — Install Power BI Desktop
1. Go to **https://powerbi.microsoft.com/downloads**
2. Click **"Download free"** → run the `.msi` installer
3. Sign in with your Microsoft / Office 365 account

### Step 2 — Load the Excel File
1. Open Power BI Desktop → **Home → Get Data → Excel Workbook**
2. Browse to `data/Human_Capital_Dashboard.xlsx` → **Open**
3. In the Navigator, **check all sheets** → click **"Transform Data"**

### Step 3 — Power Query Cleanup
In Power Query Editor:

| Column | Action |
|--------|--------|
| `Join_Date` | Transform → Data Type → **Date** |
| `Salary` | Transform → Data Type → **Whole Number** |
| `Age`, `Tenure_Years` | Transform → Data Type → **Whole Number** |
| `Performance_Score` | Transform → Data Type → **Decimal Number** |

Click **Home → Close & Apply**

### Step 4 — Add DAX Measures
See full list in [DAX Measures Reference](#dax-measures-reference).

### Step 5 — Build Visuals

| Visual | Type | Fields |
|--------|------|--------|
| Total Employees | Card | Measure: Total Employees |
| Active Rate | Card | Measure: Active % |
| Headcount by Dept | Clustered Bar | Axis: Department, Value: Total Employees |
| Gender Split | Pie Chart | Legend: Gender, Value: Total Employees |
| Regional Map | Map / Filled Map | Location: Region, Value: Total Employees |
| Headcount Over Time | Line Chart | Axis: Join_Date (Year), Value: Total Employees |
| Performance Table | Table | Dept, Avg Salary, Avg Performance, Headcount |

### Step 6 — Add Slicers (Filters)
Insert slicers for: `Department` · `Region` · `Gender` · `Year` · `Employment_Type`

### Step 7 — Publish
1. **Home → Publish** → select your workspace
2. Go to **app.powerbi.com** → find your dashboard
3. Set **Scheduled Refresh** under Dataset Settings

---

## 📖 Data Dictionary

| Field | Type | Values / Format |
|-------|------|-----------------|
| `Emp_ID` | Text | EMP0001 – EMP9999 |
| `Full_Name` | Text | First Last |
| `Gender` | Text | Male / Female |
| `Department` | Text | Operations, Finance, HR, Marketing, IT, Sales, Legal, R&D |
| `Position_Level` | Text | Staff → Junior → Senior → Supervisor → Manager → Director |
| `Employment_Type` | Text | Full-Time / Part-Time / Contract |
| `Join_Date` | Date | YYYY-MM-DD |
| `Age` | Integer | 18 – 65 |
| `Education` | Text | High School / Diploma / Bachelor / Master / PhD |
| `Region` | Text | Jakarta, Surabaya, Bandung, Medan, Bali, Makassar, Semarang |
| `Salary` | Integer | Monthly gross in IDR |
| `Performance_Score` | Decimal | 1.0 (Poor) – 5.0 (Excellent) |
| `Tenure_Years` | Integer | Years since Join_Date |
| `Status` | Text | Active / Inactive |

Full details in [docs/DATA_DICTIONARY.md](docs/DATA_DICTIONARY.md)

---

## 🧮 DAX Measures Reference

```dax
-- Headcount
Total Employees = COUNTROWS(Employee_Data)

Active Employees = 
    CALCULATE(COUNTROWS(Employee_Data), Employee_Data[Status] = "Active")

Attrition Rate = 
    1 - DIVIDE([Active Employees], [Total Employees])

Active % = 
    DIVIDE([Active Employees], [Total Employees], 0)

-- Salary
Avg Salary = AVERAGE(Employee_Data[Salary])

Total Salary Cost = SUM(Employee_Data[Salary])

-- Performance
Avg Performance = AVERAGE(Employee_Data[Performance_Score])

-- Demographics
Avg Age = AVERAGE(Employee_Data[Age])

Avg Tenure = AVERAGE(Employee_Data[Tenure_Years])

-- Gender
Male Count = 
    CALCULATE([Total Employees], Employee_Data[Gender] = "Male")

Female Count = 
    CALCULATE([Total Employees], Employee_Data[Gender] = "Female")

Gender Ratio = DIVIDE([Male Count], [Female Count], 0)
```

Full reference in [docs/DAX_MEASURES.md](docs/DAX_MEASURES.md)

---

## 🤝 Contributing

1. Fork this repository
2. Create a feature branch: `git checkout -b feature/add-new-visual`
3. Commit changes: `git commit -m "Add turnover rate visual"`
4. Push: `git push origin feature/add-new-visual`
5. Open a Pull Request

---

## 📄 License

This project is released under the **MIT License** — free to use, modify, and distribute.

---

*Built for HR Analytics — Human Capital Dashboard v1.0*
