I’ve written it so it explains your Python + SQL Server data cleansing project clearly and is friendly for people who might try to run it.
# Python and SQL Server Data Cleansing Project

## 📌 Project Overview
This project demonstrates an **ETL (Extract, Transform, Load)** process using **Python (Jupyter Notebook)** and **SQL Server**.  
The goal is to:
1. **Read** a CSV file from a source folder.
2. **Clean** the data in Python (remove duplicates, trim whitespace, handle missing values).
3. **Import** the cleaned data into a SQL Server table.
4. **Clean further** inside SQL Server using SQL queries.
5. **Export** the final cleaned dataset to a new CSV file.
6. **Move** the original file to an `Imported` folder once processed.

---

## ⚙️ Requirements

### Python Libraries
Make sure you have these installed:
```bash
pip install pandas pyodbc
SQL Server
SQL Server running locally or remotely.

ODBC Driver 17 for SQL Server installed.

Example connection details:


 ETL Workflow
1. Extract
The script reads the first CSV found in the source folder.

Example read code:
df = pd.read_csv("sales_data.csv", parse_dates=["OrderDate"])

2. Transform (Python)
Remove duplicates

Drop rows with missing key fields

Trim whitespace from string columns

3. Load to SQL Server
Create table if it does not exist

Insert cleaned data into SQL Server

4. Transform (SQL Server)
Remove invalid rows (e.g., negative quantities or prices)

Apply additional data cleansing rules

5. Export Clean CSV
Query cleaned data from SQL Server

Save it to the CleanedFile folder with a timestamp

6. Archive Original File
Move processed CSV to the Imported folder

📊 Example Output
Before Cleansing (Python): 500 rows, with duplicates and null values

After Cleansing (SQL): 480 valid rows

Final CSV saved in CleanedFile with filename:\
