# NBADataLake

![image](https://github.com/user-attachments/assets/da946492-8d8a-438e-8d3b-e3a00e43ad9f)




## **🔷 Project Highlights 🔷**

⛹🏾‍♀️ This repository contains the setup_nba_data_lake.py script, which automates the creation of a data lake for NBA analytics using AWS 
    services. 

⛹🏾‍♀️ The script integrates Amazon S3, AWS Glue, and Amazon Athena

⛹🏾‍♀️ It also sets up the infrastructure needed to store and query NBA-related data.



## **🔧 Capabilities 🔧**

**The setup_nba_data_lake.py script performs the following actions:**

🔹 Creates an Amazon S3 bucket to store raw and processed data.

🔹 Uploads sample NBA data (JSON format) to the S3 bucket.

🔹 Creates an AWS Glue database and an external table for querying the data.

🔹 Configures Amazon Athena for querying data stored in the S3 bucket.



## **🚨 Technologies 🚨**

🔹 **Cloud Provider**: AWS

🔹 **Core Services**: S3, Glue, Athena

🔹 **Command-Line Tool**: AWS CloudShell

🔹 **Programming Language**: Python 3.x

🔹 **Infrastructure as Code**: Python script for automating AWS resource creation

🔹 **External API**: SportsData.io NBA API

🔹 **Environment Management**: Environment variables for secure API key storage

🔹 **IAM Security**: Least privilege policies for S3, Glue, and Athena

🔹 **Data Querying**: Amazon Athena

🔹 **Data Storage**: Amazon S3 (raw and processed data)

🔹 **Data Cataloging**: AWS Glue



---



## **👀 Instructions 👀**   

**🔹 Prerequisites 🔹**

🔹 Go to Sportsdata.io and create a free account

🔹 IAM Role/Permissions: Ensure the user or role running the script has the following permissions:

🔹 S3: s3:CreateBucket, s3:PutObject, s3:DeleteBucket, s3:ListBucket
  Glue: glue:CreateDatabase, glue:CreateTable, glue:DeleteDatabase, glue:DeleteTable
  Athena: athena:StartQueryExecution, athena:GetQueryResults


### **Steps:**   ➡️❗ [Click Here To View Detailed Visual Steps](https://github.com/MJaloui/NBADataLake/blob/main/VisualStepsHere.md) ❗⬅️

1. Log into AWS and Open CloudShell Console

2. Create the setup_nba_data_lake.py file

3. In another window, go to [GitHub](https://github.com/MJaloui/NBADataLake) and copy the contents inside the setup_nba_data_lake.py file located in the SRC file to paste in the file
        you created in the cloudshell console.

4. Configure API key in the Python script.

5. Create .env file to create variables that store your API Key and NBA endpoint for your scripts.

6. Run the script

7. Manually Check For The Resources, validate the data is there.

8. Head over to Amazon Athena to try a query.

---

### **✔️ Keynotes ✔️**

🔹 Securing AWS services with least privilege IAM policies.

🔹 Automating the creation of services with a script.

🔹 Integrating external APIs into cloud-based workflows.


### **🌱 Opportunities for Growth 🌱**

🔹 Automate data ingestion with AWS Lambda

🔹 Implement a data transformation layer with AWS Glue ETL

🔹 Add advanced analytics and visualizations (AWS QuickSight)

