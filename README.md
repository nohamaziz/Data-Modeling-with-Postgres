Data Modelling with Postgres

Quick start

    create_tables.sql (to create the DB to Postgresql)
    etl.py (to process all the input data to the DB)
    etl.ipynb: Jupyter Notebook for interactively develop and run python code to be used in etl.py.
    test.ipynb: Jupyter Notebook for interactively run test SQL queries against used DB.

Overview

The project provides customer startup Sparkify tools to analyze the data of thier service and help  answer key business questions like "What songs users are listening to".

This project handles data of a music streaming startup, Sparkify. Data set is a set of files in JSON format and contains two parts:

    data/song_data: static data about artists and songs
    data/log_data: event data of service usage e.g. who listened what song, when, where, and with which client

The results after running the etl.py:

    data/song_data: 71 files
    data/log_data: 30 files
    songplays: 6820
    (unique) user: 97
    songs: 71
    artists: 69

This project uses python, SQL, Postgresql DataBase .It builds an (Extract, Transform, Load)ETL pipeline to create the DB and tables, get the data from JSON files, process and insert the the data to the Data Base.


About Database:
Sparkify analytics database schema is a star design.It has one fact table and 4 supporting dimension tables. The fact table has the business data and the dimension tables answers many key questions such as : what songs users are listening to . 

Fact Table

    songplays: song play data together with user, artist, and song info (songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent)

Dimension Tables

    users: user info (user_id, first_name, last_name, gender, level)
    songs: song info (song_id, title, artist_id, year, duration)
    artists: artist info (artist_id, name, location, latitude, longitude)
    time: detailed time info about song plays (start_time, hour, day, week, month, year, weekday)
    
    
    
    
    
    
    

HOW TO Use

    create_tables.py: drops existing tables and creates new ones.
    
Run create_tables.py

Type to command line:

python create_tables.py

    etl.py:uses data in data/song_data and data/log_data, processes it, and inserts the processed data into DB.

Run etl.py

Type to command line:

python etl.py


