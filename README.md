# **Northwind Database Analysis**

This project focuses on exploring and querying the Northwind database, a sample dataset commonly used for learning and testing relational database concepts. The analysis addresses key business questions for the Northwind company, using SQL queries to extract insights related to products, categories, revenue, and employee performance.

## **Overview**

- **Database**: Northwind Database (`northwind.bacpac`)
- **Objective**: Restore the database, answer key management questions, and provide insights based on SQL queries
- **Tools Used**: Azure SQL, SQL Server Management Studio (SSMS)

## **Project Description**

The Northwind database contains information about a company's sales transactions, including products, orders, employees, and customers. The objective of this project is to restore the database from a `.bacpac` file and execute specific queries to address urgent business needs.

## **Installation and Setup**

1. **Restore the Northwind Database**:
   - **Prerequisites**: You need an Azure SQL database or a local SQL Server setup and SQL Server Management Studio (SSMS) installed.
   - **Import the `.bacpac` file**: Download the Northwind database backup (`northwind.bacpac`) and restore it using SSMS.
   - **Steps to Restore**:
     - Open SSMS and connect to your server.
     - Right-click on **Databases** in Object Explorer and select **Import Data-tier Application**.
     - Follow the wizard to upload the `.bacpac` file and restore the database.

2. **Set Up the Project**:
   - Ensure that you have the database properly restored and accessible in SSMS.

## **Usage**

1. **SQL Queries**:
   - Execute the provided SQL scripts to answer the key business questions:
     - **Catalog of all products**: List all products along with their categories and unit prices.
     - **Top-performing product categories**: Identify the categories generating the highest total revenue.
     - **Top-performing employees**: Find the employees handling the most orders.

   Example SQL Query to list products with categories and unit prices:
   ```sql
   SELECT 
       p.ProductName, 
       c.CategoryName, 
       p.UnitPrice
   FROM 
       Products p
   JOIN 
       Categories c ON p.CategoryID = c.CategoryID
   ORDER BY 
       c.CategoryName, p.ProductName;
