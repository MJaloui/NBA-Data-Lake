# NBADataLake
![image](https://github.com/user-attachments/assets/da946492-8d8a-438e-8d3b-e3a00e43ad9f)

## **Project Highlights**
⛹🏾‍♀️ This repository contains the setup_nba_data_lake.py script, which automates the creation of a data lake for NBA analytics using AWS services. 

⛹🏾‍♀️ The script integrates Amazon S3, AWS Glue, and Amazon Athena

⛹🏾‍♀️ It also sets up the infrastructure needed to store and query NBA-related data.

---

## **Capabilities**
**The setup_nba_data_lake.py script performs the following actions:**

🔧 Creates an Amazon S3 bucket to store raw and processed data.

🔧 Uploads sample NBA data (JSON format) to the S3 bucket.

🔧 Creates an AWS Glue database and an external table for querying the data.

🔧 Configures Amazon Athena for querying data stored in the S3 bucket.

# Prerequisites

Go to Sportsdata.io and create a free account

You will get an email and at the bottom it says "Launch Developer Portal"

By default it takes you to the NFL, on the left click on NBA

Scroll down until you see "Standings"

You'll "Query String Parameters", the value in the drop down box is your API key. 

Copy this string because you will need to paste it later in the script

IAM Role/Permissions: Ensure the user or role running the script has the following permissions:

S3: s3:CreateBucket, s3:PutObject, s3:DeleteBucket, s3:ListBucket
Glue: glue:CreateDatabase, glue:CreateTable, glue:DeleteDatabase, glue:DeleteTable
Athena: athena:StartQueryExecution, athena:GetQueryResults

## **Technical Architectures**



---

## **Technologies**

## **Setup Instuctions** 

# Step 1: Log into AWS and Open CloudShell Console

# Step 2: Create the setup_nba_data_lake.py file


# Step 3: In another window, go to [GitHub](https://github.com/MJaloui/NBADataLake)

  - Copy the contents inside the setup_nba_data_lake.py file to paste in the file you created in the cloudshell console.

# Step 4: Configure API key in the Python script.

4. Press ^X to exit, press Y to save the file, press enter to confirm the file name 


# Step 5: Create .env file 

2. paste the following line of code into your file, ensure you swap out with your API key
```bash
SPORTS_DATA_API_KEY=your_sportsdata_api_key
NBA_ENDPOINT=https://api.sportsdata.io/v3/nba/scores/json/Players
```

3. Press ^X to exit, press Y to save the file, press enter to confirm the file name 


# Step 6: Run the script
1. In the CLI type
```bash
python3 setup_nba_data_lake.py
```
-You should see the resources were successfully created, the sample data was uploaded successfully and the Data Lake Setup Completed

# Step 7: Manually Check For The Resources
1. In the Search Bar, type S3 and click blue hyper link name

-You should see 2 General purpose bucket named "Sports-analytics-data-lake"

-When you click the bucket name you will see 3 objects are in the bucket

2. Click on raw-data and you will see it contains "nba_player_data.json"

3. Click the file name and at the top you will see the option to Open the file

-You'll see a long string of various NBA data

4. Head over to Amazon Athena and you could paste the following sample query:
```bash
SELECT FirstName, LastName, Position, Team
FROM nba_players
WHERE Position = 'PG';
```

-Click Run
-You should see an output if you scroll down under "Query Results"

### **Key Takeaways**
✔️ Securing AWS services with least privilege IAM policies.

✔️ Automating the creation of services with a script.

✔️ Integrating external APIs into cloud-based workflows.


### **Opportunities for Growth**
🌱 Automate data ingestion with AWS Lambda

🌱 Implement a data transformation layer with AWS Glue ETL

🌱 Add advanced analytics and visualizations (AWS QuickSight)

