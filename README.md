### Guided Capstone Step 1: Database Table Design Diagram

#### Overview
This project outlines the design and architecture of a database table system that ingests, processes, and stores stock exchange data. 
The data pipeline encompasses various stages, from data ingestion to final analytical ETL processes, handling different data formats 
(JSON and CSV) and categorizing the ingested data into accepted and rejected sets.

#### Data Source
The source data for this project consists of randomly generated stock exchange data, including:
- Trades: Records indicating transactions of stock shares between broker-dealers.
- Quotes: Records updating the best bid/ask price for a stock symbol on a specific exchange.

#### Data Pipeline Components
The data pipeline is composed of the following stages:

Data Ingestion:
Source Data: JSON and CSV files containing stock exchange data is ingested as source1.json and source2.csv.
Ingestion Mechanism: Data is ingested into the system through python, pyspark read files handling both JSON and CSV formats.

Data Categorization:
Accepted JSON: JSON files that pass validation checks.
Rejected JSON: JSON files that fail validation checks.
Accepted CSV: CSV files that pass validation checks.
Rejected CSV: CSV files that fail validation checks.

Database Loading:
EOD Load Database: The accepted data is stored in a structured database, partitioned by trade and quote data. The partitioned data (based on date, trade and quote) is stored as parquet files on the Azure cloud.
The cloud services like Azure Blob is used to further perform the analytical tasks.

Analytical ETL:
ETL Process: Transformations and load processes are applied to prepare the data for analytical use.

