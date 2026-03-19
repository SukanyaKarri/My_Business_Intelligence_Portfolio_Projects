# House_mArket_Overview

Dashboard: [link]

--

## Data Architecture

- **Data Source:** CSV
- **Data Warehouse:** Google BigQuery (used for storage and high‑performance querying)
- **Data Transformation (ETL/ELT):** SQL (within BigQuery to clean and aggregate data)
- **Data Visualization:** Power BI (connected via DirectQuery or Import to BigQuery)

--

## Workflow

### Loading the Data from CSV to BigQuery
1. Add file → Select source  
2. Create new dataset (DatasetID, region → OK)  
3. Select table name → Click OK  

### Importing to Power BI
1. Get Data → BigQuery  
2. Establish connection from source  
3. Choose dataset → Load/Transform Data  

--

## Data Profiling

- Checked data types  
- Handled null values (anything <1% empty replaced with most frequent value)  
- No duplicates found (validated using `UNIQ` and `DISTINCT`)  

--

## DAX Measures & Calculated Columns

- **YOY_Sales_Growth**  
  - Used `VAR`, `CALCULATE` with current vs previous year logic  
  - Created a calculated table (`DateTable`) using min/max of date  
  - Duplicated `DateOnly` dimension column with `DATEVALUE` for fact table reference  

- **Calculated Column: Offer Price**  
  - Scatter plot used to compare offer price vs purchase price  

- **Median Sales Price (DAX)**  
  - Bar chart used to check median values by region  

- **Metrics (DAX):**  
  - Units sold for last year & quarter (using `CALCULATE` + `FILTER`)  
  - KPI card visualization  

--

## Page 2: Sales Performance

- **Average SQM per Price by Region** → Donut chart  
- **Total YTD (DAX: `TOTALYTD`)** → Bar chart  
- **Calculated Column: Age of House** → Key Influencer visual (analyzed with SQM prices)  
- **Offer to SQM Ratio (DAX)** → Ratio of offer price and SQM using `DIVIDE`  

--

## Page 3: House Analysis

- Cluster column charts:  
  - Offer price & purchase price  
  - Inflation rate / interest rate yield by house type  

- Line & bar combo chart:  
  - SQM and SQM prices by house type  

- Slicers included:  
  - City, Region, Sales Type, Region (for better filtering and understanding)  

--

