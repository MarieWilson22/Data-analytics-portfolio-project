sql
-- Total sales by month
SELECT strftime('%Y-%m', order_date) AS month,
       SUM(total_amount) AS total_sales
FROM orders
GROUP BY month
ORDER BY month;

-- Top 5 products
SELECT product_name, SUM(quantity) AS total_sold
FROM sales
GROUP BY product_name
ORDER BY total_sold DESC