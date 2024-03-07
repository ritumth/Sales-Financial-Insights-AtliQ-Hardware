# Sales-Insights-AtliQ-Hardware |Power BI|SQL|Excel|

This is a project I replicated from Codebasics PowerBi Youtube playlist. You can find the link of the playlist below.

Codebasics Youtube Playlist-Link
Live Report -Link

**Problem statement**

AtliQ Hardware is a company which supplies computer hardware and peripherals to many clients across India;
The company has a head office in Dehli and regional offices throughout India.
Business Issue The sales director is facing a lot of challenges such as: The marketing is growing dynamically and then he’s struggling in terms of tracking the sales, needing more accurate insights about the company sales, and then take the necessary decisions.

**Solution**
Sales director of the AltiQ hardware, decided to build a PowerBI Dashboard for converting the data into visual representation to make data driven decisions. So, he hired a team of data people to complete this task.

**AIMS Grid**
By using the AIMS grid project management tool, we made sure what are the purpose, stakeholder, end result and success criteria of our project.
![AIMSPNG](https://github.com/ritumth/Sales-Financial-Insights-AtliQ-Hardware/assets/148063366/13acfd2c-f0c6-48b6-943a-9bd6e97e08e6)

** Steps Followed in this project**
 
Performed a High level analysis of data in SQL to get better understanding over the data.
Connected the SQL data set to PowerBI.
Performed ETL and data cleaning on the imported data.
In the currency there were two types of currencies in transactions, performed currency conversion to make all the currency type same
Created measure for needs and used them for creating visuals in PowerBi.
After the initial report reviewed by the stakeholders, made changes to the report based on the review commends.

I used SQL queries in MySQL Workbench to take a look into the data and Power BI for ETL and visualizations to create the insights.

**  Data Analysis Using SQL code:-**

Show all customer records

SELECT * FROM customers;

Show total number of customers SELECT count(*) FROM customers;

Show transactions for Chennai market (market code for chennai is Mark001

`SELECT * FROM transactions where market_code='Mark001';`
Show distrinct product codes that were sold in chennai

`SELECT distinct product_code FROM transactions where market_code='Mark001';`
Show transactions where currency is US dollars

SELECT * from transactions where currency="USD"`
Show transactions in 2020 join by date table

`SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`
Show total revenue in year 2020,

`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
Show total revenue in year 2020, January Month,

`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`
Show total revenue in year 2020 in Chennai

`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`



![Sales Finance_Insights](https://github.com/ritumth/Sales-Financial-Insights-AtliQ-Hardware/assets/148063366/764046ed-f17c-484e-8a60-3cbfd0108e9f)
