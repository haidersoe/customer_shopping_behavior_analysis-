# Customer Shopping Behavior Analysis  
**Python · PostgreSQL (SQL) · Power BI · Data Visualization**

This project is an end-to-end analysis of customer shopping behavior for a retail business.  
It combines **Python (EDA & preprocessing)**, **PostgreSQL (analytical SQL)**, and **Power BI (dashboarding)** to answer real business questions about **revenue drivers, loyalty, discounts, and customer segments**.

---

## 🚀 What This Project Demonstrates

This project is designed to showcase my skills as a **Data Analyst / Quantitative Researcher**:

- Writing **clean, analytical SQL** to answer business questions
- Performing **EDA and feature engineering in Python**
- Designing an **interactive Power BI dashboard**
- Translating data into **clear, actionable business recommendations**
- Working with an **end-to-end analytics pipeline**: CSV → Python → PostgreSQL → SQL → Power BI → Insights

---

## 🧩 Dataset

- **Rows:** 3,900 customer transactions  
- **Features:** 17+  
  - Customer: `customer_id`, `age`, `gender`, `location`  
  - Transaction: `item_purchased`, `category`, `purchase_amount`, `season`, `payment_method`  
  - Behavior: `previous_purchases`, `subscription_status`, `frequency_of_purchases`, `review_rating`, `discount_applied`, `shipping_type`  

- **Missing values:** None (checked via `df.isnull().sum()`)

---

## 🔄 Project Workflow

1. **Data Loading & Cleaning (Python / Pandas)**
   - Loaded CSV into pandas DataFrame
   - Standardized column names and removed redundant columns
   - Renamed `purchase_amount_(usd)` → `purchase_amount`
   - Verified there were **no missing values**

2. **Feature Engineering**
   - Created **`age_group`** (e.g. Young Adult, Adult, Middle Aged, Senior) using age distribution
   - Converted **`frequency_of_purchases`** from labels (e.g. “Weekly”, “Monthly”) into numeric days
   - Prepared a clean, analysis-ready dataset

3. **Loading into PostgreSQL**
   - Exported cleaned DataFrame to PostgreSQL using `SQLAlchemy`
   - Created a `customer_behavior` table for SQL analysis

4. **Analytical SQL (PostgreSQL)**
   - Wrote a series of **business-focused SQL queries** (see `sql/` folder) to analyze:
     - Revenue by gender and age group  
     - Subscription vs non-subscription behavior  
     - Customer loyalty and repeat purchases  
     - Product performance and ratings  
     - Discount sensitivity by product and category  
     - Shipping preferences and satisfaction  
     - Seasonal revenue patterns  

5. **Visualization in Power BI**
   - Built an interactive dashboard showing:
     - Total revenue & total customers  
     - Revenue by gender, age group, and category  
     - Subscription vs non-subscription contribution  
     - Top products and repeat purchases  
     - Discount usage & shipping behavior  
     - Seasonality trends  

6. **Findings & Recommendations**
   - Summarised key patterns and turned them into **concrete business actions**

---

## 📊 Key Analytical Findings

### 1. Customer Segments & Revenue

- **Gender**
  - Male customers generate **more than double** the revenue of female customers.
- **Age Group**
  - **Young Adults** are the top contributing age group by revenue.
  - Revenue is relatively balanced across all age groups (Young Adult, Adult, Middle Aged, Senior).

### 2. Subscription Behavior

- **Non-subscribers**:
  - Generate the majority of revenue.
  - Have a slightly higher average spend than subscribers.
- **Subscribers**:
  - Make up a smaller share of total customers.
- Even among **repeat buyers**, most are **not** subscribed.

➡ **Interpretation:** The subscription program exists but is **not yet driving higher spend or strong adoption**.

### 3. Loyalty & Repeat Purchases

- The customer base is dominated by **Loyal** and **Returning** customers.
- **New customers** represent only a small fraction.
- Products like **Blouse, Jewelry, Dress, Shirt, Pants** are heavily associated with **repeat purchases**.

### 4. Product Performance & Satisfaction

- **Clothing and Accessories** are the highest-revenue categories.
- Highest-rated products (by review rating) include:
  - Gloves, Sandals, Boots, Hat, T-shirt
- These items are strong candidates for promotions and feature placements.

### 5. Discount Sensitivity

- Across all categories (Clothing, Footwear, Outerwear, Accessories), roughly **42–44%** of orders use discounts.
- Some products (e.g. Hat, Sneakers, Coat, Sweater, Pants) see discounts applied in nearly **half** of all purchases.

➡ **Interpretation:** Customers are **highly discount-sensitive**; pricing and promotion strategy is critical.

### 6. Shipping & Seasonality

- **Express shipping** customers tend to spend slightly more per order.
- **Standard shipping** has the highest average satisfaction rating.
- Clothing revenue is strong across all seasons, with **Spring and Winter** showing modest peaks.

---

## 💡 Business Recommendations

Based on the analysis:

1. **Target High-Value Segments**
   - Focus campaigns on **Male** and **Young Adult** segments, who contribute the most revenue.
   - Tailor messaging, product suggestions, and discounts to these demographics.

2. **Redesign the Subscription Program**
   - Introduce clear benefits (loyalty points, member-only discounts, free/priority shipping).
   - Specifically target **loyal and returning customers** with subscription offers.
   - Track whether subscription leads to higher lifetime value.

3. **Leverage Repeat-Driving Products**
   - Promote products like **Blouse, Jewelry, Dress, Shirt, Pants** as flagship items.
   - Use them in bundles and cross-sell strategies to boost basket size.

4. **Optimize Discount Strategy**
   - Shift away from broad, flat discounts toward **targeted promotions**:
     - New customers  
     - Inactive customers  
     - Price-sensitive segments  
   - Reevaluate pricing for products where ~50% of sales require discounts.

5. **Shipping Strategy**
   - Keep **Standard shipping** as the default option given its strong satisfaction scores.
   - Offer **Express shipping** as an upsell, especially for high-value carts.

6. **Seasonal & Inventory Planning**
   - Plan inventory and marketing pushes around **Spring and Winter** peaks.
   - Maintain steady availability of top-performing products year-round.

---

## 📊 Power BI Dashboard

The Power BI report includes:

- KPIs: Total Revenue, Total Customers, Avg Purchase Amount, Avg Rating  
- Slicers for: Gender, Age Group, Subscription Status, Category, Season  
- Visuals for:
  - Revenue by gender, age group, category  
  - Top products and repeat behavior  
  - Discount usage  
  - Shipping method performance  
  - Seasonal sales patterns  

> You can open the dashboard from the `.pbix` file in the `dashboard/` folder.

---

## 🧪 Tech Stack

- **Programming & EDA:** Python (Pandas, NumPy, Matplotlib, Seaborn)
- **Database:** PostgreSQL
- **Integration:** SQLAlchemy (Python → PostgreSQL)
- **Visualization:** Power BI
- **Environment:** Jupyter Notebook

---

## 🔁 How to Run This Project (Locally)

1. **Clone the repo**
   ```bash
   git clone https://github.com/<your-username>/customer-shopping-behavior-analysis.git
   cd customer-shopping-behavior-analysis
