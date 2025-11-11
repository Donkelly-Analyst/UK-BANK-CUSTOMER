# **UK-BANK-CUSTOMERS**

## *Table of Content*

- [Project Overveiw](#poject-overveiw)
- [Data Sources](#Data-Sources)
- [Sample Preview](#Sample-Preview)
- [Tools](#tools)
- [Data Cleaning-Preparation](#data-Cleaning-Preparation)
- [Exploration Data Analysis](Exploration-Data-Analysis)
- [Data Analysis](Data-Analysis)
- [Key Insights](Key-Insights)
- [Recommendations](Recommendations)
- [Limitations]( Limitations)



### *Project Overveiw*

The UK Bank Customer Dataset includes columns like age, income, balance, and account type of bank users and so on. This helps analysts understand customer behavior, predict trends, and improve banking services by turning raw financial data into meaningful insights about how people manage money.


<img width="1313" height="769" alt="Screenshot 2025-11-10 191620" src="https://github.com/user-attachments/assets/fbe86c6a-5f86-42fc-a597-591ecc54b13f" />


<img width="1330" height="759" alt="Screenshot 2025-11-10 192231" src="https://github.com/user-attachments/assets/8ee0d667-341a-4905-be82-47f6187b8a9c" />





### *Data Sources*

The primary dataset used for this analysis is the "UK-BANK-CUSTOMER.CSV" file, containing details about the customers behaviou




### *Column headers Sample Preview*

|CUSTOMER_ID|NAME|SURNAME|GENDER|AGE|REGION|JOB_CLASSIFICATION|DATE_JOINED|BALANCE|
|-----------|----|-------|------|---|------|------------------|-----------|-------|


### *Tools*

- Excel - Data Cleaning
  - [Download here](https://Microsoft.com)
- MY SQL - Data Analysis
- Power BI - Creating Reports


  ### *Data Cleaning/Preparation*

1. Performed in Excel
2. Promoted Headers of the dataset
3. Data Loading and inspection
4. Removed missing or invalid values 
5. Filtered Rows
6. Added Additional columns
7. Merged Queries


###  *Exploration Data Analysis*

This analysis is to acquire valuable insights and a 
comprehensive understanding of the behavior, preferences and patterns 
exhibited by customers within the United Kingdom banking sector.  
Through a detailed examination of various factors, we aim to uncover key 
trends and dynamics that can contribute to a deeper appreciation of the 
customer landscape, ultimately providing valuable information for 
informed decision-making within the UK banking industry.


### *Data Analysis*

```SQL Codes
SELECT *
FROM [UK Bank Customers]

---Total customers by age group

SELECT (age) As age_group, COUNT(Customer_ID) AS total_customers
FROM [UK Bank Customers]
GROUP BY age
Order by age DESC;

---Job classification by gender

SELECT Job_Classification, gender, COUNT(CUSTOMER_ID) AS total_customers
FROM [UK Bank Customers]
GROUP BY job_classification, gender;


--- Balance by job classification and region

SELECT job_classification, region, SUM(balance) AS total_balance
FROM [UK Bank Customers]
GROUP BY job_classification, region;

---Total customers by region

SELECT region, COUNT(Distinct(Customer_ID)) AS total_customers
FROM [UK Bank Customers]
GROUP BY region;

--- Total balance by age group

SELECT (age) AS age_group , SUM(balance) AS total_balance
FROM [UK Bank Customers]
GROUP BY age
ORDER BY AGE DESC;

---Total balance by region

SELECT region, SUM(balance) AS total_balance
FROM [UK Bank Customers]
GROUP BY region;

---Total balance by gender

SELECT gender, SUM(balance) AS total_balance
FROM [UK Bank Customers]
GROUP BY gender
ORDER BY total_balance DESC;

```

### *Key Insights*


- Smoking & Hypertension: Out of 568 smokers, 71.83% (408) have hypertension. Among non-smokers (1,417), 44.04% (624) have hypertension.
- Smokers have a significantly higher rate of hypertension compared to non-smokers.
- Family History & BP: 63.18% (652) of individuals with hypertension have a positive family history of high blood pressure.
- Normal BP: 5.09K sleep hours (39.73%)
- Prehypertension: 4.0K sleep hours (31.22%)
- Hypertension: 3.72K sleep hours (29.05%)
- Individuals with hypertension tend to sleep less than those with normal BP


### *Recommendations*

1. Target Smokers for Hypertension Screening
2. Create focused campaigns to monitor and manage BP among smokers, as they are at higher risk.
3. Family History-Based Risk Assessment
4. Use family history as a key screening variable for early intervention strategies.
5. Promote Sleep Hygiene Programs
6. Encourage better sleep patterns, especially among hypertensive and prehypertensive individuals, to improve cardiovascula


### *Limitations*


While cleaning the UK Bank Customer Dataset with Excel Power Query, I noticed some limitations. The process became slow when handling large data from multiple sources, and performing complex transformations, especially statistical cleaning, was quite challenging. These limitations made the overall data preparation process take more time than expected.


  














