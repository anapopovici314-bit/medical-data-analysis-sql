# 🏥 Medical Data Analysis Project

A complete data analysis project combining **MS Excel** (for initial data cleaning and pivot tables) and **Google BigQuery / SQL** (for advanced queries and metric extraction) on a medical dataset.

---

## 🛠 Tools & Technologies Used
* **MS Excel:** Data validation, cleaning, formulas, and Pivot Tables for a quick overview.
* **Google BigQuery (SQL):** Cloud data storage and running complex queries for detailed analyses.

---

## 📊 Project Steps & SQL Queries

### 1. Top Medical Conditions and Average Cost
This query groups data by medical condition, calculates the total number of patients, and computes the average cost per condition, ordered from highest to lowest cost.
```sql
SELECT 
    Condition, 
    COUNT(Patient_ID) AS Total_Patients,
    ROUND(AVG(Cost), 2) AS avg_cost
FROM 
    `tidy-elf-498016-j2.med_project.med_table`
GROUP BY 
    Condition
ORDER BY 
    avg_cost DESC;
```

### 2. Gender Distribution Analysis
A check to see how patients and costs are distributed based on gender and medical condition.
```sql
SELECT 
    Condition,
    Gender,
    COUNT(Patient_ID) AS Total_Patients,
    ROUND(AVG(Cost), 2) AS Avg_Cost
FROM 
    `tidy-elf-498016-j2.med_project.med_table`
GROUP BY 
    Condition, Gender
ORDER BY 
    Condition ASC;
```

 ### 3.Length of Stay vs. Costs Correlation
 An analysis tracking the impact of the number of days spent in the hospital on average costs.
```sql
 SELECT 
    Length_of_Stay,
    COUNT(Patient_ID) AS Total_Patients,
    ROUND(AVG(Cost), 2) AS Avg_Cost
FROM 
    `tidy-elf-498016-j2.med_project.med_table`
GROUP BY 
    Length_of_Stay
ORDER BY 
    Length_of_Stay ASC;
```

### 4. Treatment Outcome Analysis
Patient counts grouped by their discharge status (e.g, Stable or Recovered).
```sql
SELECT 
    Outcome,
    COUNT(Patient_ID) AS total_patients
FROM 
    `tidy-elf-498016-j2.med_project.med_table`
GROUP BY 
    Outcome
ORDER BY 
    total_patients DESC;
```

ORDER BY 
    avg_cost DESC;
