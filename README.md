## Project Description

Current project is devoted to query and analyzing collected data on user activity and songs 
in new music streaming app.

## Schema for Song Play Analysis

A star schema optimized for queries on song play analysis was designed and implemented. 
It includes the following tables:

### Fact Table

1. **songplays** - records in log data associated with song plays i.e. records with page `NextSong`
    * songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

### Dimension Tables

2. **users** - users in the app
    * user_id, first_name, last_name, gender, level
3. **songs** - songs in music database
    * song_id, title, artist_id, year, duration
4. **artists** - artists in music database
    * artist_id, name, location, latitude, longitude
5. **time** - timestamps of records in songplays broken down into specific units
    * start_time, hour, day, week, month, year, weekday

## Project Files

The project workspace consists of six files:

1. `test.ipynb` displays the first few rows of each table to let you check your database.
2. `create_tables.py` drops and creates your tables. 
You run this file to reset your tables before each time you run your ETL scripts.
3. `etl.ipynb` reads and processes a single file from `song_data` and `log_data` 
and loads the data into your tables. 
This notebook contains detailed instructions on the ETL process for each of the tables.
4. `etl.py` reads and processes files from `song_data` and `log_data` and loads them into your tables. 
5. `sql_queries.py` contains all your sql queries, and is imported into the last three files above.

## Project DataFlow

Below are steps you can follow to get Song Play Database:

### Create Tables

Run `create_tables.py` to create your database and tables.
Run `test.ipynb` to confirm the creation of your tables with the correct columns. 
Make sure to click `Restart kernel` to close the connection to the database after running this notebook.

### Build ETL Processes

You can use the `etl.ipynb` notebook to debug ETL processes for each table. 
At the end of each table section, or at the end of the notebook, 
run `test.ipynb` to confirm that records were successfully inserted into each table. 
Remember to rerun `create_tables.py` to reset your tables before each time you run this notebook.

### Build ETL Pipeline

Script `etl.py` allows to process the entire data sets. 
Remember to run `create_tables.py` before running `etl.py` to reset your tables. 
Run `test.ipynb` to confirm your records were successfully inserted into each table.

### Query Examples

Some query examples to Song Play Database are presented in `test.ipynb` notebook.