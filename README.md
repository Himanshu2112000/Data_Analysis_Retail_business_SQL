# Data_Analysis_Retail_business_SQL
A GitHub repository housing SQL scripts and queries tailored for retail business analytics. Includes database schemas, data manipulation scripts, and advanced SQL queries to optimize retail operations, sales analysis, and customer insights. Ideal for enhancing retail business intelligence and data-driven decision-making.

# Databases Used:
 # Customer 
 Houses a detailed customer database schema with fields including date of birth (DOB), customer ID, gender, and city. Provides SQL queries and scripts for comprehensive customer insights, segmentation, and 
 analytics to drive data-driven business decisions.

 # Transactions
 Dedicated to fetching and analyzing transactional data from a comprehensive table. The table encompasses essential fields like transaction ID, date, mode, store type, product sub-code, rate, taxes, total amount, 
 and return amount. This repository offers SQL queries and scripts tailored for extracting, processing, and interpreting transaction data. It aims to provide valuable insights into customer purchasing behavior, 
 product performance, and financial metrics, enabling businesses to make informed decisions and optimize sales strategies."

 # Prod_cat_info
 Retrieving and analyzing data from a product category table. The table includes key information such as product category, sub-category, and product sub-code. This repository offers SQL queries and scripts 
 designed to efficiently fetch and process this data. It aims to provide businesses with insights into product preferences, category trends, and customer purchasing behavior. By leveraging this repository, 
 organizations can better understand their product landscape and tailor their marketing and inventory strategies to meet customer demands effectively.
 
# Tools Used: SQL, SQL Server

# Business Needs: 
  The primary business objective is to gain insights into customer behavior using point-of-sale (POS) data from our retail store. Through comprehensive data analysis, we aim to uncover purchasing trends, product 
  preferences, and customer segmentation. This analysis will enable us to optimize inventory levels, tailor marketing campaigns, and enhance the overall shopping experience. By understanding customer behavior more deeply, we strive to make informed decisions that drive sales growth, increase profitability, and build stronger relationships with our customers."

# Business Object 1 
Q:-Which channel is most frequently used for transactions?
  (SQL Code (SSMS))
  
# Business Object 2
Q:-What is the count of Male and Female customers in the database?
   (SQL Code (SSMS))

# Business Object 3
Q:-From which city do we have the maximum number of customers and how many?
   (SQL Code (SSMS))
   -- SELECT * from Transactions;
   --SELECT TOP 1 store_type AS most_frequent_channel, COUNT(*) AS transaction_count
     FROM Transactions
     GROUP BY store_type
     ORDER BY COUNT(*) DESC
     
   (Result) 
   ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/590f88bc-4d83-43ef-9a34-44571dd6b5c1)

     
    
# Business Object 4
Q:-How many sub-categories are there under the Books category?
   (SQL Code (SSMS))
# Business Object 5
Q:-What is the maximum quantity of products ever ordered?
   (SQL Code (SSMS))

# Business Object 6
Q:-What is the net total revenue generated in categories Electronics and Books?
   (SQL Code (SSMS))
# Business Object 7
Q:-How many customers have >10 transactions with us, excluding returns?
   (SQL Code (SSMS))
# Business Object 8
Q:-What is the combined revenue earned from the "Electronics" & "Clothing"
categories, from "Flagship stores"?
  (SQL Code (SSMS))




