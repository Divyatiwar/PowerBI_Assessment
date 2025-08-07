Project Overview
This Power BI assessment project simulates a real-world sales dashboard creation scenario. The goal was to clean, model, analyze, and visualize sales data to uncover business insights for stakeholders.

The dataset consisted of raw sales transactions across various products, customers, and feedback metrics. The analysis focused on building KPIs, trend analysis, and customer behavior metrics.

📂 Dataset Used
Sales Table: Includes transactionId, customerId, productId, date, quantity, shippingCost, profit, orderId, feedback score.

Products Table: Product details like name and category.

Customers Table: Customer demographic data like ID and location.

🧹 Data Cleaning & Transformation
Performed in Power Query Editor:

Removed null and duplicate values

Renamed columns for clarity

Corrected data types (e.g., date, numeric)

Merged lookup tables (Products & Customers) using appropriate joins

Removed unnecessary columns

📐 Data Modeling
Sales Table: Fact table containing transactional data

Products Table: Dimension table (linked via Product ID)

Customers Table: Dimension table (linked via Customer ID)

Used Star Schema model design for efficient relationship management

Set proper data cardinality and cross-filter directions

🧮 DAX Measures Created
Measure Name	Description
Total Revenue	SUM(Sales[shippingCost])
Total Orders	DISTINCTCOUNT(Sales[transactionId])
Total Quantity	Already present in dataset
Total Profit	SUM(Sales[Profit])
Average Order Value	DIVIDE(SUM(Sales[shippingCost]), DISTINCTCOUNT(Sales[transactionId]))
Product Rank	RANKX(ALL(Products[Product_Name]), [Total Revenue], DESC)
Avg Feedback Score	AVERAGEX(VALUES(Products[Category]), CALCULATE(AVERAGE(Sales[FeedbackScore])))
Repeat Purchase Rate	Measures loyal customers who ordered more than once
Customer Lifetime Value	Revenue generated per customer using ALLEXCEPT
Moving Average Revenue	3-month moving average for revenue trends

📈 Dashboard Features
🔹 Top KPIs Cards: Revenue, Orders, Quantity

📊 Line Chart: Monthly Revenue Trend

📦 Bar Chart: Top Selling Products by Revenue

🎯 Customer Analysis: Repeat Purchase Rate, Lifetime Value

🌟 Feedback Visualization: Avg Feedback Score by Category

🧭 Filters & Slicers: Product category, Customer region, Date

💡 Business Insights Derived
Identified top-performing products and categories

Analyzed revenue trends over time

Measured customer satisfaction through feedback scores

Found repeat purchase behavior and high-LTV customers

Calculated average order value for pricing strategy

🛠️ Tools & Technologies Used
Power BI Desktop

Power Query Editor

DAX (Data Analysis Expressions)

Excel (initial data review)

📌 Learning Outcomes
Real-world experience in cleaning and transforming sales data

Developed analytical thinking using DAX and visual storytelling

Built a complete dashboard using industry-standard Power BI practices

Understood business KPIs and customer behavior metrics
