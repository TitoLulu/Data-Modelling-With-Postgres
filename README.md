## Data Modelling with Postgres 
ETL Project for a fictional company sparkify. The ETL Pipeline built is aimed at enabling the Analytics team to retrieve information on songs users are listening to. 
Data sources exists in directories of JSON logs and JSON metadata on Sparkify songs app. 

## Approach
Created a database schema to match Analytics teams data requirements making use of star schema modelling. 
Fact table - songplays - log records data associated with songplays
    
    |start_time|user_id|level|song_id|artist_id|session_id|location|user_agent|
    |:---------|:------|:----|:------|:--------|:---------|:-------|:---------|
    
Dimension tables: 
 1. users - app users
     
     |first_name|last_name|gender|level|
     |:---------|:--------|:-----|:----|
     
 2. songs - songs in app database
     
     |song_id|title|artist_id|year|duration|
     |:------|:----|:--------|:---|:-------|
     
 3. artists - artists in app database
 
     |artist_id|name|location|latitude|longitude|
     |:--------|:---|:-------|:-------|:--------|
     
 4. time  - timestamps of records on songplays broken down into specific units
 
     |start_time|hour|day|week|month|year|weekday|
     |:---------|:---|:--|:---|:----|:---|:------|
 
Created a python ETL pipeline that retrieves, processes and loads records into the the various tables. 
create_tables.py --> creates the fact and dimension tables
etl.py --> reads and processes files from song_data and log_data and loads them into tables

## References
Highly uitilized the web to get an understanding of concepts 

-[Reference #1](https://pandas.pydata.org/docs/user_guide/index.html):**Pandas User Guide**

-[Reference #2](https://stackoverflow.com/questions/41925378/selecting-a-specific-value-from-a-data-frame):**Selecting a specific value from a dataframe**

-[Reference #3](https://www.dataindependent.com/pandas/dataframe-to-list/):**Dataframe to list**
