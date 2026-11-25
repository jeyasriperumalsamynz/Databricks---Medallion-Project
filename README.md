🚀 Building an End-to-End Data Pipeline with Databricks: The Medallion Architecture Project!

Data quality is everything in Data Engineering. If your raw data is messy, your reports and dashboards will be wrong.
To solve this, I recently built a complete Databricks Medallion Project.

What is Medallion Architecture in Databricks?
The Medallion Architecture is a data-design pattern used in Databricks Data Engineering to improve data quality step-by-step through three layers:
🥉 Bronze Layer (Raw): Data exactly as it is received from the source (in this case, Snowflake). It often contains duplicates, nulls, and incorrect data.
🥈 Silver Layer (Cleaned): Validated, cleaned, and transformed data. Here, I handled data-type casting (e.g., decimals, integers) and calculated metrics like total order amounts.
🥇 Gold Layer (Business Ready): The final target layer. Aggregated, high-quality data partitioned for optimal performance and ready for BI dashboards and analytics.

Project Highlights:
🔹 Connected to Snowflake using the Spark Connector.
🔹 Handled real-world scenarios (working with raw data folders, not just single files).
🔹 Masked sensitive credentials (security first!).
🔹 Orchestrated the full Bronze ➔ Silver ➔ Gold pipeline.
I’ve documented the step-by-step execution guide and uploaded the code scripts.

Try It!
https://github.com/jeyasriperumalsamynz/Databricks---Medallion-Project

EXECUTION STEPS
Step 1: Verify Source      Data (Snowflake)

Step 2: Go to Databricks      -- Create Three Notebooks --
      Bronze, Silver, Gold
https://www.databricks.com/learn/free-edition

Step 3: Open Bronze      Notebook -- Create Catalog
                                      Schema
                                      Volume
Step 4: In the same      Bronze Notebook - Extract Data
      From Snowflake (Source Data) using Spark CONNECTOR
  
Step 5: Create Bronze Orders Table Using Extracted Data
File Name: Code Scripts: BRONZE.ipynb
https://pastebin.com/Pp01S3ce - Run each cell
  
Step 6: Go to Silver Notebook - Create Silver_Order table from bronze table after below processing
cast unit_price as decimal
cast quantity as integer
multiply unit_price * quantity
File Name: Code Scripts: SILVER.ipynb
https://pastebin.com/HV5Q3KcS - Run each cell

Step 7: Go to Gold      notebook - Create gold_order table with partition
              Order      year
              Order      month
File Name: Code Scripts: GOLD.ipynb
https://pastebin.com/VEDHSSTC - Run each cell
  
Step 8: Insert the data      from silver table to Gold table by extracting
              Year      and Month from order date in silver table
              (Dynamic      Partitions)

Step 9: Orchestrate the entire Pipeline

📂 Check out the GitHub repository here:
https://github.com/jeyasriperumalsamynz/Databricks---Medallion-Project
📄 View the full execution steps in the attached PDF!
  
📂 Check out the GitHub repository here:
https://lnkd.in/eM2Bb6wP
📄 View the full execution steps in the attached PDF!
