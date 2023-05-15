# sales-insight
# INTRODUCTION
# 1. Problem Statement
AtliQ Hardware is a company which supplies computer hardware and peripherals to many of clients such as Excel stores, Surge stories across India. AtliQ Hardware head office is situated in Delhi, India and they have many regional office throughout the India.

Challenges- Market is growing dynamically and Sales Director is facing issue in terms of tracking the Sales in this dynamically growth market and he is having issues with growth of his business, as overall sales was declining. He has regional managers for North India, South and Central India. Whenever he wants to get insight of these region he would call these people and on the phone regional manager give some insights to him.

Now Problem was that all these thing happening is verbal and there was no proof with facts that how his business is affected and which made him frustrated as he can see that overall sales is declining but when he ask regional manager, he is not getting complete picture of his business. And when he ask to give detail, they give lot of excel file and this AtliQ hardware is big business so to see insight clearly , he needs a dashboard to look at real data . And he will get proper insight and can take data driven decision to increase sales of his company.

# 2. Project planning with AIMS Grid and Data Discovery
AIMS Grid -is a project management tool and it has four component-

Purpose- to unlock sales insights that are not visible before for the sales team for decision support and automate them to reduced manual time spent in data gathering.

Stakeholders- are people who will involve in this project like sales director, marketing team, customer service team, data analytics team and IT.

End Result- An automated dashboard providing quick and latest sales insights in order to support data driven decision making.

Success Criteria-

→ Dashboard uncovering sales order insights with latest data available

→ Sales team able to take better decision and prove 10% cost savings of total spend.

→ Sales analyst stops data gathering manually in order to save 20% of their business time and reinvest it value added activity.

# 3. Data Exploration Using MySQL
The data has been downloaded and imported into MySQL. All the tables have been checked for corrections.

Observation 1- Sales Qty is in negative which is invalid and also currency is in USD ,so we need to convert it into INR as in finding insight it will be problematics(total sum of revenue)

Observation 2- Company is doing Sales in India and also might have done in New York and Paris for 1–2 time , so here we will remove it because right now company is doing business only in India so these data are not useful.

The following codes have been used in SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`

# 4. Data Cleaning and ETL

The Power BI has been connected to the MySQL database for loading the table into Power BI
After loading all the data have been cleaned using Power Query editor tool.

# 5. Building Dashboard 
The 3 dashboard has been built to sjhow the Key insights, profit analysis and performance insights

# Dasboard 1 : Key insights

![Key insights](https://github.com/Premnath1405/sales-insight/assets/128468794/4f40a8f3-e44e-458c-8c52-6849fcd50dde)


# Dashboard 2 : Profit analysis

![Profit analysis](https://github.com/Premnath1405/sales-insight/assets/128468794/0f502862-f47c-4ae1-9102-820084c48779)

# Dasboard 3 : Performance insights

![Performance insights](https://github.com/Premnath1405/sales-insight/assets/128468794/383cde4b-5f48-43fb-aa7f-3809364baa62)

# Final report
Based on the dashbaords insights, I have made some conclusions and recommendation that Sales Marketing team should/can consider making a sales strategy.

# Conclusions
Sales were rapidly decreasing in 2020 compared to 2019 by around 57.7%.
Highest revenue generated from Markets such as Delhi NCR, Mumbai, Ahmedabad, Bhopal, Nagpur, and so on.
Highest quantities sold in the Market such as Delhi NCR, Mumbai, Nagpur, Kochi, Ahmedabad, and so on.
Majority of the sales were takes place in the month of January followed by November and March.

# Recommendation
Make a new sales strategy for lucknow since its showing lowest revenue and negative profit margin and if possible so as for Surat and Bhubhaneshwar also.
try to increase sales quantity in Patna, Surat and Kanpur since they have lowest sales quantity.
start target campagin for Prod047 and Prod061 since they two are the most profitable and most selling products.
try to give special benefits to Electronics and Excel stores as they are most profitable customers.
make campgain strategy for mid year as they are showing high sales among other months.

# References
Inspiration : Codebasics Youtube channel



