# SQL-Waste_Collection_Management_System
Waste Collection Management System is a MySQL-based database project designed to manage customers, drivers, vehicles, collection schedules, waste records, and payments. It demonstrates relational database design, primary and foreign keys, constraints, relationships, data management, and SQL queries for real-world waste collection operations.

---

# Waste Collection Management System

A **MySQL-based Waste Collection Management System** designed to manage and organize waste collection operations through a structured relational database. The project manages customers, vehicles, drivers, collection schedules, waste records, and payments.

It demonstrates practical SQL and database concepts using a real-world waste management scenario.

---

## Project Overview

The **Waste Collection Management System** provides a centralized database for managing day-to-day waste collection activities.

The database connects customers with collection schedules, drivers, and vehicles while maintaining waste collection and payment records. It also includes SQL queries for analyzing operational and financial data.

The database contains six major entities:

* Customers
* Vehicles
* Drivers
* Collection Schedule
* Waste Collection
* Payments

---

## Project Objectives

* Manage customer information efficiently
* Maintain vehicle and driver records
* Schedule waste collection for customers
* Track collected waste and its weight
* Record different types of waste
* Manage customer payments
* Track paid and pending payments
* Analyze waste collection data
* Demonstrate relationships between database tables

---

## Database Structure

### 1. Customers

Stores information about customers and their waste requirements.

**Key attributes:**

* Customer ID
* Customer Name
* Phone
* Email
* Address
* Area
* Waste Type

The table uses `CustomerID` as the Primary Key.

---

### 2. Vehicles

Stores information about waste collection vehicles.

**Key attributes:**

* Vehicle ID
* Vehicle Number
* Vehicle Type
* Capacity
* Status

`VehicleNumber` is defined as a unique field to avoid duplicate vehicle records.

---

### 3. Drivers

Maintains driver information and their assigned vehicles.

**Key attributes:**

* Driver ID
* Driver Name
* Phone
* License Number
* Vehicle ID

The `VehicleID` establishes a relationship between drivers and vehicles using a Foreign Key.

---

### 4. Collection Schedule

Manages scheduled waste collection activities.

**Key attributes:**

* Schedule ID
* Customer ID
* Driver ID
* Collection Date
* Collection Time
* Status

The table connects customers and drivers using Foreign Keys.

---

### 5. Waste Collection

Records details of the waste collected during scheduled pickups.

**Key attributes:**

* Collection ID
* Schedule ID
* Waste Weight
* Waste Type
* Collection Status

`ScheduleID` connects waste collection records with the corresponding collection schedule.

---

### 6. Payments

Stores payment information related to customers.

**Key attributes:**

* Payment ID
* Customer ID
* Amount
* Payment Date
* Payment Mode
* Payment Status

Payment records are linked to customers through `CustomerID`.

---

## Database Relationships

```text
Customers
    │
    ├──────────────► CollectionSchedule
    │                       │
    │                       ├──────► Drivers ──────► Vehicles
    │                       │
    │                       └──────► WasteCollection
    │
    └──────────────► Payments
```

### Relationship Summary

| Relationship                         | Description                                     |
| ------------------------------------ | ----------------------------------------------- |
| Customers → CollectionSchedule       | A customer can have collection schedules        |
| Drivers → CollectionSchedule         | Drivers are assigned to collection schedules    |
| Vehicles → Drivers                   | Vehicles can be assigned to drivers             |
| CollectionSchedule → WasteCollection | Waste is recorded against a collection schedule |
| Customers → Payments                 | Customer payment records are maintained         |

---

## Technologies Used

* **MySQL**
* **SQL**
* **MySQL Workbench / phpMyAdmin**
* **Relational Database Management System (RDBMS)**

---

## SQL Concepts Demonstrated

This project demonstrates several important SQL concepts:

### Database & Table Creation

* `CREATE DATABASE`
* `CREATE TABLE`
* `USE`
* `SHOW TABLES`

### Constraints

* `PRIMARY KEY`
* `FOREIGN KEY`
* `UNIQUE`
* `NOT NULL`
* `AUTO_INCREMENT`

### Data Manipulation

* `INSERT INTO`
* `SELECT`
* `WHERE`
* `ORDER BY`

### Aggregate Functions

* `COUNT()`
* `SUM()`
* `AVG()`
* `MAX()`
* `MIN()`

For example, the project calculates total customers, total waste, average waste, total paid revenue, pending payments, highest waste quantity, and lowest waste quantity.

### GROUP BY & HAVING

The project analyzes customers by area using `GROUP BY` and filters grouped results using `HAVING`.

### JOIN Operations

The project uses `INNER JOIN` to combine related information such as customers with collection schedules and drivers with vehicles.

### Subqueries

Subqueries are used for analytical queries such as finding payments above the average payment amount and identifying the highest waste collection.

### Window Functions

The project demonstrates:

* `RANK()`
* `DENSE_RANK()`

These are used to rank waste collection records according to waste weight.

---

## Sample Analysis

The project can answer questions such as:

* How many customers are registered?
* What is the total amount of waste collected?
* What is the average waste weight?
* What is the highest waste collection?
* What is the lowest waste collection?
* How much revenue has been paid?
* How many payments are still pending?
* Which areas have more customers?
* Which payments have the highest amounts?
* Which waste collections have the highest rankings?
* Which payments are above the average payment amount?

---

## Project Structure

```text
Waste-Collection-Management-System/
│
├── Waste_Collection_Project.sql
│
└── README.md
```

---

## How to Run the Project

### Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/waste-collection-management-system.git
```

### Step 2: Open MySQL

Open **MySQL Workbench**, **phpMyAdmin**, or another MySQL-compatible SQL environment.

### Step 3: Import the SQL File

Open:

```text
Waste_Collection_Project.sql
```

### Step 4: Execute the Script

Run the complete SQL script.

The script creates the `WasteCollectionDB` database and its required tables.

### Step 5: Verify the Database

```sql
USE WasteCollectionDB;

SHOW TABLES;
```

---

## Future Enhancements

The project can be further enhanced by developing a web-based application with:

* Admin Dashboard
* Customer Login
* Driver Management
* Vehicle Tracking
* Collection Notifications
* Payment Dashboard
* Waste Analytics Dashboard
* Area-wise Collection Reports
* Monthly Revenue Reports
* Online Payment Integration

---

## Learning Outcomes

Through this project, I gained practical experience in:

* Relational Database Design
* MySQL Database Management
* SQL Query Writing
* Primary & Foreign Key Relationships
* Database Constraints
* Aggregate Functions
* GROUP BY & HAVING
* JOIN Operations
* Subqueries
* Window Functions
* Data Analysis using SQL

---

## Author

**Apurvesh Buwa**

---

## License

This project is created for **educational and portfolio purposes**.
