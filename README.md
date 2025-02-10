# Supermarket Billing System

## Overview
The **Supermarket Billing System** is a Java-based application that helps manage supermarket purchases, track customer details, and update product inventories. It connects to a MySQL database using JDBC to store and retrieve product and customer data.

## Features
- View available products and their details.
- Purchase products and update stock automatically.
- Generate bills with GST and discount calculations.
- Store customer details and purchase history in the database.

## Technologies Used
- **Java** (JDK 8+)
- **MySQL** (Database)
- **JDBC** (Database Connectivity)
- **Scanner Class** (For user input handling)

## Database Setup
1. **Create the database:**
   ```sql
   CREATE DATABASE super;
   USE super;
   ```
2. **Create tables:**
   ```sql
   CREATE TABLE products (
       Product_ID INT AUTO_INCREMENT PRIMARY KEY,
       Name_of_product VARCHAR(255) NOT NULL,
       Price_Of_Product FLOAT NOT NULL,
       Qunatity_Available INT NOT NULL
   );

   CREATE TABLE customer (
       id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(255) NOT NULL,
       phone_no INT NOT NULL,
       bill DOUBLE NOT NULL
   );

   CREATE TABLE purchases (
       id INT,
       product_name VARCHAR(255),
       quantity INT,
       total_cost DOUBLE,
       FOREIGN KEY (id) REFERENCES customer(id)
   );
   ```

## How to Run
1. **Compile the Java Program:**
   ```sh
   javac SuperMarket.java
   ```
2. **Run the Program:**
   ```sh
   java SuperMarket
   ```
3. **Follow On-Screen Instructions:**
   - View available products.
   - Purchase items and generate a bill.
   - Enter customer details.

## Example Usage
- **Viewing Products:**
  - Displays a list of available products.
- **Purchasing Products:**
  - User enters product ID and quantity.
  - Total cost is calculated.
  - Stock is updated in the database.
- **Generating Bill:**
  - GST (20%) and Discount (30%) are applied.
  - Final bill amount is displayed.

## Troubleshooting
- Ensure **MySQL is running** and the database `super` is created.
- Verify **JDBC MySQL driver** is installed and added to the project classpath.
- If `java.sql.SQLException` occurs, check **database credentials** in the code.

## Author
- **Yashwanth Raj**

