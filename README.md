# Project : Data Modeling with Postgres

## Music Streaming Analytics

### Overview

This project aims to provide actionable insights for a startup's music streaming app by analyzing the data collected on user activity on song metadata. The data is currently stored in JSON format, with logs detailing user activity and metadata describing the songs available on the platform. 

### Objective

- To design and implement a database schema using PostgreSQL 
- Develop an ETL (Extract, Transform, Load) pipeline to transfer data from JSON files into the database.
- Creating star schema database. The schema will be structured as a star schema, consisting of facts and dimension tables optimised for analytical queries.

### Data Sources

The datasets provide complimentary information for analyzing both the content (songs and artists) and the usage patterns (user activity) of the music streaming app.

1. **User Activity Logs** : 
    - **Source** : Subset of the Million Song Dataset.
    - **Format** : JSON Files
    - **Partitioning** : Files are partitioned by the first three letters of each song track ID.
    - **Content** : Contains meta data about each song, including title, duration, release year. Includes information about the artist, such as name, location, and terms associated with the artist.
    - **Purpose** : Provides detailed information about the songs available on the music streaming app, facilitating analysis of song attribute and artist characterstics.
    
     
2. **Song Metadata** :
    - **Source** : Generated log files from the music streaming app.
    - **Format** : JSON Files
    - **Partitioning** : Files are partitioned by year and month.
    - **Content** : Log user activity on the music streaming app, such as song plays, timestamps, user ids, session ids, and details about the song played.
    - **Purpose** : Captures user interactions with the app, enabling analysis of user behaviour, popular songs, and user engagement over time.
    
### Database Schema
The database schema is designed using a star schema approach, with a central fact table - ***songplays*** surrounded by dimension tables ***users, songs, artists, time***.

### ETL Pipeline
ETL pipeline is developed using Python and SQL to extract data from JSON files, transform it into a suitable format, and load it into the PostgreSQL database. Python scripts handle the extraction and transformation processes. SQL commands to create and populate the database tables.

### Directory Structure

- **create_tables.py** : python script to create database schema and tables in PostgreSQL
- **etl.ipynb** : Jupyter Notebook containing the ETL (Extract, Transform, Load) pipeline for transferring data from JSON files to the database.
- **etl.py** : Python script implementing the ETL pipeline
- **sql_queries.py** : Python script containing SQL queries for data analysis and manipulation
- **README.md** : Markdown file containg project documentation including instructions and descriptions.
- **test.ipynb** : Jupyter Notebook for testing the database creation and database insertion.

### Running the Project

1. **create_tables.py**
- Run this script first to create the database schema and tables in PostgreSQL.
- This step ensures that the database structure is set up before loading any data.

2. **etl.py or etl.ipynb**
- Execute the ETL pipeline to extract data from JSON files, transform it as needed, and load it into the PostgreSQL database.
- You can choose to run either the python script (etl.py) or the Jupyter Notebook (etl.ipynb) containing the ETL pipeline.

3. **test.ipynb**
- Use this Jupyter Notebook to confirm the successful creation of database and insertion of records.
- perform queries and checks to validate that the data is correctly loaded into the database tables.
