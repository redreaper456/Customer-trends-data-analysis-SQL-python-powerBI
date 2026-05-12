# Customer Shopping Behavior Analysis

![Data Analysis](https://img.shields.io/badge/Data-Analysis-blue)
![Python](https://img.shields.io/badge/Python-3.x-yellow)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-🐘-blue)
![Power BI](https://img.shields.io/badge/Power_BI-📊-yellow)

## 📊 Project Overview
This project analyzes customer shopping behavior using transactional data from 3,900 purchases across various product categories. The primary objective is to uncover actionable insights into spending patterns, customer segments, product preferences, and subscription behaviors to guide strategic business decisions and optimize marketing efforts.

## 📂 Dataset Summary
- **Size**: 3,900 rows and 18 columns.
- **Key Features**:
  - **Customer Demographics**: Age, Gender, Location, Subscription Status.
  - **Purchase Details**: Item Purchased, Category, Purchase Amount, Season, Size, Color.
  - **Shopping Behavior**: Discount Applied, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type.
- **Data Quality**: Addressed 37 missing values in the `Review Rating` column.

## 🛠️ Tech Stack & Workflow
1. **Python (Pandas)**: Exploratory Data Analysis (EDA), data cleaning, and feature engineering.
2. **PostgreSQL**: Structured query analysis to extract business KPIs and transactional insights.
3. **Power BI**: Interactive data visualization and dashboarding.

---

## 🔍 Methodology

### 1. Data Preparation & EDA (Python)
- **Missing Data Handling**: Imputed missing values in `Review Rating` using the median rating of each respective product category.
- **Standardization**: Converted all column names to snake_case for seamless database integration.
- **Feature Engineering**: 
  - Created `age_group` by binning customer ages.
  - Derived `purchase_frequency_days` from raw purchase data.
- **Data Consistency**: Dropped redundant columns (`promo_code_used`) after verifying overlap with `discount_applied`.
- **Database Integration**: Exported the cleaned dataset directly into PostgreSQL.

### 2. SQL Analysis (PostgreSQL)
Key business questions were answered using structured SQL queries:
- **Revenue by Gender**: Analyzed total revenue contributions (Male: $157,890 | Female: $75,191).
- **High-Spending Discount Users**: Identified customers utilizing discounts but maintaining above-average basket sizes.
- **Product Performance**: 
  - Top 5 products by rating: Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78).
  - Identified the top 3 best-selling products across all major categories (Accessories, Clothing, Footwear, Outerwear).
- **Subscription Economics**: Compared average spend and total revenue between subscribers ($62,645 total) and non-subscribers ($170,436 total).
- **Customer Segmentation**: Segmented users into Loyal (3,116), Returning (701), and New (83) based on historical purchase counts.

### 3. Data Visualization (Power BI)
Built an interactive **Customer Behavior Dashboard** highlighting:
- High-level KPIs (Total Customers, Average Purchase Amount, Average Review Rating).
- Revenue and Sales breakdowns by Category and Age Group.
- Customer distribution by Subscription Status.

---

## 💡 Key Business Recommendations

Based on the analysis, the following strategic actions are recommended:

1. **Boost Subscriptions**: Since non-subscribers currently make up ~73% of the customer base but repeat buyers show potential, promote exclusive benefits to convert them into subscribers.
2. **Customer Loyalty Programs**: Reward the massive base of "Loyal" customers (3,116 users) to maintain retention and increase lifetime value.
3. **Review Discount Policy**: Highly discounted items (like Hats, Sneakers, and Coats at ~47-50% discount rates) should be monitored to balance sales volume with profit margin control.
4. **Product Positioning**: Highlight top-rated products (Gloves, Sandals) and best-sellers (Blouses, Pants, Jewelry) in front-page marketing campaigns.
5. **Targeted Marketing**: Focus retention and upsell efforts on the "Young Adult" demographic, which represents the highest revenue-generating age group ($62,143).

## 🚀 How to Run the Project
1. Clone the repository to your local machine.
2. Run the `Customer_Shopping_Behaviour_Analysis.py` script to preprocess the raw dataset and engineer new features.
3. Execute `customer_behavior_sql_queries.sql` in your PostgreSQL environment to generate the analytical views.
4. Open `Customer_Behavior_Dashboard.pbix` in Power BI Desktop to interact with the visual dashboard.
