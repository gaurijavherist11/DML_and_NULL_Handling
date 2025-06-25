# DML_and_NULL_Handling

# 🧾 DML and NULL Handling – MySQL Project

This repository demonstrates practical usage of **Data Manipulation Language (DML)** operations in MySQL, along with **NULL handling**, using an e-commerce-style database with customers, products, orders, order items, and payments.

This is ideal for understanding how to insert, update, delete data while handling missing values correctly and efficiently.

---

## 📦 Tables Involved

- **Customers**: Buyer information (name, email, phone, city)
- **Products**: Product catalog (name and price)
- **Orders**: Tracks orders placed by customers
- **Order_Items**: Links products to orders with quantity
- **Payments**: Tracks payment made for orders

---

## 🔹 1. INSERT INTO Statements (with NULL Handling)

✅ Customers Table

INSERT INTO customers (customer_id, name, email, phone, city)
VALUES 
(1, 'John Smith', 'john.smith@example.com', '555-123-4567', 'New York'),
(2, 'Sarah Johnson', 'sarah.j@example.com', '555-987-6543', 'Chicago'),
(3, 'Michael Brown', NULL, '555-456-7890', 'Los Angeles'),
(4, 'Emily Davis', 'emily.d@example.com', NULL, 'Houston'),
(5, 'Robert Wilson', 'robert.w@example.com', '555-789-0123', NULL);
✅ Products Table
INSERT INTO products (product_id, product_name, price)
VALUES 
(101, 'Laptop', 999.99),
(102, 'Smartphone', 699.99),
(103, 'Headphones', 149.99),
(104, 'Tablet', 399.99),
(105, 'Smartwatch', 199.99);
✅ Orders Table
sql
Copy
Edit
INSERT INTO orders (order_id, customer_id, order_date)
VALUES 
(1001, 1, '2025-01-15'),
(1002, 2, '2025-02-20'),
(1003, 3, '2025-03-10'),
(1004, 1, '2025-04-05'),
(1005, 4, NULL); -- NULL order date
✅ Order Items Table
sql
Copy
Edit
INSERT INTO order_items (order_item_id, order_id, product_id, quantity)
VALUES 
(1, 1001, 101, 1),
(2, 1001, 103, 2),
(3, 1002, 102, 1),
(4, 1003, 104, 1),
(5, 1003, 105, 1),
(6, 1004, 101, 1),
(7, 1005, 103, 3); -- Added by mistake, deleted later
✅ Payments Table
INSERT INTO payments (payment_id, order_id, amount_paid, payment_date)
VALUES 
(5001, 1001, 1299.97, '2025-01-16'),
(5002, 1002, 699.99, '2025-02-21'),
(5003, 1003, 599.98, NULL), -- Payment date missing
(5004, 1004, 999.99, '2025-04-06'),
(5005, 1005, 449.97, '2025-05-15');

🔸 2. Handling NULL Values
This project includes deliberate use of NULL to represent missing or optional data:

Missing emails, phone numbers, cities in the Customers table

Missing order dates in the Orders table

Missing payment dates in the Payments table

This shows how real-world data can have gaps and how to design your database to handle it gracefully.

✏️ 3. UPDATE Statements
-- Update a customer's email
UPDATE customers 
SET email = 'michael.b@example.com' 
WHERE customer_id = 3;

-- Fix missing payment date
UPDATE payments 
SET payment_date = '2025-03-12' 
WHERE payment_id = 5003;

-- Change price of a product
UPDATE products 
SET price = 179.99 
WHERE product_id = 103;

🗑️ 4. DELETE Statements
-- Remove customer with no orders
DELETE FROM customers 
WHERE customer_id = 5 
AND NOT EXISTS (SELECT 1 FROM orders WHERE customer_id = 5);

-- Delete mistakenly added order item
DELETE FROM order_items 
WHERE order_item_id = 7 
AND order_id = 1005;

-- Remove payments for cancelled orders (where order_date is NULL)
DELETE FROM payments 
WHERE order_id IN (SELECT order_id FROM orders WHERE order_date IS NULL);
💡 Learning Objectives
Practice DML operations: INSERT, UPDATE, DELETE

Understand how to work with NULL values in databases

Learn to write safe and accurate SQL queries

Handle real-world data inconsistencies

🛠 Tools Used
MySQL 8.x

MySQL Workbench

GitHub

🙋‍♀️ Author
Gauri Milind Javheri
Internship Project – DML & NULL Handling in MySQL



