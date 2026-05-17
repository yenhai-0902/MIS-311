# MIS-311
Introduction to Business Analytics
## 1. **Data Overview:**  
The analysis focused on identifying sales patterns and customer purchasing behaviour in a supermarket environment. The dataset includes variables such as product category, customer type, quantity sold, city, and total sales revenue.

---

## **Key Variables:**  
This dataset includes 253 rows and 8 columns of data. The variables include:
- **Sale_id (object):** Unique identifier  
- **Branch (object):** Brand of the supermarket  
- **City (object):** City of the supermarket  
- **Customer_type (object):** Type of customers  
- **Product_name (object):** Name of product  
- **Product_category (object):** Category of product  
- **Quantity (int):** Amount sold  
- **Total_price (float64):** Amount of sales in USD  

---

## 2. **Data Cleaning:**  

Before conducting the analysis, the dataset was checked for missing values, duplicate records, and inconsistent product categories. this step was important because poor data quality can lead to inaccurate insights and misleading business conclusions.

| issue                     | column              | number_of_cases | treatment                                   |
|---------------------------|---------------------|-----------------|---------------------------------------------|
| missing values            | customer_type       | 3               | replaced with mode: member                  |
| missing values            | product_category    | 6               | reclassified based on product_name          |
| missing values            | quantity            | 3               | replaced with median: 11                    |
| duplicate records         | whole dataset       | 3               | removed                                     |
| inconsistent categories   | product_category    | several cases   | created cleaned_product_category            |

### Cleaning explanation

The missing values in `customer_type` were replaced with member because it was the most frequent customer type in the dataset. this method helps preserve the dataset size while keeping the customer type distribution relatively stable.

The missing values and inconsistencies in `product_category` were handled by comparing the product category with the product name. some products were placed in unsuitable categories. for example, orange juice should be classified as beverages, detergent should be classified as household, and shampoo should be classified as personal care. therefore, a new cleaned category column was created to make the product classification more consistent.

The missing values in `quantity` were replaced using the median value. since quantity represents the number of units sold, it should be shown as a whole number. the median value was more appropriate than the mean because the mean was approximately 10.6, which is not suitable for product quantity in a retail context.

After removing duplicate records and handling missing values, the final cleaned dataset contains 239 unique transactions. the cleaned dataset is more reliable and suitable for descriptive statistics, visualization, and further business analysis.

---



## 3. **Descriptive Statistics:**

Descriptive statistics were used to summarize the main numerical variables in the dataset, including quantity, total price, and revenue.

| variable     | description                                               |
|--------------|-----------------------------------------------------------|
| quantity     | shows the number of products sold in each transaction     |
| total price  | shows the total value of each transaction                 |
| revenue      | shows the revenue generated from each transaction         |

The descriptive statistics provide a general overview of customer purchasing behavior. they help identify the average transaction size, the range of transaction values, and the overall distribution of sales performance.

<img width="561" height="224" alt="image" src="https://github.com/user-attachments/assets/fbdc1e48-6f5f-4f0a-bff5-de634113b530" />

<img width="381" height="60" alt="image" src="https://github.com/user-attachments/assets/94c87ea7-8325-4a70-adca-abf5718d2caf" />

The supermarket generated a high total sales value, indicating strong customer purchasing activity. The average sales per transaction also suggest stable consumer spending patterns across different product categories. 

## 3.1. Insight 1: Average Total price by Customer type

<img width="233" height="78" alt="image" src="https://github.com/user-attachments/assets/d7ed32c5-59e5-40e4-81bf-de51caeda196" />

 <img width="475" height="297" alt="image" src="https://github.com/user-attachments/assets/165b15cb-bebb-4454-b403-4e7afb340b4d" />

---


This analysis compares the average transaction value between different customer types, including member customers and normal customers. Based on the pivot table, member customers recorded an average total price of 133.88, while normal customers recorded an average total price of 112.38. the overall average total price of all transactions was 123.77.

This means that member customers spent approximately 21.50 more per transaction than normal customers. in percentage terms, the average spending of member customers was about 19.1% higher than that of normal customers. The chart indicates that member customers have a higher average transaction value than normal customers. this suggests that customers who join the membership program may be more likely to spend more per transaction.

From a business perspective, this finding shows that the membership program may help increase customer value. therefore, the business should continue to encourage customers to become members by offering loyalty points, exclusive discounts, or personalized promotions.

