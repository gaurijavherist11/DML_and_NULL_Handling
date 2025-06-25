# DML_and_NULL_Handling – MySQL Project

This repository showcases the use of **Data Manipulation Language (DML)** operations in **MySQL**, along with effective handling of **NULL values**. The database simulates a mini e-commerce system involving customers, products, orders, order items, and payments.

---

## 📦 Tables Involved

- **Customers**: Contains buyer details including optional fields like email, phone, and city.
- **Products**: Stores product information such as name and price.
- **Orders**: Tracks orders placed by customers; some orders may have missing order dates.
- **Order Items**: Connects products to orders with quantity details.
- **Payments**: Captures payment amounts and dates; some records have missing payment dates.

---

## 🔹 1. INSERT Operations

Sample data was inserted into all tables, including scenarios where some fields were deliberately left **NULL** (e.g., missing emails, phone numbers, order dates, and payment dates). This helps simulate real-world situations where user or system data might be incomplete.

---

## 🔸 2. Handling Missing Values

The project demonstrates how databases handle **NULL values**:
- Allowing optional data entry for certain fields
- Using `NULL` where values are unknown or unavailable
- Preparing the database to accept incomplete but valid data entries

---

## ✏️ 3. UPDATE Operations

Several updates were made to:
- Correct missing or incorrect customer emails
- Add missing payment dates
- Update product prices

These updates show how to safely modify existing records, including fields with `NULL` values.

---

## 🗑️ 4. DELETE Operations

Examples include:
- Deleting customers who haven't placed any orders
- Removing incorrectly added order items
- Deleting payments related to cancelled (null-dated) orders

These cases illustrate safe deletion while ensuring database consistency and referential integrity.

---

## 💡 Learning Outcomes

- Understanding of DML operations: **INSERT**, **UPDATE**, **DELETE**
- Proper handling and use of **NULL values**
- Writing queries for real-world use cases with incomplete data
- Maintaining database reliability and accuracy

---

## 🛠 Tools Used

- MySQL 8.x
- MySQL Workbench
- GitHub

---

## 🙋‍♀️ Author

**Gauri Milind Javheri**  
Internship Project – DML & NULL Handling in MySQL



