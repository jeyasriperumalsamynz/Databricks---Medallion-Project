DATABRICKS – MEDALLION PROJECT
https://github.com/jeyasriperumalsamynz/Databricks---Medallion-Project

EXECUTION STEPS
1.	Verify Source Data (Snowflake)
2.	Go to Databricks -- Create Three Notebooks --
a.	Bronze, Silver, Gold
Try: https://www.databricks.com/learn/free-edition

3.	Open Bronze Notebook -- Create Catalog
   				Schema
    				Volume
Try: Code Scripts: BRONZE.ipynb
https://pastebin.com/Pp01S3ce

4.	In the same Bronze Notebook - Extract Data
From Snowflake (Source Data) using Spark CONNECTOR
# NOTE: Snowflake credentials have been masked for security. 
# To run this code, please download the source data from GitHub: [Insert GitHub Link Here]
spark.read.format("snowflake").option("sfURL","XXXXX-ci54681.snowflakecomputing.com").option("sfAccount"," XXXXXXX ").option("sfUser","XXXXXXX").option("sfPassword"," XXXXXXX @uk").option("sfDatabase","XXXXX").option("sfSchema","XXXXXX").option("sfRole","XXXXXX").option("sfWarehouse","XXXXXX").option("dbtable","srctab").load().write.mode("overwrite").parquet("/Volumes/procat/proschema/provolume/snowflake_orders")
# Here is the actual code. Since I cannot share my Snowflake username and password, I have masked them with 'XXXXX'. Instead, I will provide a link to download the source data from GitHub. Create Bronze Orders Table Using Extracted Data.

Raw data from GitHub:https://github.com/jeyasriperumalsamynz/Databricks---Medallion-Project/tree/main/2.%20Raw%20Data
5.	Create Bronze Orders Table Using Extracted Data

6.	Go to Silver Notebook - Create Silver_Order table from bronze table
after below processing
i.	cast unit_price as decimal
cast quantity as integer
multiply unit_price * quantity

Try: Code Scripts: SILVER.ipynb
https://pastebin.com/HV5Q3KcS

7.	Go to Gold notebook - Create gold_order table with partition
 	Order year
 	Order month
Try: Code Scripts: GOLD.ipynb
https://pastebin.com/VEDHSSTC

8.	Insert the data from silver table to Gold table by extracting
 	Year and Month from order date in silver table
 	(Dynamic Partitions)
9.	Orchestrate the entire Pipeline


How to open the (Code Scripts) .ipynb file on your PC or Run the Pastebin code
1. Open your web browser and go to your Databricks workspace.
2. Go to the folder where you want the notebook.
3. Click the Import button (or right-click in the folder and select Import).
4. Select the .ipynb file you just downloaded.
5. Click on the newly imported notebook and run one by one
6. Download clean data Results
