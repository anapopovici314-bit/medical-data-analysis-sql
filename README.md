# 🏥 Medical Data Analysis Project

A complete data analysis project combining **MS Excel** (for initial data cleaning and pivot tables) and **Google BigQuery / SQL** (for advanced queries and metric extraction) on a medical dataset.

---

## 🛠️️ Tools & Technologies Used
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
    `project_name.medical_project.hospital_data`
GROUP BY 
    Condition
ORDER BY 
    avg_cost DESC;
