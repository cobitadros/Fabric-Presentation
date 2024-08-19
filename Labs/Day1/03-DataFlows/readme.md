## Fabric Data Flows Gen 2 LAB

### The data source is:
https://services.odata.org/v4/northwind/northwind.svc

### Step by step Lab:

- Choose `Orders` and `Order_Details` tables and create a data flow to join them.
- Remove the Object based columns from both tables in PowerQuery
- Add Data Destination to the data flow and save the data to the current Lakehouse
- You will get 3 errors on the 3 Date Type columns
- Fix the Date Type colum on the `Orders` table by transforming the column type to DateTime
- Publish the Data Flow to the Workspace for BOTH tables (not only one, remember to publish both tables)
  


