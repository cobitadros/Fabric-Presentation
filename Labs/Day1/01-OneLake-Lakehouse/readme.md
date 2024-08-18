## Download the OneLake Explorer App

[Download the OneLake Explorer App](https://www.microsoft.com/en-us/download/details.aspx?id=105222)

Run the installer and follow the instructions to install the OneLake Explorer App.
Make sure you see the inclusion of the folder in your Windows Explorer.

## Download the Lakehouse Data from Github

Get the data from the following link: [Lakehouse Data](https://github.com/TheTrainingBoss/Fabric-Presentation/tree/main/Data) by cloning the repo or downloading the zip file repository.

## Exercise the following steps:

- Upload 1 or 2 csv files to a Lakehouse (create one if you don't have one) to the FILES folder. (It is recommended to create a subfolder under Files called something like `Data` and upload the files there.)
- Right click on each csv file and use `Load to Tables` to load the data into a `delta parquet` table in the Lakehouse under `Tables` folder.
- Experiment with the table view in Delta by clicking on any of the generated tables.
- Experiment with the types of columns that got generated for each table.
- Change the view from `Lakehouse` to `SQL Analysis Endpoint` and run a simple SQL query to select all records from a table.

## Sample
I would use the Sales.csv file from the Lakehouse Data folder to load into the Lakehouse and then load it into a table. I would then run a simple SQL query like:
```sql
SELECT PRODUCTLINE, Sum(QUANTITYORDERED) from sales
group by PRODUCTLINE
```