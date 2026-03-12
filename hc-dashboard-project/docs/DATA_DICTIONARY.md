# 📖 Data Dictionary — Human Capital Dashboard

This document defines every field in the `Employee_Data` sheet.

---

## Table: Employee_Data

| # | Field | Data Type | Allowed Values | Notes |
|---|-------|-----------|----------------|-------|
| 1 | `Emp_ID` | Text | EMP0001 – EMP9999 | Unique identifier, never reuse |
| 2 | `Full_Name` | Text | Any | Format: First Last |
| 3 | `Gender` | Text | Male / Female | Case-sensitive for COUNTIF formulas |
| 4 | `Department` | Text | Operations, Finance, HR, Marketing, IT, Sales, Legal, R&D | Must match exactly for lookups |
| 5 | `Position_Level` | Text | Staff, Junior, Senior, Supervisor, Manager, Director | Ordered hierarchy low→high |
| 6 | `Employment_Type` | Text | Full-Time, Part-Time, Contract | Used in regional breakdown |
| 7 | `Join_Date` | Date | YYYY-MM-DD | Used to calculate tenure; must be Date type in Power BI |
| 8 | `Age` | Integer | 18–65 | Age as of current calendar year |
| 9 | `Education` | Text | High School, Diploma, Bachelor, Master, PhD | Ordered hierarchy low→high |
| 10 | `Region` | Text | Jakarta, Surabaya, Bandung, Medan, Bali, Makassar, Semarang | Maps to geographic location |
| 11 | `Salary` | Integer | > 0 | Monthly gross salary in IDR (Indonesian Rupiah) |
| 12 | `Performance_Score` | Decimal | 1.0 – 5.0 | Annual review rating; 1=Poor, 5=Excellent |
| 13 | `Tenure_Years` | Integer | 0–45 | = Current Year − Join Year |
| 14 | `Status` | Text | Active / Inactive | Active = current employee; Inactive = resigned/terminated |

---

## Notes for Data Entry

- All text fields are **case-sensitive** — use consistent casing as shown above
- Do not leave any field blank in rows you add; use "N/A" if unknown
- `Join_Date` must be a proper date format (not plain text) for Power BI to parse correctly
- `Salary` is in **IDR (Indonesian Rupiah)** — adjust currency label in Power BI if needed

---

*Last updated: 2024 | Human Capital Dashboard v1.0*
