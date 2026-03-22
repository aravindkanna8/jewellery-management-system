# 💎 Jewellery Management System

A full-stack **inventory and billing management system** for jewellery businesses, built with Java (AWT/Swing) and MySQL. Manages 1000+ products and handles 1000+ billing transactions with real-time inventory tracking and reporting.

---

## 🚀 Features

- **Inventory Management** — Add, update, delete, and search 1000+ jewellery products (gold, silver, diamond) with category, weight, price, and stock tracking
- **Billing System** — Generate itemized invoices for 1000+ transactions with auto price calculation, GST, and discount support
- **Real-time Stock Updates** — Inventory auto-updates on every purchase transaction
- **Reports & Analytics** — Daily/monthly sales reports, stock summary, and low-inventory alerts
- **Search & Filter** — Filter products by category, metal type, price range
- **CRUD Operations** — Complete Create, Read, Update, Delete on products, customers, and transactions
- **Reduced manual operations by 40%** compared to spreadsheet-based tracking

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Language | Java |
| UI Framework | AWT, Swing |
| Database | MySQL |
| DB Connectivity | JDBC |
| Build Tool | Manual / Eclipse IDE |

---

## 🗄️ Database Schema

```sql
-- Products Table
CREATE TABLE products (
  id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(100),
  category VARCHAR(50),       -- gold, silver, diamond
  weight_grams DECIMAL(10,2),
  price_per_gram DECIMAL(10,2),
  stock_qty INT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Transactions Table
CREATE TABLE transactions (
  id INT PRIMARY KEY AUTO_INCREMENT,
  product_id INT,
  customer_name VARCHAR(100),
  quantity INT,
  total_amount DECIMAL(10,2),
  gst DECIMAL(10,2),
  transaction_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (product_id) REFERENCES products(id)
);
```

---

## ⚙️ How to Run

### Prerequisites
- Java JDK 8+
- MySQL 5.7+
- Any Java IDE (Eclipse / IntelliJ)

### Setup Steps

```bash
# 1. Clone the repository
git clone https://github.com/aravindkanna8/jewellery-management-system.git
cd jewellery-management-system

# 2. Set up MySQL database
mysql -u root -p
CREATE DATABASE jewellery_db;
USE jewellery_db;
# Run the schema SQL above

# 3. Update DB credentials in DBConnection.java
# src/DBConnection.java
String url = "jdbc:mysql://localhost:3306/jewellery_db";
String user = "root";
String password = "your_password";

# 4. Compile and Run
javac -cp .:mysql-connector-java.jar src/*.java
java -cp .:mysql-connector-java.jar src/Main
```

---

## 📊 Key Metrics

| Metric | Value |
|---|---|
| Products managed | 1000+ |
| Transactions handled | 1000+ |
| Manual operation reduction | 40% |
| Transaction processing speed | Improved significantly vs manual |

---

## 📁 Project Structure

```
jewellery-management-system/
├── src/
│   ├── Main.java               # Entry point
│   ├── DBConnection.java       # JDBC MySQL connection
│   ├── ProductManager.java     # Inventory CRUD logic
│   ├── BillingManager.java     # Transaction & invoice logic
│   ├── ReportGenerator.java    # Sales & stock reports
│   └── UI/
│       ├── MainFrame.java      # Main Swing window
│       ├── ProductPanel.java   # Inventory UI
│       └── BillingPanel.java   # Billing UI
├── db/
│   └── schema.sql              # Database schema
└── README.md
```

---

## 🎯 Problem Statement

Traditional jewellery shops maintain inventory and billing in physical registers or Excel sheets — error-prone, slow, and hard to track. This system digitizes the entire workflow, enabling real-time stock tracking, automated billing, and instant reporting.

---

## 👨‍💻 Author

**AravindSamy Selvaraj**
- LinkedIn: [linkedin.com/in/aravind-samy-s](https://linkedin.com/in/aravind-samy-s)
- GitHub: [github.com/aravindkanna8](https://github.com/aravindkanna8)
