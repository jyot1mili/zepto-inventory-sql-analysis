# Zepto Inventory SQL Analysis

A SQL-based data analytics project focused on exploring and analyzing inventory data from Zepto, one of India’s leading quick-commerce platforms. This project demonstrates practical SQL skills including data cleaning, exploratory analysis, and business insight generation using PostgreSQL.

## Project Objective

The goal of this project is to analyze e-commerce inventory data to uncover useful business insights related to:

* Product pricing
* Discounts
* Inventory availability
* Category-wise performance
* Revenue opportunities

The project simulates a typical workflow followed by data analysts while working with retail or e-commerce datasets.

---

## Dataset Information

The dataset contains product-level inventory information scraped from Zepto product listings.

Each row represents a product SKU with attributes such as:

* Product name
* Category
* MRP
* Discount percentage
* Selling price
* Available quantity
* Product weight
* Stock availability

---

## Tools & Technologies

* PostgreSQL
* SQL
* pgAdmin
* CSV Dataset

---

## Database Schema

```sql
CREATE TABLE zepto (
    sku_id SERIAL PRIMARY KEY,
    category VARCHAR(120),
    name VARCHAR(150) NOT NULL,
    mrp NUMERIC(8,2),
    discountPercent NUMERIC(5,2),
    availableQuantity INTEGER,
    discountedSellingPrice NUMERIC(8,2),
    weightInGms INTEGER,
    outOfStock BOOLEAN,
    quantity INTEGER
);
```

---

## Project Workflow

### 1. Data Import

* Imported CSV dataset into PostgreSQL using pgAdmin
* Handled UTF-8 encoding issues during import

### 2. Data Exploration

Performed initial exploratory analysis to understand the dataset:

* Total record count
* Distinct product categories
* Null value checks
* In-stock vs out-of-stock products
* Duplicate product listings

### 3. Data Cleaning

* Removed invalid entries with zero pricing
* Standardized pricing values
* Improved data consistency for analysis

### 4. Business Analysis

Generated insights using SQL queries such as:

* Top discounted products
* High-value out-of-stock items
* Estimated category revenue
* Products with low discounts and high MRP
* Category-wise average discount analysis
* Price-per-gram comparison
* Inventory weight distribution

---

## Key Insights

* Certain categories offered significantly higher average discounts compared to others.
* Multiple products appeared under different package sizes and quantities.
* Some high-MRP products were unavailable despite strong potential revenue contribution.
* Price-per-gram analysis helped identify better-value products for customers.

---

## Sample Analysis Queries

### Top Discounted Products

```sql
SELECT name, mrp, discountPercent
FROM zepto
ORDER BY discountPercent DESC
LIMIT 10;
```

### Category-wise Revenue Estimation

```sql
SELECT category,
       SUM(discountedSellingPrice * availableQuantity) AS estimated_revenue
FROM zepto
GROUP BY category
ORDER BY estimated_revenue DESC;
```

---

## How to Run

1. Clone the repository

```bash
git clone <your-repo-link>
```

2. Create a PostgreSQL database

3. Import the dataset CSV file

4. Run the SQL queries from the project file

---

## Learning Outcomes

Through this project, I practiced:

* Writing complex SQL queries
* Data cleaning using SQL
* Aggregate and analytical functions
* Business-focused data analysis
* Working with real-world structured datasets

---

## Future Improvements

* Build interactive dashboards using Power BI
* Add Python-based analysis
* Perform trend and category forecasting
* Automate reporting workflow

---


```
```
