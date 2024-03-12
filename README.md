# Basic BI - Data Warehouse Design Assignment Answer

## Objective
The objective of this assignment is to design a data warehouse (DWH) schema for the Sales dataset. The task involves creating an Entity-Relationship Diagram (ERD) that accurately represents the schema of the chosen dataset.

## Sales Data Warehouse Design Case Study

### Introduction

Company XYZ, a retail corporation, aims to analyze its sales data to gain insights into product performance, customer demographics, and sales trends. To achieve this, Company XYZ has designed a comprehensive data warehouse schema to store and analyze sales-related information.

### Data Warehouse Design

#### Dimension Tables

1. **dim_product**: 
   - `product_id` (Primary Key): Unique identifier for each product.
   - `product_name`: Name of the product.
   - `category`: Category to which the product belongs.

2. **dim_store**: 
   - `store_id` (Primary Key): Unique identifier for each store.
   - `store_name`: Name of the store.
   - `city`: City where the store is located.
   - `state`: State where the store is located.
   - `country`: Country where the store is located.

3. **dim_time**: 
   - `time_id` (Primary Key): Unique identifier for each time record.
   - `date`: Date of the sales transaction.
   - `day_of_week`: Day of the week of the sales transaction.
   - `month`: Month of the sales transaction.
   - `year`: Year of the sales transaction.

4. **dim_sales_name**: 
   - `sales_name_id` (Primary Key): Unique identifier for each salesperson.
   - `sales_name`: Name of the salesperson.
   - `sales_age`: Age of the salesperson.
   - `sales_gender`: Gender of the salesperson.

#### Fact Table

- **fact_sales**: 
   - `sale_id`: Identifier for each sales transaction.
   - `store_id` (Foreign Key): References `dim_store.store_id`.
   - `sales_name_id` (Foreign Key): References `dim_sales_name.sales_name_id`.
   - `time_id` (Foreign Key): References `dim_time.time_id`.
   - `product_id` (Foreign Key): References `dim_product.product_id`.
   - `quantity`: Quantity of the product sold.
   - `price`: Price per unit of the product.

### Schema Description (Star Schema)

![Sales](https://github.com/ikhsannur1996/Basic-BI-Assignment/assets/32507742/caf271d5-46a8-45ae-a735-0c247b9330a7)

In a star schema design, the fact table (e.g., `fact_sales`) sits at the center, surrounded by dimension tables (e.g., `dim_product`, `dim_store`). This design simplifies queries and enhances performance by denormalizing data.

**Star Schema:**
In a Star schema, data is organized into a central fact table surrounded by multiple dimension tables, but unlike the Snowflake schema, these dimension tables are not further normalized. Instead, they directly relate to the fact table.

- **Parents**: The central fact table, `fact_sales`, contains transactional data related to sales.
- **Children**: Dimension tables directly connected to the fact table include `dim_product`, `dim_store`, `dim_time`, and `dim_sales_name`. These dimensions provide details such as product information, store details, time-related attributes, and salesperson details respectively.

## Requirements

### ERD Diagram
Create an ERD representing the chosen dataset's schema.

### Deliverables
- Provide an ERD link to drawsql.

## Evaluation Criteria
Your assignment will be evaluated based on the following criteria:
1. Correct Number of tables
2. Correct table names
3. Correct column number
4. Correct column names
5. Correct data types
