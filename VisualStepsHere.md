Go to Sportsdata.io and create a free account

You will get an email and at the bottom it says "Launch Developer Portal"

By default it takes you to the NFL, on the left click on NBA

Scroll down until you see "Standings"

You'll "Query String Parameters", the value in the drop down box is your API key.

Copy this string because you will need to paste it later in the script








Step 1: Log into AWS and Open CloudShell Console
Step 2: Create the setup_nba_data_lake.py file
Step 3: In another window, go to GitHub
Copy the contents inside the setup_nba_data_lake.py file to paste in the file you created in the cloudshell console.
Step 4: Configure API key in the Python script.
Press ^X to exit, press Y to save the file, press enter to confirm the file name
Step 5: Create .env file
paste the following line of code into your file, ensure you swap out with your API key
SPORTS_DATA_API_KEY=your_sportsdata_api_key
NBA_ENDPOINT=https://api.sportsdata.io/v3/nba/scores/json/Players
Press ^X to exit, press Y to save the file, press enter to confirm the file name
Step 6: Run the script
In the CLI type
python3 setup_nba_data_lake.py
-You should see the resources were successfully created, the sample data was uploaded successfully and the Data Lake Setup Completed

Step 7: Manually Check For The Resources
In the Search Bar, type S3 and click blue hyper link name
-You should see 2 General purpose bucket named "Sports-analytics-data-lake"

-When you click the bucket name you will see 3 objects are in the bucket

Click on raw-data and you will see it contains "nba_player_data.json"

Click the file name and at the top you will see the option to Open the file

-You'll see a long string of various NBA data

Head over to Amazon Athena and you could paste the following sample query:
SELECT FirstName, LastName, Position, Team
FROM nba_players
WHERE Position = 'PG';
-Click Run -You should see an output if you scroll down under "Query Results"
