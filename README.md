# Sales ETL Project
The Sales ETL Project is an Extract, Transform, and Load (ETL) pipeline developed using SQL Server Integration Services (SSIS). This project processes sales data from an Excel file source and loads it into a star schema in an SQL Server database. It incorporates advanced ETL features such as delta loading, incremental loading, Slowly Changing Dimensions (SCD), and data transformation tasks to ensure efficient and reliable data processing.
## Project Features
### Star Schema Design:

#### **Fact Table:**
  * SalesFact: Stores sales transaction data with references to dimension tables.

#### **Dimension Tables:**
  - _DateDimension:_ Stores calendar dates with relevant attributes.
    
  + _CustomerDimension:_ Contains customer data with Type 2 Slowly Changing Dimensions (SCD).
  
  * _ProductDimension:_ Includes detailed product information.
### ETL Processes:

1- **SCD Type 2 Implementation:**
Tracks historical changes in customer data in the CustomerDimension table.

2- **Delta Load:**
Updates only new or modified records in the ProductDimension table.

3- **Incremental Load:**
Inserts new data into the SalesFact table without duplicating existing records.

4- **Data Transformation:**
Calculates derived columns, including:
  
  * _Total Sales Amount:_ `Unit Price × Quantity`
  + _Expiry Status:_ `Active` or `Expired` based on the expiry date.
  - _Customer Loyalty Tier:_ Categorizes customers as:
  `Bronze` (low spending)
  `Silver` (medium spending)
  `Gold` (high spending)
  * _Order Priority:_ Classifies orders as `High` or `Normal` based on order quantity.
  + _Product Age:_ Calculates the number of days since the product became effective.
  + _Discount Category:_ Categorizes discounts as:
  `No Discount`
  `Low`
  `Medium`
  `High`

## Technologies Used
- ETL Tool: SQL Server Integration Services (SSIS)
* Database Management: SQL Server Management Studio (SSMS)
+ Source Data: Microsoft Excel

### Project Structure
* **Source Data:**
Located in the data folder. This includes the sales data Excel file.
- **ETL Packages:**
SSIS packages handling data extraction, transformation, and loading processes.
+ **Destination Tables:**
SQL Server database designed as a star schema.

## Author
[**Fatema Samir**](https://github.com/FatemaSamir)