#### Business meaning

Member customers appear to be a more valuable customer segment because they generate a higher average transaction value. the business should focus on retaining these customers and increasing their purchase frequency through loyalty programs, targeted promotions, and personalized marketing campaigns.


### 3.2. Insight 2: Total price by City

<img width="220" height="98" alt="image" src="https://github.com/user-attachments/assets/f3aa961a-3318-4d56-8ab0-b0f4dac22bb7" />
<img width="478" height="287" alt="image" src="https://github.com/user-attachments/assets/8ae01f49-fe8b-4113-aa8a-c99b63e27f27" />

---

This analysis compares the total transaction value across three cities: Chicago, Los angeles, and New york.

Based on the pivot table, chicago recorded the highest total price at 11,133.05, followed by new york with 10,992.27, while los angeles had the lowest total price at 9,187.46. the total transaction value across all three cities was 31,312.78. In terms of contribution, Chicago accounted for approximately 35.6% of the total sales value, New york contributed around 35.1%, and Los angeles contributed about 29.3%. this shows that Chicago and New york generated very similar sales performance, while los angeles was noticeably lower.

The difference between Chicago and New york was only 140.78, which means their sales performance was almost equal. however, Chicago generated 1,945.59 more than Los angeles, and New york generated 1,804.81 more than Los angeles. From a business perspective, Chicago and New york appear to be the strongest-performing cities in terms of total transaction value. these cities may have stronger customer demand, better sales activity, or more effective product performance. meanwhile, Los angeles may need more attention in terms of promotion, customer engagement, or product availability.

#### Business meaning

Chicago and new york should be prioritized because they contribute the largest share of total sales. the business should maintain strong inventory and marketing activities in these two cities. at the same time, los angeles should be analyzed further to understand why its total sales value is lower and what strategies can be used to improve its performance.


### 3.3. Insight 3: Revenue Distribution by Product Category

<img width="206" height="139" alt="image" src="https://github.com/user-attachments/assets/50b4fe11-2fa1-4ed5-ab43-2a7149d4f0c5" />
<img width="480" height="296" alt="image" src="https://github.com/user-attachments/assets/b797f180-a34e-4a21-b525-d7343474e72f" />

---

This analysis examines how total revenue is distributed across different product categories, including Fruits, Stationery, Beverages, Household, and Personal care.

Based on the pivot table, Fruits generated the highest revenue at 116,766.92, followed by Stationery with 96,477.07 and beverages with 95,533.38. meanwhile, Household recorded 70,915.60, and Personal care had the lowest revenue at 64,779.15. the total revenue across all product categories was 444,472.12. In terms of revenue contribution, Fruits accounted for approximately 26.3% of total revenue, making it the strongest-performing product category. stationery contributed around 21.7%, while Beverages contributed about 21.5%. Household and Personal care contributed approximately 16.0% and 14.6%, respectively.

The difference between Fruits and Personal care was 51,987.77, showing a clear gap between the highest-performing and lowest-performing categories. Fruits also generated 20,289.85 more revenue than Stationery and 21,233.54 more than Beverages. From a business perspective, Fruits appear to be the most important product category in terms of revenue contribution. This category should be prioritized in inventory management, product availability, and promotional campaigns. Stationery and Beverages also show strong performance, so they can be maintained as key revenue-supporting categories. On the other hand, Household and Personal care may require further analysis to understand whether lower revenue is caused by weaker demand, lower pricing, limited product variety, or insufficient promotion.

#### Business meaning

Fruits, Stationery, and Beverages are the main revenue-driving categories. The business should ensure that these categories are well-stocked and promoted effectively. At the same time, Household and Personal care should be reviewed to identify opportunities for improvement, such as better product placement, discount strategies, or targeted marketing campaigns.

## 4. Overall conclusion:

In conclusion, the analysis shows that member customers, chicago and new york, and the fruits category are the strongest contributors to business performance. member customers spent more per transaction than normal customers, while chicago and new york generated the highest total sales value. in terms of product category, fruits contributed the largest share of total revenue.

These findings suggest that the business should strengthen its membership program, maintain strong marketing and inventory strategies in high-performing cities, and prioritize key product categories such as fruits, stationery, and beverages. lower-performing areas such as los angeles, household, and personal care should also be reviewed to improve future sales performance.
Fruits generated the highest revenue among all product categories, indicating that it was the most profitable and in-demand category.

