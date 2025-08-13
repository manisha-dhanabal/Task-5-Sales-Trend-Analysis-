# Task 6: Sales Trend Analysis Using Aggregations

## 📌 Objective
Analyze **monthly revenue** and **order volume** from sales data to identify time-based trends.

---

## 🛠 Tools Used
- **Google Colab** (Python + SQLite)
- **Pandas** (DataFrames & SQL results)
- **SQLite3** (In-memory SQL database)

---

## 📂 Dataset
**Table Name:** `online_sales`

| Column       | Type     | Description                          |
|--------------|----------|--------------------------------------|
| `order_id`   | INTEGER  | Unique ID for each order              |
| `order_date` | DATE     | Date of the order (YYYY-MM-DD)        |
| `amount`     | REAL     | Total amount of the order             |
| `product_id` | INTEGER  | Product identifier                    |

---

## 📋 Steps

### 1. Create SQLite Database and Table
```python
import sqlite3
import pandas as pd

# Create in-memory database
conn = sqlite3.connect(":memory:")
cur = conn.cursor()

# Create sales table
cur.execute("""
CREATE TABLE online_sales (
    order_id INTEGER,
    order_date DATE,
    amount REAL,
    product_id INTEGER
)
""")
