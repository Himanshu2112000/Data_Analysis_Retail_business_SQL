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
 ### -(Code)
 SELECT TOP 1 store_type AS most_frequent_channel, COUNT(*) AS transaction_count FROM Transactions group by store_type order by COUNT(*) DESC
   ## -(Result)
   
  ### ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/590f88bc-4d83-43ef-9a34-44571dd6b5c1)

 ## -(Object Result) 
The analysis of transaction data from the 'Transactions' table reveals that the store type 'most_frequent_channel' is the most popular channel based on transaction count. The query identified the store type with the highest number of transactions, providing valuable insights into customer preferences and channel effectiveness. This information can be utilized by the retail store to prioritize marketing efforts, optimize inventory for the most frequented channels, and enhance overall business strategies to capitalize on the most popular sales channels and drive revenue growth.
      
# Business Object 2
## What is the count of Male and Female customers in the database?
 ### -(Code)
SELECT Gender, COUNT(*) AS Count FROM Customers GROUP BY Gender;
 ## -(Result)
 
## ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/4fe07b62-23db-4ede-8b94-e4f491a8275f)

## -(Object Result) 
The analysis of customer data from the 'Customers' table provides a breakdown of gender distribution among customers. The query grouped customers by gender and counted the number of occurrences for each gender category. This data offers valuable insights into the demographic composition of the customer base, allowing for targeted marketing strategies and personalized promotions. Understanding the gender distribution can help the retail store tailor its product offerings, advertising campaigns, and customer engagement initiatives to better resonate with different customer segments, ultimately driving sales and enhancing customer satisfaction."

# Business Object 3
## From which city do we have the maximum number of customers and how many?
 ### -(Code)
SELECT TOP 1 city_code AS city_code , COUNT(*) AS number_customer FROM customers GROUP BY city_code ORDER BY COUNT(*) DESC;
 ## -(Result)

 ## ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/648cc03c-181e-4a43-a364-240c17aac812)

 ## -(Object Result)  
The analysis of customer data from the 'Customers' table reveals the city with the highest number of customers based on city_code. The query identified the city_code with the largest customer base, providing critical insights into regional customer distribution. This information can be leveraged to focus marketing efforts, tailor promotions, and optimize inventory to meet the demands of the most populated city. Understanding the geographic distribution of customers enables the retail store to implement targeted strategies, expand market reach, and enhance customer engagement to drive sales and foster brand loyalty in key regions.
    
# Business Object 4
## How many sub-categories are there under the Books category?
  ### -(Code)
 Select count(*) as no_subcategory from prod_cat_info where prod_cat = 'books'
  ## -(Result)

  ## ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/1bb3ad41-baf0-4c7f-9d96-64df012db9a6)

  ## -(Object Result)
 The query on 'prod_cat_info' indicates the count of subcategories under the 'books' category. This insight informs inventory and marketing 
 decisions, helping the retail store to diversify and optimize its 'books' product range based on customer preferences and demand.
  
# Business Object 5
## What is the maximum quantity of products ever ordered?
  ### -(Code)
  SELECT p.prod_cat, COUNT(qty) AS no_product_category FROM Transactions t JOIN prod_cat_info p ON t.prod_subcat_code = p.prod_sub_cat_code 
  GROUP BY p.prod_cat;
   ## -(Result)

 ## ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/84c446bd-3415-4088-aa69-1420805e2f91)

  ## -(Object Result)
 The query joins 'Transactions' with 'prod_cat_info' to count products by category. Grouped by product category (p.prod_cat), it provides 
 insights into the distribution of product categories based on the quantity of transactions. This analysis aids in understanding purchasing 
 patterns and helps optimize inventory for different product categories to enhance sales and customer satisfaction.

# Business Object 6
## What is the net total revenue generated in categories Electronics and Books?
   ### -(Code)
  select distinct sum(t.total_amt) as total_revenue,pc.prod_cat from Transactions t join prod_cat_info pc on t.prod_cat_code = 
  pc.prod_cat_code where pc.prod_cat in ('electronics','books') group by pc.prod_cat
   ## -(Result)
   
## ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/73ff53b2-6538-49d1-b5a0-1f43cbea1b20)

 ## -(Object Result)
The query calculates the total revenue for distinct product categories, specifically 'electronics' and 'books', by joining 'Transactions' with 'prod_cat_info' on matching product category codes. The results offer insights into revenue generated from these two product categories individually. This analysis assists in evaluating the performance of 'electronics' and 'books' segments and guiding targeted marketing and inventory strategies to optimize sales and profitability
 
   
# Business Object 7
## How many customers have >10 transactions with us, excluding returns?
  ### -(Code)
select  cust_id, count(cust_id) as no_trans_by_customer from Transactions where total_amt > 0 group by cust_id
having count(*) > 10
   ## -(Result)

## ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/0cf64ce9-3f24-4353-86e0-dddd7395dddd)

 ## -(Object Result) 
The query identifies customers with more than 10 transactions where the total amount spent is greater than zero. It counts the number of transactions (no_trans_by_customer) for each customer (cust_id) and filters the results to focus on loyal or frequent customers. This analysis provides insights into customer behavior and purchasing frequency, aiding in customer segmentation, targeted marketing, and personalized engagement strategies to enhance customer loyalty and drive sales.

# Business Object 8
## What is the combined revenue earned from the "Electronics" & "Clothing" categories, from "Flagship stores"?
  ### -(Code)
select sum(t.total_amt) as total_revenue from Transactions t join prod_cat_info pc on t.prod_cat_code = pc.prod_cat_code
where pc.prod_cat in ('electronics','clothing')  group by t.Store_type having t.Store_type = 'Flagship store'
  ## -(Result)

  ## ![image](https://github.com/Himanshu2112000/Data_Analysis_Retail_business_SQL/assets/164239242/18bdbe6e-a841-4f94-9f64-bc630ca1e397)

 ## -(Object Result)
The query calculates the total revenue from transactions related to 'electronics' and 'clothing' product categories, specifically for the 'Flagship store' store type. By joining 'Transactions' with 'prod_cat_info' based on matching product category codes, it provides insights into revenue generated from these categories at flagship stores. This analysis assists in evaluating the performance of specific product categories at flagship locations, guiding inventory management and promotional strategies to optimize sales and profitability.



