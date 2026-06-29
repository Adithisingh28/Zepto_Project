# Zepto SQL Project

## Overview
This project involves designing and analyzing a relational database for **Zepto**, a quick-commerce grocery delivery platform. The dataset models product-level inventory data — including pricing, discounts, stock availability, and packaging details — across various grocery categories. Using PostgreSQL, the project covers database design, data cleaning, and exploratory analysis to derive business insights around pricing strategy, inventory management, and discount patterns.

## Objectives
- Design a normalized schema to store SKU-level product data
- Clean and validate data (handle nulls, duplicates, and inconsistent values)
- Analyze pricing and discount trends across product categories
- Identify out-of-stock patterns and inventory gaps
- Calculate revenue potential and margin impact of discounts
- Use SQL aggregations, window functions, and CTEs to answer business questions

## Tech Stack
- PostgreSQL
- pgAdmin 4
- SQL (DDL, DML, joins, aggregations, window functions)

## Database Schema

```sql
CREATE TABLE zepto(
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

| Column | Description |
|---|---|
| `sku_id` | Unique identifier for each product (Primary Key) |
| `category` | Product category (e.g., Fruits, Dairy, Snacks) |
| `name` | Product name |
| `mrp` | Maximum Retail Price |
| `discountPercent` | Discount percentage applied |
| `discountedSellingPrice` | Final selling price after discount |
| `availableQuantity` | Units currently in stock |
| `weightInGms` | Product weight in grams |
| `outOfStock` | Stock availability flag |
| `quantity` | Order/package quantity |

## Business Questions Explored
- Which categories offer the highest average discounts?
- What is the revenue loss due to out-of-stock SKUs?
- Which products have the best price-per-gram value?
- How does discount percentage vary with MRP across categories?
- What's the distribution of stock availability by category?

## How to Run
1. Create the database and run the schema script above in pgAdmin 4 / psql.
2. Import the dataset (CSV) into the `zepto` table.
3. Run the analysis queries from the `queries.sql` file (or your notebook) to explore the insights.
