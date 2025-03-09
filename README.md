# data-analytics-portfolio
SQL Data Analysis Project

Introduction

This project showcases an SQL-based data analysis conducted to extract insights from a structured dataset. The objective was to perform data cleaning, aggregation, and query optimization to generate meaningful results for business decision-making.

Project Overview

Project Name: SQL Data Analysis

Tools Used: MySQL

Data Source: Hospital Dataset

Key Focus Areas: Data cleaning, querying, aggregation, and reporting

Data Cleaning Process

Handling Missing Values:

Used IS NULL and COALESCE() to detect and replace missing values.

Removing Duplicates:

Utilized DISTINCT to remove redundant data entries.

Data Type Standardization:

Ensured column data types were appropriate (e.g., dates in DATE format, numerical values in INT/FLOAT).

Normalization:

Structured data into separate tables to reduce redundancy using JOIN operations.

Data Validation:

Used constraints (PRIMARY KEY, FOREIGN KEY, CHECK) to enforce data integrity.

SQL Queries and Analysis

Key Queries Executed:

Extracting Unique Room and Admission Data:

SELECT DISTINCT Room_no, Date_of_Adm, Hosp_name, Med_condition, Amt, Disch_date
FROM hospitaldataset
WHERE Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31';

Hospital and Doctor Pairing:

SELECT DISTINCT h.Hosp_name, d.Doc_name
FROM hospitaldataset h
LEFT JOIN hospitaldataset d ON h.Room_no = d.Room_no
WHERE h.Hosp_name IS NOT NULL AND d.Doc_name IS NOT NULL;

Counting Unique Attributes:

SELECT COUNT(DISTINCT Hosp_name) AS Total_Unique_Hospital,
       COUNT(DISTINCT Doc_name) AS Total_Unique_Doc,
       COUNT(DISTINCT Med_condition) AS Total_Unique_Condition
FROM hospitaldataset;

Insights and Findings

Identified the most frequently occurring medical conditions in different hospitals.

Analyzed the distribution of medical expenses among patients.

Established relationships between doctors and hospitals.

Determined the average duration of patient stays in different hospitals.

Recommendations

Data Integrity: Hospitals should enforce constraints to maintain consistency.

Efficient Storage: Data normalization should be implemented to improve query performance.

Advanced Reporting: Integrate Power BI for more in-depth visual analytics.

Conclusion

This SQL project demonstrates how structured query language (SQL) can be used to clean, process, and extract valuable insights from hospital data. The findings provide actionable recommendations to improve hospital data management and reporting systems. This project serves as a strong portfolio piece showcasing database querying and data analysis skills.



