# 🛒 Zepto E-commerce Inventory Analysis (SQL) Project
    This project uses a real-world Zepto Inventory dataset to simulate the end-to-end workflow of a professional 
    e-commerce data analyst. You will transform raw scraped data into actionable business insights, covering 
    everything from initial exploration to strategic decision-making. It's a practical showcase of how  to 
    handle quick-commerce challenges using authentic industry data.
    
    This project is perfect for:
    -> Anyone learning SQL hands-on.
    -> Preparing for interviews in retail, e-commerce or product analytics.
## Project Overview:
    This project walks you through the life of a data analyst using SQL to:
    1.Turn messy warehouse data into a polished inventory system.
    2.Implement data cleaning to handle null values, remove invalid entries and convert pricing from paise to rupees.
    3.Write queries to track sales and stock, pricing, inventory, stock availability, revenue and more.
## Dataset Overview:
   This data comes from Zepto's actual listings on Kaggle, giving you a taste of real-world e-commerce files. It tracks 
   every single item( Stock Keeping Unit),so you wil see the same product name popup multiple times if it 
   comes in different sizes or deals. This messy overlap is exactly what professional analyst have to organise and make sense of everyday.
 
 
 COLUMNS:
 
-sku_id: Unique identifier for each product entry (Synthetic Primary Key)

  -name: Product name as it appears on the app
  
  -category: Product category like Fruits, Snacks, Beverages, etc.
  
  -mrp: Maximum Retail Price (originally in paise, converted to ₹)
  
  -discountPercent: Discount applied on MRP
  
  -discountedSellingPrice: Final price after discount (also converted to ₹)
  
  -availableQuantity: Units available in inventory
  
  -weightInGms: Product weight in grams
  
  -outOfStock: Boolean flag indicating stock availabilityquantity: Number of units per package (mixed with grams for loose produce)
# Project Workflow:
  Here is step by step procedure of what we do in this project.
## 1.Database and Table creation
  We start creating a SQL table with appropriate datatypes
  
  CREATE TABLE zepto (
  
  sku_id SERIAL PRIMARY KEY,
  
  category VARCHAR(120),
  
  name VARCHAR(150) NOT NULL,
  
  mrp NUMERIC(8,2),
  
  discountPercent NUMERIC(5,2),
  
  availableQuantity INTEGER,
  
  discountedSellingPrice NUMERIC(8,2),
  
  weightInGms INTEGER,
  
  outOfStock BOOLEAN,
  
  quantity INTEGER
  
);
## 2.Data Import
  =>Loaded CSV using pgAdmin's import feature.
  
  =>Faced encoding issues (UTF-8 error), which were fixed by saving the CSV file using CSV UTF-8 format.
## 3.Data Exploration
 =>Counted the total number of records in the dataset.

 =>Viewed a sample of the dataset to understand structure and content.

 =>Checked for null values across all columns.

 =>Identified distinct product categories available in the dataset.

 =>Compared in-stock vs out-of-stock product counts.

 =>Detected products present multiple times, representing different SKUs.
## 4.Data Cleaning
 =>Identified and removed rows where MRP or discounted selling price was zero.

 =>Converted mrp and discountedSellingPrice from paise to rupees for consistency and readability.
## 5.Business Insights
=>Found top 10 best-value products based on discount percentage

=>Identified high-MRP products that are currently out of stock

=>Estimated potential revenue for each product category

=>Filtered expensive products (MRP > ₹500) with minimal discount

=>Ranked top 5 categories offering highest average discounts

=>Calculated price per gram to identify value-for-money products

=>Grouped products based on weight into Low, Medium, and Bulk categories

=>Measured total inventory weight per product category
 












