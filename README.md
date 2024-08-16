# GlobalDoor-sales-Analysis
## Project Overview 
This repository contains a comprehensive sales data analysis from  the GlobalStore . Using Excel, Microsoft  SQL Server, and Power BI, the project explores trends, and  revenue patterns to provide actionable insights for optimizing sales strategies, providing recommendations  and improving business performance.

### Data Sources 
The dataset used for this analysis is "GlobalSuperstore - Capstone.xlsx." containing each sale made by the company.
  - [Downlaod Here](https://docs.google.com/spreadsheets/d/1nxESpFzWjlGDMGDVLH69xmDzIl9l6OEq/edit#gid=633280281)

### Tools 
- Excel for data cleaning
   - [Download Here](https://Microsoft.com)
- SQL server management studio for data exploration and analysis
   - [Download Here](https://aka.ms/ssmsfullsetup)
- Power BI for visualization/creating a report


### Data cleaning/Preparation
In the initial prepartion phase we  performed the following;
1. loaded the data into excel.
2. Checked for duplicates.
3. Inspected the data if there is no missing values.
4. Removed unnecessary columns
   
### Exploratory data Analysis
The EDA phase involves exploring the sales data to discover trends and answer questions such as ;
1. Question 1.
- What are the three countries that generated the highest total profit for Global Superstore in 2014?
- For each of these three countries, find the three products with the highest total profit. Specifically,
   what are the products’ names and the total profit for each product?
2. Question 2.
- Identify the 3 subcategories with the highest average shipping cost in the United States.
3. Question 3.
- Assess Nigeria’s profitability (i.e., total profit) for 2014. How does it compare to other African
countries?
- What factors might be responsible for Nigeria’s poor performance? 
4. Question 4.
- Identify the product subcategory that is the least profitable in Southeast Asia.
- Is there a specific country in Southeast Asia where Global Superstore should stop offering the
subcategory identified ?
5. Question 5.
- Which city is the least profitable (in terms of average profit) in the United States? For this analysis,
discard the cities with less than 10 Orders. b) Why is this city’s average profit so low?
6. Question 6.
- Which product subcategory has the highest average profit in Australia?
### Data Analysis
  The data analysis was done using MY SQL management server
  ```SQL
    SELECT TOP 1 City,ROUND(AVG(Profit),2) as profit ,COUNT(Order_ID) as count1 
    FROM ORDERS 
    WHERE Country='United States'
    GROUP BY City 
    HAVING Count(Order_ID)>10
    ORDER BY profit ASC;
 ```
 ```SQL
   SELECT TOP 1 Country,ROUND(SUM(Profit),2)as profit
   FROM ORDERS 
   WHERE Sub_Category = 'Tables'
	  AND Region='Southeast Asia'
   GROUP BY Country
   ORDER BY profit ASC;
 ```
### Results and findings
- United states ,India and China where the top 3 countries that generated the highest total profit in the year 2014 with a total profit of $933508,$48808  and $46794 respectively.
- The three categories with the highest shipping cost in the united states are copiers,machines and Tables.
- Compared to other countries nigeria is the less profitable country($-23,825) and this can be because of the high shipping cost and high discount rates.
- Indonesia is a country where selling tables proves to be highly unprofitable.
- Lancester is the least profitable city in the united states.
- Appliances has the highest average profit in Australia.

### Recommendations
  - It is recommended that the company set up warehouses or partner with local fulfillment centers  strategically located closer to the  customers in Nigeria.This will reduce the cost of shipping to this country.
  - The company should consider reducing the sales of tables in Indonesia because it is not profitable.

### References
- How to use new Visual cards Power BI [Here](https://youtu.be/jvwT1KS86dU?si=dyRlhHi_uKZdFf_Y)
  
  
