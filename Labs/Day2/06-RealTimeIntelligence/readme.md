## Fabric Real Time Intelligence LAB

### Data source:
https://services.odata.org/v4/northwind/northwind.svc
https://raw.githubusercontent.com/MicrosoftLearning/dp-data/main/orders.csv

// Use "take" to view a sample number of records in the table and check the data.
Stocks
| take 100

// See how many records are in the table.
Stocks
| count

// This query returns the number of ingestions per hour in the given table.
Stocks
| summarize IngestionCount = count() by bin(ingestion_time(), 1h)

Stocks
| where Ticker == "MSFT"
|project Close, Date
|order by Date desc
| render timechart 