# 🛒 Flipkart Product Analysis | Python, Pandas & Data Visualization

## 📌 Project Overview

This project performs an end-to-end exploratory data analysis of **80,000 Flipkart product listings** using Python. The analysis focuses on product pricing, discounts, estimated revenue, sales volume, customer ratings, seller performance, delivery time, return policies, inventory, and product categories.

The objective is to transform raw e-commerce product data into meaningful analytical insights that can support decisions related to **pricing, promotions, product assortment, seller performance, customer experience, and operational strategy**.

The project uses **Pandas, NumPy, Matplotlib, and Seaborn** for data preparation, statistical analysis, exploratory data analysis, and visualization.

---

## 🎯 Business Objectives

The analysis aims to answer the following business questions:

* Which product categories have the highest number of listings?
* Which categories generate the highest estimated revenue?
* Which products have the highest sales volume?
* How are product prices distributed?
* How effective are discounts in driving units sold?
* Which categories have the highest average discount?
* Which categories have the highest customer ratings?
* Does customer rating have a meaningful relationship with units sold?
* Does delivery time appear to influence sales?
* Does return-policy duration appear to influence sales?
* Which brands generate the highest sales volume?
* Which sellers have the highest average product scores?
* Which products have high ratings but low sales?
* Which products have high prices but relatively low sales?
* Which products may represent potential business risks?

---

## 📊 Dataset Overview

The dataset contains **80,000 product records** and **25 original columns** covering product, seller, pricing, customer experience, inventory, shipping, and sales-related information.

### Dataset Size

| Metric                  |            Value |
| ----------------------- | ---------------: |
| Records                 |           80,000 |
| Original Columns        |               25 |
| Original Missing Values | 13,484 in `size` |
| Duplicate Rows          |                0 |
| Average Product Price   |       ₹30,137.26 |
| Average Discount        |           21.35% |
| Average Final Price     |       ₹23,697.78 |
| Average Rating          |             3.00 |
| Average Units Sold      |         2,507.52 |
| Average Delivery Time   |        6.01 days |
| Average Seller Rating   |             4.00 |

---

## 🧾 Key Dataset Columns

| Column               | Description                       |
| -------------------- | --------------------------------- |
| `product_id`         | Unique product identifier         |
| `product_name`       | Product name                      |
| `category`           | Product category                  |
| `brand`              | Product brand                     |
| `seller`             | Seller name                       |
| `seller_city`        | Seller location                   |
| `price`              | Original product price            |
| `discount_percent`   | Percentage discount               |
| `final_price`        | Price after discount              |
| `rating`             | Customer product rating           |
| `review_count`       | Number of reviews                 |
| `stock_available`    | Available inventory               |
| `units_sold`         | Units sold                        |
| `listing_date`       | Product listing date              |
| `delivery_days`      | Expected delivery duration        |
| `weight_g`           | Product weight                    |
| `warranty_months`    | Warranty duration                 |
| `color`              | Product color                     |
| `size`               | Product size                      |
| `return_policy_days` | Return-policy duration            |
| `is_returnable`      | Whether the product is returnable |
| `payment_modes`      | Available payment methods         |
| `shipping_weight_g`  | Shipping weight                   |
| `product_score`      | Product performance score         |
| `seller_rating`      | Seller rating                     |

---

## 🛠️ Tools & Technologies

### Programming & Analysis

* Python
* Pandas
* NumPy

### Visualization

* Matplotlib
* Seaborn

### Environment

* Jupyter Notebook

---

# 🔄 Analytical Workflow

```text
Raw E-Commerce Data
        ↓
Data Inspection
        ↓
Data Quality Analysis
        ↓
Missing-Value Treatment
        ↓
Duplicate Check
        ↓
Feature Engineering
        ↓
Descriptive Statistics
        ↓
Exploratory Data Analysis
        ↓
Category & Product Analysis
        ↓
Sales & Revenue Analysis
        ↓
Correlation Analysis
        ↓
Business Segmentation
        ↓
Key Insights
        ↓
Business Recommendations
```

---

# 🧹 1. Data Cleaning & Preparation

The first stage focused on understanding the structure and quality of the dataset.

### Data Quality Checks

The following checks were performed:

* Dataset structure and data types
* Missing-value analysis
* Duplicate-record analysis
* Numerical descriptive statistics
* Initial data inspection

### Missing Values

The `size` column contained **13,484 missing values**.

Instead of removing these records and potentially losing useful product information, the missing values were represented as:

```text
Unknown
```

This preserved the product records while clearly identifying unavailable size information.

### Duplicate Records

The dataset contained:

```text
0 duplicate rows
```

Therefore, no duplicate records were removed.

---

# ⚙️ 2. Feature Engineering

Additional analytical variables were created to support business analysis.

### Discount Value

