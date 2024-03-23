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
## Which channel is most frequently used for transactions?
 ### (Code)
 SELECT TOP 1 store_type AS most_frequent_channel, COUNT(*) AS transaction_count FROM Transactions group by store_type order by COUNT(*) DESC
   ## (Result)
   
  ### ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/590f88bc-4d83-43ef-9a34-44571dd6b5c1)

 ## Object Result 
The analysis of transaction data from the 'Transactions' table reveals that the store type 'most_frequent_channel' is the most popular channel based on transaction count. The query identified the store type with the highest number of transactions, providing valuable insights into customer preferences and channel effectiveness. This information can be utilized by the retail store to prioritize marketing efforts, optimize inventory for the most frequented channels, and enhance overall business strategies to capitalize on the most popular sales channels and drive revenue growth.
      
# Business Object 2
## What is the count of Male and Female customers in the database?
 ### (Code)
SELECT Gender, COUNT(*) AS Count FROM Customers GROUP BY Gender;
 ## (Result)
 
## ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/4fe07b62-23db-4ede-8b94-e4f491a8275f)

## Object Result 
The analysis of customer data from the 'Customers' table provides a breakdown of gender distribution among customers. The query grouped customers by gender and counted the number of occurrences for each gender category. This data offers valuable insights into the demographic composition of the customer base, allowing for targeted marketing strategies and personalized promotions. Understanding the gender distribution can help the retail store tailor its product offerings, advertising campaigns, and customer engagement initiatives to better resonate with different customer segments, ultimately driving sales and enhancing customer satisfaction."

# Business Object 3
Q:-From which city do we have the maximum number of customers and how many?
 ### (Code)
SELECT TOP 1 city_code AS city_code , COUNT(*) AS number_customer FROM customers GROUP BY city_code ORDER BY COUNT(*) DESC;
 ## (Result)

 ## ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/648cc03c-181e-4a43-a364-240c17aac812)

 ## Object Result  
The analysis of customer data from the 'Customers' table reveals the city with the highest number of customers based on city_code. The query identified the city_code with the largest customer base, providing critical insights into regional customer distribution. This information can be leveraged to focus marketing efforts, tailor promotions, and optimize inventory to meet the demands of the most populated city. Understanding the geographic distribution of customers enables the retail store to implement targeted strategies, expand market reach, and enhance customer engagement to drive sales and foster brand loyalty in key regions.
    
# Business Object 4
Q:-How many sub-categories are there under the Books category?
  ### (Code)
 Select count(*) as no_subcategory from prod_cat_info where prod_cat = 'books'
  ## (Result)

  ## ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/1bb3ad41-baf0-4c7f-9d96-64df012db9a6)

  ## Object Result
 The query on 'prod_cat_info' indicates the count of subcategories under the 'books' category. This insight informs inventory and marketing 
 decisions, helping the retail store to diversify and optimize its 'books' product range based on customer preferences and demand.
  
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




