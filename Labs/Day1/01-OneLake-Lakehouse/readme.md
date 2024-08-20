## Download the Lakehouse Data from Github

Get the data from the following link: [Lakehouse Data](https://github.com/TheTrainingBoss/Fabric-Presentation/tree/main/Data) by cloning the repo or downloading the zip file repository.

## Exercise the following steps:

- Upload 1 or 2 csv files to a Lakehouse (create one if you don't have one) to the FILES folder. (It is recommended to create a subfolder under Files called something like `Data` and upload the files there.)
- Right click on each csv file and use `Load to Tables` to load the data into a `delta parquet` table in the Lakehouse under `Tables` folder.
- Experiment with the table view in Delta by clicking on any of the generated tables.
- Experiment with the types of columns that got generated for each table.
- Change the view from `Lakehouse` to `SQL Analysis Endpoint` and run a simple SQL query to select all records from a table.

## Sample
I would use the Items.csv file from the Lakehouse Data folder to load into the Lakehouse and then load it into a table. Rename the Delta file to products.
I would then run a simple SQL query like:
```sql
SELECT Category, AVG(WholesaleCost) as [AVG Wholesale Cost]
From products
group by Category
```
## Using MS Sql Server Management Studio to access the Delta Files
- Open the SQL Studio Management Studio
- Use the connection string from your `SQL Analytics Endpoint` (you can find it by clicking on the gear in the upper left corner of the SQL Analytics Endpoint page)
- Login with EntraID with MFA
- Issue the same select statement from above to try teh access from the SQL Server Management Studio.

## Download the OneLake Explorer App

[Download the OneLake Explorer App](https://www.microsoft.com/en-us/download/details.aspx?id=105222)

Run the installer and follow the instructions to install the OneLake Explorer App.
Make sure you see the inclusion of the folder in your Windows Explorer.

## S3 Bucket fabricdata.csv 
Follow along if you don't have an Amazon S3 bucket account.