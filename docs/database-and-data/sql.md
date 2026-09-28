# SQL Cheatsheet 🗄️

A quick reference guide for essential SQL queries, Window Functions, and Data Manipulation statements.

---

## 1. Data Querying Basics

| Action | Query Example |
| :--- | :--- |
| **Select Columns** | `SELECT col1, col2 FROM table_name;` |
| **Distinct Values** | `SELECT DISTINCT status FROM orders;` |
| **Filter Rows** | `SELECT * FROM users WHERE age >= 21 AND country = 'US';` |
| **Pattern Matching** | `SELECT * FROM products WHERE name LIKE 'Pro%';` |
| **In List Filter** | `SELECT * FROM employees WHERE department_id IN (1, 3, 5);` |
| **Range Filter** | `SELECT * FROM sales WHERE sale_date BETWEEN '2026-01-01' AND '2026-06-30';` |
| **Sort Results** | `SELECT * FROM products ORDER BY price DESC, name ASC;` |
| **Limit Output** | `SELECT * FROM logs ORDER BY created_at DESC LIMIT 10 OFFSET 0;` |

---

## 2. Aggregation & Grouping

| Action | Query Example |
| :--- | :--- |
| **Basic Aggregation** | `SELECT COUNT(*), AVG(salary), SUM(revenue) FROM sales;` |
| **Group By** | `SELECT category_id, COUNT(*), AVG(price) FROM products GROUP BY category_id;` |
| **Filter Groups (HAVING)** | `SELECT user_id, SUM(amount) FROM orders GROUP BY user_id HAVING SUM(amount) > 1000;` |

---

## 3. Joins

| Join Type | Query Example | Description |
| :--- | :--- | :--- |
| **INNER JOIN** | `SELECT * FROM orders o INNER JOIN users u ON o.user_id = u.id;` | Returns matching rows in both tables |
| **LEFT JOIN** | `SELECT * FROM users u LEFT JOIN orders o ON u.id = o.user_id;` | All rows from left table + matched right rows |
| **RIGHT JOIN** | `SELECT * FROM orders o RIGHT JOIN users u ON o.user_id = u.id;` | All rows from right table + matched left rows |
| **FULL OUTER JOIN** | `SELECT * FROM table_a a FULL OUTER JOIN table_b b ON a.id = b.id;` | All rows when there is a match in either table |
| **CROSS JOIN** | `SELECT * FROM colors CROSS JOIN sizes;` | Cartesian product of both tables |

---

## 4. Window Functions (Advanced Analytics)

| Function | Query Example | Description |
| :--- | :--- | :--- |
| **ROW_NUMBER** | `ROW_NUMBER() OVER (PARTITION BY dept_id ORDER BY salary DESC)` | Unique sequential integer for each row |
| **RANK** | `RANK() OVER (PARTITION BY dept_id ORDER BY salary DESC)` | Rank with gaps for ties |
| **DENSE_RANK** | `DENSE_RANK() OVER (PARTITION BY dept_id ORDER BY salary DESC)` | Rank without gaps for ties |
| **LAG / LEAD** | `LAG(sales, 1) OVER (PARTITION BY store_id ORDER BY sale_date)` | Access previous/next row value |
| **Running Total** | `SUM(amount) OVER (PARTITION BY user_id ORDER BY order_date)` | Cumulative sum per partition |

---

## 5. CTEs & Subqueries

| Concept | Query Example |
| :--- | :--- |
| **Common Table Expression (CTE)** | `WITH HighValueUsers AS (`<br>&nbsp;&nbsp;`SELECT user_id FROM orders GROUP BY user_id HAVING SUM(amount) > 5000`<br>`)`<br>`SELECT * FROM users WHERE id IN (SELECT user_id FROM HighValueUsers);` |
| **Subquery in WHERE** | `SELECT * FROM employees WHERE salary > (SELECT AVG(salary) FROM employees);` |

---

## 6. Conditional Expressions & Strings

| Action | Query Example |
| :--- | :--- |
| **CASE WHEN** | `SELECT name, CASE WHEN score >= 90 THEN 'A' WHEN score >= 80 THEN 'B' ELSE 'C' END AS grade FROM students;` |
| **COALESCE (Null Fallback)** | `SELECT COALESCE(phone_number, email, 'No Contact') FROM users;` |
| **String Concatenation** | `SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM employees;` |
| **Substring** | `SELECT SUBSTRING(email FROM 1 FOR 5) FROM users;` |

---

## 7. Data Modification (DML & DDL)

| Action | Query Example |
| :--- | :--- |
| **INSERT INTO** | `INSERT INTO users (name, email) VALUES ('Alice', 'alice@example.com');` |
| **UPDATE** | `UPDATE products SET price = price * 1.1 WHERE category = 'Electronics';` |
| **DELETE** | `DELETE FROM logs WHERE created_at < '2025-01-01';` |
| **CREATE TABLE** | `CREATE TABLE users (id SERIAL PRIMARY KEY, name VARCHAR(100), created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP);` |
