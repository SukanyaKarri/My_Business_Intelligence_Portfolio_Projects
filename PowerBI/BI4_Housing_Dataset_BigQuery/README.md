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

### DAX measures:
YOY
### calculated column:
offer price 