```python
discount_value = price - final_price
```

This represents the monetary value of the discount applied to a product.

### Estimated Revenue

```python
revenue_estimate = final_price × units_sold
```

This provides an **estimated revenue measure** based on the available product price and units-sold fields.

> **Note:** This should not be interpreted as verified transaction revenue because the dataset does not contain actual order-level revenue records.

---

# 📈 3. Descriptive Statistics

The numerical variables were analyzed using descriptive statistics including:

* Mean
* Median
* Standard deviation
* Minimum
* Maximum
* Quartiles

### Key Statistical Observations

* Average product price: **₹30,137.26**
* Median product price: **₹30,164.46**
* Average discount: **21.35%**
* Median discount: **20%**
* Average final price: **₹23,697.78**
* Average customer rating: **3.00**
* Average units sold: **2,507.52**
* Average delivery time: **6.01 days**
* Average seller rating: **4.00**

---

# 🛍️ 4. Category Analysis

Product categories were analyzed based on:

* Number of listings
* Average price
* Average discount
* Average rating
* Estimated revenue

### Product Distribution

The largest category by number of product listings was:

**Toys — 10,151 products**

Other large categories included:

* Beauty — 10,094
* Fashion — 10,080
* Electronics — 10,052
* Sports — 9,985
* Appliances — 9,971
* Mobiles — 9,904
* Home & Kitchen — 9,763

### Average Price by Category

**Beauty** had the highest average product price at approximately **₹30,328**.

### Average Discount by Category

**Toys** had the highest average discount at approximately **21.48%**.

### Average Rating by Category

**Fashion** had the highest average rating at approximately **3.02**.

---

# 💰 5. Estimated Revenue Analysis

Estimated revenue was calculated using:

```text
Final Price × Units Sold
```

### Estimated Revenue by Category

| Category       | Estimated Revenue |
| -------------- | ----------------: |
| Toys           |          ₹606.45B |
| Beauty         |          ₹605.82B |
| Fashion        |          ₹599.56B |
| Electronics    |          ₹599.49B |
| Appliances     |          ₹594.06B |
| Sports         |          ₹589.05B |
| Mobiles        |          ₹584.33B |
| Home & Kitchen |          ₹583.16B |

### Key Finding

**Toys** generated the highest estimated revenue in the dataset at approximately **₹606.45 billion**, followed closely by **Beauty at ₹605.82 billion**.

The relatively small difference between the leading categories suggests that estimated revenue is broadly distributed across the product portfolio.

---

# 🏆 6. Product & Brand Performance

The project identifies:

* Top-selling products by units sold
* Top brands by total units sold
* High-rated products with low sales
* High-priced products with relatively low sales

This helps distinguish between:

### High-performing products

Products with strong sales volume.

### Hidden opportunities

Products with high customer ratings but relatively low sales.

### Potential pricing problems

Products with relatively high final prices but low sales volume.

### Risk candidates

Products combining low ratings with longer return policies.

---

# 🏪 7. Seller Analysis

Seller performance was evaluated using average `product_score`.

The ranking showed:

| Seller       | Average Product Score |
| ------------ | --------------------: |
| MegaStore    |                 51.07 |
| SmartDeals   |                 50.90 |
| ValueKart    |                 50.75 |
| SuperMart    |                 50.72 |
| BestBuy      |                 50.67 |
| QuickShop    |                 50.51 |
| UrbanRetails |                 50.48 |
| RetailHub    |                 50.29 |

### Key Finding

**MegaStore** recorded the highest average product score among the sellers analyzed.

The differences between sellers are relatively small, suggesting that seller-level performance should be evaluated alongside additional metrics such as sales volume, seller rating, product ratings, and delivery performance.

---

# 🏷️ 8. Discount Analysis

The relationship between discount percentage and sales volume was analyzed using both grouped statistics and visualization.

Average units sold by discount level were approximately:

| Discount | Average Units Sold |
| -------: | -----------------: |
|       0% |           2,532.59 |
|       5% |           2,519.56 |
|      10% |           2,480.26 |
|      15% |           2,510.91 |
|      20% |           2,483.73 |
|      30% |           2,504.08 |
|      40% |           2,506.95 |
|      50% |           2,522.36 |

### Key Finding

Average units sold remain relatively similar across discount levels.

This suggests that **higher discounts do not automatically correspond to substantially higher unit sales** within this dataset.

Therefore, applying deeper discounts universally may not be the most effective strategy.

---

# ⭐ 9. Customer Rating Analysis

Customer ratings were analyzed across products and categories.

### Average Rating

The overall average product rating was approximately:

**3.00 / 5**

### Highest-Rated Categories

1. Fashion — **3.02**
2. Appliances — **3.02**
3. Toys — **3.00**
4. Electronics — **3.00**
5. Beauty — **3.00**

