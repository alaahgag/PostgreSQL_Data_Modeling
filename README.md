# PostgreSQL_Data_Modeling

## Sparkify - Data Modeling with Postgres

### Introduction 
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

### Project Description
In this project, I applied what I had learned on data modeling with Postgres and build an ETL pipeline using Python. I defined fact and dimension tables for a star schema for a particular analytic focus, and write an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.

### Datasets
#### Songs Dataset:
This dataset is a subset of real data from the Million Song Dataset. Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID.
#### Log Dataset:
This dataset consists of log files in JSON format generated by this event simulator based on the songs in the dataset above. These simulate activity logs from a music streaming app based on specified configurations. The files are partitioned by year and month.
### Files
- test.ipynb displays the first few rows of each table to check database.
- create_tables.py drops and creates tables.
- etl.ipynb reads and processes a single file from song_data and log_data and loads the data into tables.
- etl.py reads and processes files from song_data and log_data and loads them into your tables. You can fill this out based on your work in the ETL notebook.
- sql_queries.py contains all sql queries

### DataBase Design
Using the song and log datasets, you'll need to create a star schema optimized for queries on song play analysis. This includes the following tables.
A star schema optimized for queries on song play analysis. It was created using the song and log datasets, and it includes the following tables:
#### Fact Table:
- songplays --records in log data associated with song plays i.e. records with page 'NextSong'
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent.
#### Dimension Tables:
- users --users in the app.
user_id, first_name, last_name, gender, level
- songs --songs in music database
song_id, title, artist_id, year, duration
- artists --artists in music database
artist_id, name, location, latitude, longitude
- time --timestamps of records in songplays broken down into specific units
start_time, hour, day, week, month, year, weekday

![Alt text](https://user-images.githubusercontent.com/72750325/213785780-f51843f1-8dd8-4c64-891d-4eee05b3d21d.png)

### Steps
- Design Star Schema then implement it by Create the Tables ,set datatypes and constraints
- Build ETL Processes by python
- Build ETL Pipeline
- Test the results
