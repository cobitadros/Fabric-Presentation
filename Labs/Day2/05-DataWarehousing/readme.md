## Fabric Data Warehousing LAB

### SQL for creating Tables:
```sql
DROP TABLE IF EXISTS [dbo].[dimension_city];
CREATE TABLE [dbo].[dimension_city]
(
            [CityKey] [INT] NULL,
            [WWICityID] [INT] NULL,
            [City] [VARCHAR](8000) NULL,
            [StateProvince] [VARCHAR](8000) NULL,
            [Country] [VARCHAR](8000) NULL,
            [Continent] [VARCHAR](8000) NULL,
            [SalesTerritory] [VARCHAR](8000) NULL,
            [Region] [VARCHAR](8000) NULL,
            [Subregion] [VARCHAR](8000) NULL,
            [Location] [VARCHAR](8000) NULL,
            [LatestRecordedPopulation] [BIGINT] NULL,
            [ValidFrom] [DATETIME2](6) NULL,
            [ValidTo] [DATETIME2](6) NULL,
            [lineagekey] [INT] NULL
);
```
```sql
DROP TABLE IF EXISTS [dbo].[dimension_customer];
CREATE TABLE [dbo].[dimension_customer]
(
        [CustomerKey] [INT] NULL,
        [WWICustomerID] [INT] NULL,
        [Customer] [VARCHAR](100) NULL,
        [BillToCustomer] [VARCHAR](100) NULL,
        [Category] [VARCHAR](50) NULL,
        [BuyingGroup] [VARCHAR](50) NULL,
        [PrimaryContact] [VARCHAR](50) NULL,
        [PostalCode] [VARCHAR](10) NULL,
        [ValidFrom] [DATETIME2](6) NULL,
        [ValidTo] [DATETIME2](6) NULL,
        [LineageKey] [INT] NULL
    );
```

```sql
DROP TABLE IF EXISTS [dbo].[dimension_date];
CREATE TABLE [dbo].[dimension_date]
(
    [Date] [DATE] NULL,
    [DayNumber] [INT] NULL,
    [Day] [VARCHAR](10) NULL,
    [Month] [VARCHAR](10) NULL,
    [ShortMonth] [VARCHAR](5) NULL,
    [CalendarMonthNumber] [int] NULL,
    [CalendarMonthLabel] [VARCHAR](20) NULL,
    [CalendarYear] [INT] NULL,
    [CalendarYearLabel] [VARCHAR](10) NULL,
    [FiscalMonthNumber] [INT] NULL,
    [FiscalMonthLabel] [VARCHAR](20) NULL,
    [FiscalYear] [INT] NULL,
    [FiscalYearLabel] [VARCHAR](10) NULL,
    [IsoWeekNumber] [INT] NULL
);
```
```sql
DROP TABLE IF EXISTS [dbo].[fact_sale];
CREATE TABLE [dbo].[fact_sale]
(
    [SaleKey] [BIGINT] NULL,
    [CityKey] [INT] NULL,
    [CustomerKey] [INT] NULL,
    [BillToCustomerKey] [INT] NULL,
    [StockItemKey] [INT] NULL,
    [InvoiceDateKey] [DATETIME2](6) NULL,
    [DeliveryDateKey] [DATETIME2](6) NULL,
    [SalesPersonKey] [INT] NULL,
    [WWIInvoiceID] [INT] NULL,
    [Description] [VARCHAR](8000) NULL,
    [Package] [VARCHAR](8000) NULL,
    [Quantity] [INT] NULL,
    [UnitPrice] [DECIMAL](18, 2) NULL,
    [TaxRate] [DECIMAL](18, 3) NULL,
    [TotalExcludingTax] [DECIMAL](29, 2) NULL,
    [TaxAmount] [DECIMAL](38, 6) NULL,
    [Profit] [DECIMAL](18, 2) NULL,
    [TotalIncludingTax] [DECIMAL](38, 6) NULL,
    [TotalDryItems] [INT] NULL,
    [TotalChillerItems] [INT] NULL,
    [LineageKey] [INT] NULL,
    [Month] [INT] NULL,
    [Eear] [INT] NULL,
    [Quarter] [INT] NULL
);	
```

### Data sources:
COPY INTO [dbo].[dimension_city] FROM 'https://azuresynapsestorage.blob.core.windows.net/sampledata/WideWorldImportersDW/tables/dimension_city.parquet' 
WITH (file_type = 'PARQUET');

COPY INTO [dbo].[dimension_customer] FROM 'https://azuresynapsestorage.blob.core.windows.net/sampledata/WideWorldImportersDW/tables/dimension_customer.parquet' 
WITH (file_type = 'PARQUET');   

COPY INTO [dbo].[dimension_date] FROM 'https://azuresynapsestorage.blob.core.windows.net/sampledata/WideWorldImportersDW/tables/dimension_date.parquet' 
WITH (file_type = 'PARQUET');

COPY INTO [dbo].[fact_sale] FROM 'https://azuresynapsestorage.blob.core.windows.net/sampledata/WideWorldImportersDW/tables/fact_sale.parquet'
WITH (file_type = 'PARQUET');