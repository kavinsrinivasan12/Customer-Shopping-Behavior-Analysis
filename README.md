# Customer Shopping Behavior Analysis

A comprehensive data analytics project analyzing customer purchasing patterns, demographics, and engagement metrics using SQL, Power BI, and Python. This project demonstrates end-to-end analytics capabilities from data exploration to actionable business insights.

## 📊 Project Overview

This project analyzes **3,900+ customer transactions** across multiple product categories to uncover behavioral patterns, revenue drivers, and customer segmentation opportunities. The analysis covers gender-based revenue distribution, subscription impact, discount effectiveness, and product performance metrics.

**Skills Demonstrated:** SQL | Power BI | Data Analysis | Python | Dashboard Design | Business Intelligence

## 📁 Project Structure

```
├── Customer_Shopping_Behavior_Analysis.pbix    # Power BI Dashboard
├── customer_shopping_behavior.csv               # Dataset (3,900 records)
├── Customer_Shopping_Analysis.sql               # SQL Queries (10 analyses)
└── Customer_Shopping_Behavior_Analysis.ipynb    # Python Notebook
```

## 🔍 Dataset Overview

**Dataset Size:** 3,900 customer records  
**Dimensions:** 18 columns covering demographics, transactions, products, and engagement

### Key Columns:
- **Customer Info:** Customer ID, Age, Gender, Location
- **Purchase Data:** Purchase Amount (USD), Item Purchased, Category
- **Behavior Metrics:** Review Rating, Previous Purchases, Subscription Status, Frequency of Purchases
- **Transaction Details:** Discount Applied, Promo Code Used, Shipping Type, Payment Method
- **Product Attributes:** Size, Color, Season

## 📈 Analysis & Key Queries

### 1. **Revenue by Demographics**
   - Breakdown revenue by gender and age group
   - Identify high-value customer segments
   - **Output:** Gender-based revenue distribution and age group contribution analysis

### 2. **Subscription Impact Analysis**
   - Compare average spend between subscribers vs. non-subscribers
   - Analyze total revenue and customer count by subscription status
   - **Finding:** Subscription status correlation with customer spending patterns

### 3. **Discount Strategy Effectiveness**
   - Identify high-discount products (top 5 by discount rate)
   - Filter customers who used discounts but exceeded average spending
   - **Insight:** Discount application rate by product category

### 4. **Product Performance**
   - Top 5 products by average review rating
   - Top 3 most purchased products within each category
   - **Use Case:** Product recommendation and inventory optimization

### 5. **Customer Segmentation**
   - Segment customers into New (1 purchase), Returning (2-10), and Loyal (10+)
   - Analyze repeat buyer subscription behavior (5+ previous purchases)
   - **Application:** Targeted marketing and retention strategies

### 6. **Shipping & Logistics**
   - Compare average purchase amounts between Standard vs. Express shipping
   - Identify shipping type preferences by customer segment
   - **Impact:** Shipping cost optimization and delivery strategy

## 🎯 Key Insights

✓ Gender-based revenue disparity indicates opportunity for targeted marketing  
✓ Subscribers show distinct purchasing behavior patterns  
✓ High-discount products dominate specific categories  
✓ Review ratings correlate with product category (Accessories ≥ 4.5 avg)  
✓ Repeat buyers (5+ purchases) show strong subscription adoption  
✓ Seasonal purchase patterns present inventory optimization opportunities  

## 🛠️ SQL Queries Implemented

10 production-ready queries including:
- Aggregation with GROUP BY and window functions
- Complex filtering and subqueries
- CTEs (Common Table Expressions) for data staging
- DENSE_RANK() for product rankings
- CASE statements for customer segmentation
- JOIN operations (implied through multi-column analysis)

**Sample Query Architecture:**
```sql
-- Example: Top Products with Ranking
With category_wise_cnt as (
    Select Category, item_purchased, Count(item_purchased) as Cnt
    From customer 
    Group by category, item_purchased
),
top_3_products as (
    Select *, Dense_Rank() Over(Partition by category Order by cnt Desc) as drnk
    From category_wise_cnt 
)
Select * From top_3_products Where drnk <= 3;
```

## 📊 Power BI Dashboard Features

- **Interactive dashboard** with customer and product analysis
- **KPI cards** for revenue, customer count, and subscription rates

## 💡 Business Applications

### For BFSI Sector:
- Customer lifetime value (CLV) estimation framework
- Risk segmentation based on purchase consistency
- Subscription model optimization

### For E-Commerce Sector:
- Product recommendation engine foundation
- Discount strategy ROI analysis
- Customer retention and churn prediction setup
- Inventory management optimization

## 🚀 How to Use

1. **SQL Analysis:** Run queries in your SQL database (MS SQL Server, PostgreSQL, MySQL)
2. **Power BI Dashboard:** Open `.pbix` file to explore interactive visualizations
3. **Dataset:** Use `customer_shopping_behavior.csv` for custom analysis

## 📌 Technical Stack

| Component | Technology |
|-----------|-----------|
| Data Source | CSV (3,900 records) |
| SQL Queries | T-SQL / Standard SQL |
| Visualization | Power BI |
| Analysis | Python, SQL |
| Database | Compatible with MS SQL, PostgreSQL, MySQL |

## 🎓 Learning Outcomes

This project demonstrates proficiency in:
- ✅ SQL query optimization and complex data retrieval
- ✅ Business intelligence dashboard design
- ✅ Customer segmentation and RFM analysis
- ✅ Data-driven decision-making frameworks
- ✅ End-to-end analytics pipeline (Data → Analysis → Visualization)

## 📧 Contact

- **LinkedIn:** [linkedin.com/in/kavinsrinivasan12](https://linkedin.com/in/kavinsrinivasan12)
