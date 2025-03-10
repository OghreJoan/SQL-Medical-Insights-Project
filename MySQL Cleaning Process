SELECT distinct Room_no, Date_of_Adm, Hosp_name, Med_condition, Amt, Disch_date
FROM hospitaldataset
WHERE Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31';
SELECT DISTINCT h.Hosp_name, d.Doc_name
FROM hospitaldataset h
LEFT JOIN hospitaldataset d ON h.Room_no = d.Room_no
WHERE h.Hosp_name IS NOT NULL AND d.Doc_name IS NOT NULL;
SELECT DISTINCT Doc_name
FROM hospitaldataset; 
SELECT COUNT(DISTINCT Hosp_name) AS Total_Unique_Hospital, 
COUNT(DISTINCT Doc_name) AS Total_Unique_Doc,
COUNT(DISTINCT Med_condition) AS Total_Unique_Condition,
COUNT(DISTINCT Adm_type) AS Total_Unique_Adm_Type 
FROM hospitaldataset;
SELECT 
    Doc_name, 
    (SELECT COUNT(DISTINCT Doc_name) FROM hospitaldataset) AS Total_Doctors
FROM hospitaldataset
GROUP BY Doc_name;
SELECT SUM(Amt) AS Total_amt  
FROM hospitaldataset  
WHERE Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31';
SELECT Med_condition, SUM(Amt) AS Total_amt  
FROM hospitaldataset  
GROUP BY Med_condition;
CREATE VIEW `Med_condition/Total_Amt` AS     
 SELECT Med_condition, SUM(Amt) AS Total_amt  
FROM hospitaldataset  
GROUP BY Med_condition;  
SELECT Hosp_name, SUM(Amt) AS Total_amt  
FROM hospitaldataset  
GROUP BY Hosp_name;
ORDER BY Hosp_name desc;
SELECT Med_condition, MAX(Amt) AS Max_amt
FROM hospitaldataset
WHERE Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31'
GROUP BY Med_condition;
SELECT Doc_name, SUM(Amt) AS Total_amt  
FROM hospitaldataset  
GROUP BY Doc_name;
SELECT Hosp_name, Med_condition, Adm_type, SUM(Amt) AS Total_amt
FROM hospitaldataset
WHERE Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31'
GROUP BY Hosp_name, Med_condition, Adm_type
ORDER BY Hosp_name desc;
SELECT h.Room_no, p.Pat_name, p.Gender, h.Hosp_name, 
    h.Date_of_Adm, h.Med_condition, h.Disch_date, h.Amt, MAX(h.Amt) AS max_amt 
FROM hospitaldataset h
JOIN patientdataset p
ON p.Room_no = h.Room_no
WHERE h.Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31'  
GROUP BY  
     h.Room_no, p.Pat_name, p.Gender, h.Hosp_name, 
    h.Date_of_Adm, h.Med_condition, h.Disch_date, h.Amt
ORDER BY 1,2;
SELECT DISTINCT p.Pat_name, MAX(h.Amt) AS Max_amt , SUM(h.Amt) as Total_Amt
FROM hospitaldataset h
JOIN patientdataset p
ON p.Room_no = h.Room_no
WHERE h.Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31'   
GROUP BY  
     p.Pat_name
ORDER BY 1,2;
SELECT COUNT(DISTINCT Pat_name) AS Total_Unique_Patients
FROM patientdataset;
SELECT COUNT(*) AS Total_Cases
FROM hospitaldataset
WHERE Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31';
SELECT Med_condition, COUNT(*) AS Case_Count
FROM hospitaldataset
WHERE Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31'
GROUP BY Med_condition
ORDER BY Case_Count DESC;
SELECT Room_no, COUNT(*) AS Case_Count
FROM hospitaldataset
WHERE Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31'
GROUP BY Room_no
ORDER BY Case_Count DESC;
SELECT Med_condition, 
       AVG(DATEDIFF(Disch_date, Date_of_Adm)) AS Avg_Duration,
       MAX(DATEDIFF(Disch_date, Date_of_Adm)) AS Max_Duration
FROM hospitaldataset
WHERE Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31'
GROUP BY Med_condition
ORDER BY Max_Duration DESC;
SELECT p.Pat_name, h.Med_condition, h.Hosp_name, 
       DATEDIFF(h.Disch_date, h.Date_of_Adm) AS Stay_Duration
FROM hospitaldataset h
JOIN patientdataset p ON h.Room_no = p.Room_no
WHERE h.Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31'
ORDER BY Stay_Duration DESC
LIMIT 1;
SELECT h.Hosp_name, SUM(h.Amt) AS Total_Hospital_Billing
FROM hospitaldataset h
WHERE h.Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31'
GROUP BY h.Hosp_name
ORDER BY Total_Hospital_Billing DESC;
SELECT p.Pat_name, h.Hosp_name, SUM(h.Amt) AS Total_Billing
FROM hospitaldataset h
JOIN patientdataset p ON h.Room_no = p.Room_no
WHERE h.Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31'
GROUP BY p.Pat_name, h.Hosp_name
ORDER BY Total_Billing DESC
LIMIT 5;
SELECT h.Med_condition, 
       AVG(DATEDIFF(h.Disch_date, h.Date_of_Adm)) AS Avg_Stay_Duration,
       SUM(h.Amt) AS Total_Billing
FROM hospitaldataset h
WHERE h.Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31'
GROUP BY h.Med_condition
ORDER BY Total_Billing DESC;
SELECT h.Doc_name, h.Med_condition, SUM(h.Amt) AS Total_Billing
FROM hospitaldataset h
WHERE h.Date_of_Adm BETWEEN '2023-01-01' AND '2024-12-31'
GROUP BY h.Doc_name, h.Med_condition
ORDER BY Total_Billing DESC;

