1. Go to Sportsdata.io and create a free account



2. Click "API Free Trail"
![image](https://github.com/user-attachments/assets/4bf332c5-f303-4ad5-9576-97616c8e4cb3)



3. Click "SportsDataIO API Free Trial"
![image](https://github.com/user-attachments/assets/fe09198d-75db-4638-a77d-78d39a49fcd7)



4. Fill out all of the information asked for the free trial and click "Submit".
![image](https://github.com/user-attachments/assets/92916034-cb25-499a-aa62-8f39a77be52b)
![image](https://github.com/user-attachments/assets/758853c4-0dcd-4699-970e-3fa5e038edeb)



5. You will get an email and at the bottom it says "Launch Developer Portal"
![image](https://github.com/user-attachments/assets/a19fcea7-e8dd-4349-af9e-f2922616cb11)
![image](https://github.com/user-attachments/assets/292a8de8-fbca-4034-b8bb-d0331911f2fb)



6. By default it takes you to the NFL, on the left click on NBA
![image](https://github.com/user-attachments/assets/0cba64fe-e369-4f44-ab87-26a149d726eb)
![image](https://github.com/user-attachments/assets/f24a2a60-bc9d-44ae-905e-1e6c772fd313)



7. Scroll down until you see "Standings"
![image](https://github.com/user-attachments/assets/25f05463-483a-442f-9ce5-557dda71217c)



8.You'll "Query String Parameters", the value in the drop down box is your API key, copy this string because you will need to paste it later in the script.
![image](https://github.com/user-attachments/assets/e64f7b49-3e43-4b0d-9420-4ee51e17852c)



9. Log into AWS and Open CloudShell Console on the bottom left.
![image](https://github.com/user-attachments/assets/b618e0a0-4922-495e-b2e5-a4027c9cbd3d)
![image](https://github.com/user-attachments/assets/f6309918-685c-43a9-8e8e-56bb57cd3f09)




10. Create a python file with nano command to add your script, name it setup_nba_data_lake.py  (or whatever you want to name it).

Enter cmd:
```bash
nano setup_nba_data_lake.py
```

![image](https://github.com/user-attachments/assets/3e0277d4-dc08-4ae3-a5c6-8a34e592f9cf)
![image](https://github.com/user-attachments/assets/dd4cff07-de75-4a27-bb3e-725563dbada2)




11. In another window, go to src/setup_nba_data_lake.py in [my GitHub](https://github.com/MJaloui/NBADataLake/blob/main/src/setup_nba_data_lake.py) and
Copy the contents inside the setup_nba_data_lake.py file to paste in the file you created in the cloudshell console.

![image](https://github.com/user-attachments/assets/d379cc04-9e6d-4d50-98fd-e7093f59ebdd)
![image](https://github.com/user-attachments/assets/7b17473f-3248-4b21-8857-6eb24c9cb3d4)



12. Go back to Python script and configure API key, endpoint, and remove "os.getenv" next to "api_key =" and "nba_endpoint =". Remove the 
    parenthesis as well.

     Berfore: api_key = os.getenv("SPORTS_DATA_API_KEY")  # Get API key from .env
        
              nba_endpoint = os.getenv("NBA_ENDPOINT")  # Get NBA endpoint from .env

      After:  api_key = "Insert_Your_Key_Here"  # Get API key from .env
          
              nba_endpoint = "Insert_your_endpoint_URL_Here"  # Get NBA endpoint from .env 
          
![image](https://github.com/user-attachments/assets/1bb70fec-430b-4d10-a66f-f5e5a3b9e6a9)
![image](https://github.com/user-attachments/assets/155737fa-9076-4ad6-9150-2d5784f3f84c)
![image](https://github.com/user-attachments/assets/75a4e73f-46f1-4d04-bf80-6a34b72ad4cd)




13. Configure the "bucket_name" so it's unique. I added my GitHub username in front of what is already there.

    Before: bucket_name = "sports-analytics-data-lake"

    After: bucket_name = "mjaloui-sports-analytics-data-lake"

![image](https://github.com/user-attachments/assets/7a476654-67df-4a2e-a9e3-40503fc32d2a)




14. On your keyboard press "^X" (ctrl+x) to exit, press "Y" to save the file, press "Enter" to confirm the file name. Look on the bottom left 
    to verify you are entering the right thing.

![image](https://github.com/user-attachments/assets/cc0037f3-d7bf-49ee-a891-3c4d6834c621)
![image](https://github.com/user-attachments/assets/ac0b5801-edfd-4ce9-b5a7-a286870b1ef5)




15. After you you Press "Enter" Validate your "setup_nba_data_lake.py" file was created by enterinf "ls" in the commandline. You will also see it saying it has has been modified.
    Enter cmd:
    ```bash
    ls
    ```
    
![image](https://github.com/user-attachments/assets/c47b18e3-8dc2-45ba-bcc7-f04c1e1630cb)




16.  Create an .env file to create variables that store your API Key and NBA endpoint for your scripts.
     Enter cmd:
     ```bash
     .env
     ```
![image](https://github.com/user-attachments/assets/6df1ac04-ccdc-4dde-8a77-6235e88e77f2)



 
17. Paste the following variables into your ".env" file, ensure you configure your API key and endpoint URL.

   SPORTS_DATA_API_KEY=your_sports_data_api_key
   NBA_ENDPOINT=https://api.sportsdata.io/v3/nba/scores/json/Players

![image](https://github.com/user-attachments/assets/c684e2e4-e321-49c8-8fb7-1f1a6cac3eb0)

18. On your keyboard press "^X" (ctrl+x) to exit, press "Y" to save the file, press "Enter" to confirm the file name. Look on the bottom 
     left to verify you are entering the right thing.

![image](https://github.com/user-attachments/assets/204bca34-2a2c-4662-88ca-b88c4f8f490c)
![image](https://github.com/user-attachments/assets/a94a03ec-fad8-427c-9301-0a4676a05367)




19. Run the script.
    Enter cmd:
    ```bash
    python3 setup_nba_data_lake.py
    ```



20. You should see the resources were successfully created, the sample data was uploaded successfully and the Data Lake Setup Completed
![image](https://github.com/user-attachments/assets/ee1b2405-5616-4d10-b27e-abc2293e7947)




Step 7: Manually Check For The Resources
In the Search Bar, type S3 and click blue hyper link name
-You should see 2 General purpose bucket named "Sports-analytics-data-lake"
![image](https://github.com/user-attachments/assets/9d5e2dda-b0d1-4f35-8c53-ab60385e5b1d)
![image](https://github.com/user-attachments/assets/4134bd1d-d0b5-48c3-a611-7e4d2d406711)



-When you click the bucket name you will see 3 objects are in the bucket

Click on raw-data and you will see it contains "nba_player_data.json"

Click the file name and at the top you will see the option to Open the file

-You'll see a long string of various NBA data

Head over to Amazon Athena and you could paste the following sample query:
SELECT FirstName, LastName, Position, Team
FROM nba_players
WHERE Position = 'PG';
-Click Run -You should see an output if you scroll down under "Query Results"
