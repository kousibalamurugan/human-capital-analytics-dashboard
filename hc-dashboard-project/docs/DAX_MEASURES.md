# 🧮 DAX Measures Reference — Human Capital Dashboard

All measures to create in Power BI Desktop. To add a measure:
**Home tab → New Measure → paste formula → press Enter**

---

## Headcount Measures

```dax
Total Employees = 
    COUNTROWS(Employee_Data)

Active Employees = 
    CALCULATE(
        COUNTROWS(Employee_Data),
        Employee_Data[Status] = "Active"
    )

Inactive Employees = 
    CALCULATE(
        COUNTROWS(Employee_Data),
        Employee_Data[Status] = "Inactive"
    )

Active % = 
    DIVIDE([Active Employees], [Total Employees], 0)

Attrition Rate = 
    DIVIDE([Inactive Employees], [Total Employees], 0)
```

---

## Salary Measures

```dax
Avg Salary = 
    AVERAGE(Employee_Data[Salary])

Total Salary Cost = 
    SUM(Employee_Data[Salary])

Min Salary = 
    MIN(Employee_Data[Salary])

Max Salary = 
    MAX(Employee_Data[Salary])
```

---

## Performance Measures

```dax
Avg Performance = 
    AVERAGE(Employee_Data[Performance_Score])

High Performers = 
    CALCULATE(
        COUNTROWS(Employee_Data),
        Employee_Data[Performance_Score] >= 4.0
    )

High Performer % = 
    DIVIDE([High Performers], [Total Employees], 0)
```

---

## Demographic Measures

```dax
Avg Age = 
    AVERAGE(Employee_Data[Age])

Avg Tenure = 
    AVERAGE(Employee_Data[Tenure_Years])

Male Count = 
    CALCULATE([Total Employees], Employee_Data[Gender] = "Male")

Female Count = 
    CALCULATE([Total Employees], Employee_Data[Gender] = "Female")

Gender Ratio (M:F) = 
    DIVIDE([Male Count], [Female Count], 0)
```

---

## Department Measures

```dax
Dept Headcount = 
    CALCULATE([Total Employees], ALLEXCEPT(Employee_Data, Employee_Data[Department]))

Dept % of Total = 
    DIVIDE([Total Employees], CALCULATE([Total Employees], ALL(Employee_Data)), 0)
```

---

*Human Capital Dashboard v1.0*
