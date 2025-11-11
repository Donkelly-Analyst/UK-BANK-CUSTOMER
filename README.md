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


- The bank serves a total of 4,014 customers, with men slightly outnumbering women.
- Young adults and early middle-aged customers make up the largest share and hold the highest balances.
- These groups represent the bank’s most financially active and valuable customer base.
- England leads in both customer count and total balance, followed by Scotland.
- Wales and Northern Ireland have fewer customers and lower balances, showing potential for expansion.
- Men dominate blue-collar jobs, while women are more in white-collar and professional roles; men hold higher total balances, but women show strong growth potential.

### *Recommendations*

1. Focus on middle-aged and young adult customers with tailored products like investments, mortgages, and savings incentives.
2. Expand engagement in Wales and Northern Ireland through financial education and community programs.
3. Improve digital banking access to reach underrepresented regions.
4. Provide targeted financial solutions for women, including business funding and investment packages.
5. Promote financial literacy and savings habits among younger customers.
6. Aim to build long-term loyalty and secure future account holders through consistent engagement.




### *Limitations*


While cleaning the UK Bank Customer Dataset with Excel Power Query, I noticed some limitations. The process became slow when handling large data from multiple sources, and performing complex transformations, especially statistical cleaning, was quite challenging. These limitations made the overall data preparation process take more time than expected.


  














