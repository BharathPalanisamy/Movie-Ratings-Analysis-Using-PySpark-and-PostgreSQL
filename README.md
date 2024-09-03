# Movie Ratings Analysis Using PySpark and PostgreSQL #

## Project Overview ##
  This project aims to analyze movie ratings using Apache Spark for data processing and PostgreSQL for data storage. 
  The goal is to gain insights into movie ratings, including average ratings by movie, the most rated movies, and average ratings by genre and year. 
  The project is implemented using PySpark, a powerful tool for distributed data processing, and PostgreSQL, a reliable and widely-used relational database management system.

## Technologies Used ##
  
  Python: The core programming language used for scripting and automation. <br>
  PySpark: An open-source unified analytics engine for large-scale data processing. <br>
  PostgreSQL: A powerful, open-source object-relational database system. <br>
  SQLAlchemy: A SQL toolkit and Object-Relational Mapping (ORM) library for Python. <br>
  Matplotlib: A Python 2D plotting library for data visualization. <br>

## Project Structure ##
```
  ├── data/
      ├── ml-latest-small/          # Directory containing the movie ratings dataset
  │       ├── movies.csv
  │       ├── ratings.csv
  ├── main.py                       # Main script for executing the data analysis pipeline
  ├── README.md                     # Project documentation
```
## Data Engineering Concepts Used ##
1. #### Data ingestion ####
    - Data is loaded from CSV files into PySpark DataFrames. The movies.csv file contains movie details, while ratings.csv includes user ratings for each movie.
    - The data is read into PySpark DataFrames using the spark.read.csv() method. <br>

2. #### Data Cleaning and Transformation ####
- Data cleaning is an essential step to ensure data quality and consistency. 
  - The following cleaning operations are performed:
    - Removing Duplicates: Duplicate records are dropped to avoid biased analysis.
    - handling Missing Values: Null ratings are replaced with a default value, and missing movie titles or genres are filled with a placeholder.
    - Normalizing Data Formats: Genres are converted to lowercase for uniformity.

3. #### Data Merging ####
- The movie ratings and movie details DataFrames are merged using the movieId as the key.
- This combined DataFrame enables analysis that requires both movie details and ratings.