### Lowest Average Rating

Mobiles recorded the lowest average category rating at approximately **2.97**.

---

# 🔗 10. Correlation Analysis

Correlation analysis was used to examine relationships between key numerical variables.

### Rating vs Units Sold

Correlation:

**-0.0012**

This indicates an almost nonexistent linear relationship between product rating and units sold.

### Delivery Days vs Units Sold

Correlation:

**0.0016**

This indicates an almost nonexistent linear relationship between delivery time and units sold.

### Return Policy Days vs Units Sold

Correlation:

**-0.0039**

Again, the relationship is extremely weak.

### Weight vs Units Sold

Correlation:

**-0.0013**

The relationship is also negligible.

---

# 🔍 11. Price, Discount & Rating Relationships

The analysis specifically evaluated the relationship between:

* Price and rating
* Discount and rating
* Price and discount

### Price vs Rating

Correlation:

**-0.0038**

This indicates virtually no linear relationship between product price and customer rating.

### Discount vs Rating

Correlation:

**0.0069**

This indicates virtually no linear relationship between discount percentage and customer rating.

### Price vs Discount

Correlation:

**0.0018**

This indicates virtually no linear relationship between original product price and discount percentage.

### Analytical Interpretation

The results suggest that **price, discount percentage, and customer rating behave largely independently in this dataset** from a linear-correlation perspective.

> Correlation does not imply causation, so these results should be interpreted as relationships rather than causal effects.

---

# 🎯 12. Product Segmentation

Products were segmented into:

* **Low Price**
* **Medium Price**
* **High Price**

using the 33rd and 66th percentiles of `final_price`.

This segmentation provides a simple framework for comparing products across different pricing tiers.

---

# 💎 13. Hidden-Gem Analysis

Products were identified that had:

* High customer ratings
* Low units sold

These products can represent potential **underexposed or underperforming high-quality products**.

Possible reasons may include:

* Low visibility
* Weak product placement
* Limited promotion
* Higher price
* Low brand awareness

Further analysis would be required to determine the exact cause.

---

# ⚠️ 14. Risk Analysis

Products with:

* Rating below 3
* Return policy greater than 10 days

were identified as potential risk candidates.

These products may require additional investigation because low customer satisfaction combined with a longer return window could create customer-experience and operational concerns.

---

# 📊 15. Visualizations Created

The project includes visual analysis covering:

### Product & Category Analysis

* Number of products by category
* Top categories by estimated revenue
* Top-rated categories

### Pricing

* Price distribution
* Price segmentation

### Discount Analysis

* Discount vs units sold
* Average discount by category

### Sales Analysis

* Top brands by units sold
* Rating vs units sold
* Delivery days vs units sold

### Operations

* Return policy vs units sold

### Statistical Analysis

* Correlation heatmap
* Price, discount and rating correlation

---

# 💡 16. Key Business Insights

### 1. Product assortment is relatively balanced

No single category dominates the number of product listings. Toys, Beauty, Fashion, and Electronics each contribute roughly 10,000 listings.

**Business implication:** The platform has a relatively broad product portfolio, allowing category-level optimization rather than relying on a single dominant category.

---

### 2. Toys leads estimated revenue

Toys generated approximately **₹606.45B in estimated revenue**, followed closely by Beauty at approximately **₹605.82B**.

**Business implication:** These categories should be closely monitored for inventory availability, promotional opportunities, and product-level performance.

---

### 3. Discounts do not show a strong sales relationship

Average units sold remain relatively stable across the analyzed discount levels.

**Business implication:** Increasing discounts alone may not substantially increase sales. Promotional decisions should consider product category, brand, price, ratings, and demand instead of discount percentage alone.

---

### 4. Customer ratings are not strong predictors of sales

The correlation between rating and units sold is approximately **-0.0012**, indicating almost no linear relationship.

**Business implication:** Highly rated products should not automatically be assumed to generate high sales. Visibility, price, brand, availability, and promotional placement may also matter.

---

### 5. Delivery time shows almost no linear relationship with sales

The correlation between delivery days and units sold is approximately **0.0016**.

**Business implication:** Delivery time alone does not explain sales variation in this dataset. However, delivery reliability and customer satisfaction should still be monitored separately.

---

### 6. Fashion has the highest average rating

Fashion recorded the highest average category rating at approximately **3.02**.

**Business implication:** High-rated categories can be evaluated for successful product characteristics and customer preferences.

---

# 💼 17. Business Recommendations

### Recommendation 1 — Use Targeted Discounts

Because average units sold remain relatively stable across discount levels, the platform should avoid relying on blanket discount increases.

**Recommended approach:** Use targeted promotions based on product demand, category, price segment, and historical sales performance.

---

### Recommendation 2 — Promote High-Rating, Low-Sales Products

