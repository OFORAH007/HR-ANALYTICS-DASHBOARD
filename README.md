## HR Analytics Dashboard Project

This repository contains insights derived from an HR dataset visualized using a Power BI dashboard. The aim of this analysis is to uncover key HR metrics around employee attrition, age distribution, job satisfaction, departmental breakdowns, and education-related trends.

>  **Completed by:** Oforah Ivan Chukwudumeje  
>  **Tool used:** Tableau   
>  **Dataset:** Provided in  [HR Data.xlsx](https://github.com/user-attachments/files/21680144/HR.Data.xlsx)

>  **Time Taken:** 4 Days

---

<img width="2048" height="739" alt="Gemini_Generated_Image_382fgu382fgu382f" src="https://github.com/user-attachments/assets/22285101-c9e8-434f-ae80-641a1dc27e5f" />

##  Objective

To analyze employee attrition patterns and uncover actionable insights that help HR teams improve retention, understand workforce distribution, and evaluate job satisfaction across departments and roles.

---

##  Dashboard Highlights

###  Key Metrics
- **Total Employees:** 1,470  
- **Active Employees:** 1,233  
- **Attrition Count:** 237  
- **Attrition Rate:** 16%  
- **Average Age:** 37  

###  Attrition Overview
- **By Gender:**  
  - Male: 150  
  - Female: 87  
- **By Department:**  
  - Sales: 133 (56.12%)  
  - R&D: 92 (38.82%)  
  - HR: 12 (5.06%)  
- **By Age Group:**  
  Highest attrition in age group 25–34 (112 exits), particularly among males.

###  Education Field & Attrition
- **Top Fields by Attrition:**  
  - Life Sciences: 89  
  - Medical: 63  
  - Marketing: 35

###  Job Satisfaction Ratings
- Satisfaction scale: 1 (Low) to 4 (High)  
- Sales Executives had the highest count with lower satisfaction scores (especially rating 1 & 2).

###  Age Distribution
- Largest group of employees are in the **30–34** age range.
- Lowest representation among employees aged **over 55**.

---

<img width="2048" height="668" alt="Gemini_Generated_Image_67ziut67ziut67zi" src="https://github.com/user-attachments/assets/038eb2ee-919b-4fd4-9609-defa76df2cfa" />

##  Tools Used

- **Tableau** – for dynamic visualization and dashboard creation  
- **Excel** – for data preparation and transformation
- **SQL Database** - Data Extraction
- **Markdown** – to document and explain insights

---
##  Dataset Description

File: `[HR Data.xlsx](https://github.com/user-attachments/files/21680129/HR.Data.xlsx)`

- 39 columns including: `Attrition`, `Age Band`, `Department`, `Gender`, `Job Role`, `Job Satisfaction`, `Education Field`, `Total Working Years`, etc.  
- Clean and structured for business intelligence tools.

---

### SQL Code for ETL
```
Extracting All Employee Data
SELECT
  EmployeeID,
  Age,
  Gender,
  Department,
  JobRole,
  JobSatisfaction,
  EducationField,
  YearsAtCompany,
  Attrition
FROM
  Employees;
```
```
Calculating Attrition rate by Department

SELECT
  Department,
  COUNT(CASE WHEN Attrition = 'Yes' THEN 1 ELSE NULL END) AS AttritionCount,
  COUNT(EmployeeID) AS TotalEmployees,
  (COUNT(CASE WHEN Attrition = 'Yes' THEN 1 ELSE NULL END) * 1.0 / COUNT(EmployeeID)) * 100 AS AttritionRate
FROM
  Employees
GROUP BY
  Department
ORDER BY
  AttritionRate DESC;
```
```
Analyzing Attrition by Job role & Satisfaction 

SELECT
  JobRole,
  COUNT(CASE WHEN Attrition = 'Yes' THEN 1 ELSE NULL END) AS AttritionCount,
  COUNT(EmployeeID) AS TotalEmployees,
  AVG(JobSatisfaction) AS AverageJobSatisfaction
FROM
  Employees
GROUP BY
  JobRole
ORDER BY
  AttritionCount DESC;
```
##  Insights

1. **Sales department** has the highest attrition—more than half of all recorded exits.
2. **Male employees** contribute more to attrition across all age brackets.
3. **Job dissatisfaction** appears to be concentrated among Sales Executives and Lab Technicians.
4. **Younger professionals** (25–34) are more likely to leave, possibly due to career transitions or better opportunities.
5. **Life Sciences and Medical fields** record the highest attrition in terms of educational background.

<img width="1550" height="859" alt="HR Analytic" src="https://github.com/user-attachments/assets/cc82c0eb-b246-4c17-9ea4-86740ff019fd" />

---
 
##  Author & Contact

**Oforah Ivan Chukwudumeje**  
Data Analyst | HR & Sales Operations Analytics

📬 [LinkedIn](https://www.linkedin.com/in/oforah/) 
🌐 [My Portfolio Website](https://chukwudumejeoforah.carrd.co/)  

---

## 📘 License

This project is shared for educational and professional demonstration purposes only. Dataset is synthetic or anonymized and not representative of any real company.

