# Ranking Analysis

---

- Order the values of dimensions by measure.
- Top N performers I Bottom N Performers

<aside>

### Which 5 products generate the highest revenue?

```sql
SELECT TOP 5
    dp.product_name,
    SUM(fs.sales_amount) total_revenue
FROM gold.fact_sales fs
LEFT JOIN gold.dim_products dp
ON fs.product_key = dp.product_key
GROUP BY dp.product_name
ORDER BY total_revenue DESC
```

![Ranking Analysis](sql-data-analytics-project-1/eda-results/ranking-analysis-1.png)

</aside>

<aside>

### What are the 5 worst-performing products in terms of sales?

```sql
SELECT TOP 5
    dp.product_name,
    SUM(fs.sales_amount) total_revenue
FROM gold.fact_sales fs
LEFT JOIN gold.dim_products dp
ON fs.product_key = dp.product_key
GROUP BY dp.product_name
ORDER BY total_revenue ASC
```

![](https://raw.githubusercontent.com/DesrajSingh/image-storage-1/main/sql-data-analytics-project-1/eda-results/ranking-analysis-2.png)

</aside>

# Product Details

| Product | QTY | price |
| --- | --- | --- |
| A | 5 | 90 |
| B | 6 | 15 |
| C | 7 | 65 |