Products with high ratings but low sales may represent hidden opportunities.

**Recommended approach:** Increase visibility through search ranking, recommendation systems, featured listings, and category-level promotions before increasing discounts.

---

### Recommendation 3 — Investigate High-Price, Low-Sales Products

Products with high final prices and relatively low sales should be reviewed.

**Recommended approach:** Compare their prices against similar products, ratings, brands, discounts, and seller performance before making pricing decisions.

---

### Recommendation 4 — Monitor Low-Rated Products

Products with ratings below 3 should be investigated, particularly when combined with longer return policies.

**Recommended approach:** Review product quality, seller performance, customer feedback, and return behavior before continuing aggressive promotion.

---

### Recommendation 5 — Optimize Category-Level Strategy

Since category-level differences exist in price, discount, rating, and estimated revenue, promotional strategy should be category-specific.

**Recommended approach:** Develop separate pricing and promotional strategies for categories rather than applying a single marketplace-wide approach.

---

### Recommendation 6 — Evaluate Sellers Using Multiple KPIs

Seller performance should not be judged using product score alone.

**Recommended approach:** Combine:

* Seller rating
* Units sold
* Product rating
* Delivery time
* Return policy
* Product score

to create a more complete seller-performance framework.

---

# ⚠️ 18. Analytical Limitations

This analysis has several limitations that should be considered when interpreting the results.

1. The dataset is product-level rather than transaction-level.
2. `revenue_estimate` is calculated using `final_price × units_sold` and should not be treated as verified accounting revenue.
3. The dataset does not provide actual profit or margin information.
4. Correlation analysis identifies linear relationships but does not establish causation.
5. Sales volume may depend on factors not included in the dataset, such as advertising exposure, search ranking, competitor pricing, and seasonality.
6. Customer ratings alone may not fully represent customer satisfaction.
7. The dataset contains product listings across categories and sellers, so some comparisons may reflect differences in product mix.

---

# 🚀 19. Future Improvements

The project can be extended with:

* Profit-margin analysis
* Seller-level performance scoring
* Product recommendation systems
* Price prediction
* Sales forecasting
* Customer review sentiment analysis
* NLP analysis of product reviews
* Competitor price comparison
* Time-series sales analysis
* Category-level demand forecasting
* Interactive Streamlit dashboard
* Automated data pipeline

---

# 📁 20. Project Structure

```text
FLIPKART_PRODUCT_ANALYSIS-PYTHON/
│
├── README.md
│
├── FLIPKART_PRODUCT_ANALYSIS.ipynb
│
├── data/
│   └── flipkart.csv
│
├── images/
│   ├── category_analysis.png
│   ├── revenue_analysis.png
│   ├── price_distribution.png
│   ├── discount_analysis.png
│   ├── rating_analysis.png
│   └── correlation_heatmap.png
│
└── requirements.txt
```

---

# 🧠 21. Skills Demonstrated

### Python

* Pandas
* NumPy
* Data manipulation
* Feature engineering
* Conditional filtering
* GroupBy analysis
* Statistical analysis

### Data Cleaning

* Missing-value handling
* Duplicate detection
* Data validation
* Data-quality assessment

### Exploratory Data Analysis

* Univariate analysis
* Bivariate analysis
* Category analysis
* Segmentation
* Outlier-oriented analysis

### Statistics

* Descriptive statistics
* Correlation analysis
* Distribution analysis
* Quantile-based segmentation

### Data Visualization

* Bar charts
* Histograms
* Scatter plots
* Box plots
* Correlation heatmaps

### Business Analytics

* Product performance analysis
* Pricing analysis
* Discount analysis
* Seller analysis
* Sales analysis
* Customer rating analysis
* Business recommendations

---

# 📝 22. Conclusion

This project demonstrates an end-to-end Python-based data analytics workflow applied to **80,000 Flipkart product listings**.

The analysis progressed from data inspection and cleaning to feature engineering, descriptive statistics, product and category analysis, sales estimation, seller evaluation, segmentation, and correlation analysis.

The findings indicate that estimated revenue is relatively balanced across categories, discount levels do not show a strong relationship with units sold, and customer ratings, delivery time, and return-policy duration have very weak linear relationships with sales volume in this dataset.

Rather than relying on a single metric, the analysis demonstrates the importance of combining **price, discount, sales volume, ratings, seller performance, inventory, and operational variables** when making e-commerce business decisions.

---

## 👤 Author

**Sharya Fatima**

Aspiring Data Analyst | Python | SQL | Power BI | Data Visualization

---

## ⭐ Project Highlights

**80,000+ Products** • **25 Original Variables** • **Python EDA** • **Data Cleaning** • **Feature Engineering** • **Statistical Analysis** • **Business Insights** • **Data Visualization**
