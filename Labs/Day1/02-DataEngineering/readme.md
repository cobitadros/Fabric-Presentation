## Fabric Data Engineering LAB

### Data Wrangling with Spark DataFrame
In this lab, you will learn how to use Spark DataFrame to manipulate data in Fabric. You will use a Jupyter Notebook to create a Spark DataFrame and perform some basic data wrangling tasks.
Get the data from the following link:
[Titantic Passanger List](https://raw.githubusercontent.com/plotly/datasets/master/titanic.csv)

### Step by Step Lab:
Create a Notebook in Fabric and use the following code to read the data into a Pandas DataFrame.
```python
import pandas as pd
df = pd.read_csv('https://raw.githubusercontent.com/plotly/datasets/master/titanic.csv')
display(df)
```

### Use a Notebook to create a Spark DataFrame
Follow the instruction in 02-Notebook.ipynb to experiment with Spark DataFrame in Fabric and get a feel for how to manipulate data in a Spark DataFrame from the Python side.

## S3 Bucket fabricdata.csv 
Follow along if you don't have an Amazon S3 bucket account.


