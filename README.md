# Movies-ETL
Using ETL process to analyze and predict movie popularity

## Overview
The code contained follows the extract, transform, and load method using movie data from two separate sources including .csv and .json. The code accomplishes the following tasks:
1. An ETL function which reads three data files
[ETL Function Test]('ETL_function_test.ipynb')
2. Extracts and transforms Wikipedia data in .json format
[Clean Wikipedia Movies]('ETL_clean_wiki_movies.ipynb')
3. Extracts and transforms Kaggle data in .csv format
[Clean Kaggle Data]('ETL_clean_kaggle_data.ipynb')
4. Creates a PostgreSQL database to save the DataFrames
[Create Database]('ETL_create_database.ipynb')

## Code Explanation
The function clean_movie() is designed to consolidate the columns of the Wikipedia .json file, removing the random Languages and consolidating the duplicate column information. 

The function extract_transform_load() to clean the data performs the following tasks:
- Filters out uneeded data
- Maps numeric and data data to a standard format using regular expressions
- Reorder and rename columns
- Adds columns showing rating data grouped by movie
- Sends the resulting DataFrame and original rating .csv file information to a new PostgreSQL database 

## Summary
While both files needed to be culled and adjusted in order to merge them and prepare for analysis, the .json data received from the Wikipedia file needed more manipulation. The Wikipedia transformation included consolidating and removing unneeded data, while the kaggle data only need to have a few rows removed and then change the numeric and date formats. The bulk of the work performed by this code involves cleaning, or transforming the raw data by using pandas functions. Creating the PostgreSQL database will allow analysts to query against movie data from multiple sources using a single SQL database. 
