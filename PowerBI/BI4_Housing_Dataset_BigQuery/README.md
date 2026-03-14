## Analysis of Housing Dataset 

- Data Source: (CSV)
- Data Warehouse: Google BigQuery (used for storage and high-performance querying).
- Data Transformation (ETL/ELT): SQL (used within BigQuery to clean and aggregate data).
- Data Visualization: Power BI (connected via DirectQuery or Import to BigQuery).

### Loading the Data from CSV to BigQuery
- Add file--> Select source--> create new dataset ( in pop up --give datasetID --region-- ok) -- selet name for table click ok

### Importing to PowerBI
- Get Data--> BigQuery--> Establish the connection from source--> chose the dataset-->load/Transform Data

### Data Profiling
- Check Data Types
- Handle null values (anything <1 percent empty values replaced them with most frequent value)
- No duplicates found (validated usign uniq and distinct values)

### DAX measures & Calculted columns:  [Refer to notepad scripts for Measures]
YOY_Sales_Gowth- Used the var ,calculate methods taking ref of curr-prev/prev logic " here max-latest year is considered as current year"
- Created a Calculate table ("DateTable") for this using min and max of date
- used a duplicated record of dateonly dimension column with datevalue in calcutted table which is create from existing date column of fact table
### calculated column:
offer price - scatter plot is used for newly created offer price in compariosn to purchase price, scatter plot is used becoz it helps in understaning relation between 2 variables


