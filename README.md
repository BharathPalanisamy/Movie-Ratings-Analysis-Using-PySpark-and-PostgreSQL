# Movie Ratings Analysis Using PySpark and PostgreSQL #

## Project Overview ##
  This project aims to analyze movie ratings using Apache Spark for data processing and PostgreSQL for data storage. 
  The goal is to gain insights into movie ratings, including average ratings by movie, the most rated movies, and average ratings by genre and year. 
  The project is implemented using PySpark, a powerful tool for distributed data processing, and PostgreSQL, a reliable and widely-used relational database management system.

## Technologies Used ##
  
  **Python:**  The core programming language used for scripting and automation. <br>
  **PySpark:**  An open-source unified analytics engine for large-scale data processing. <br>
  **PostgreSQL:**  A powerful, open-source object-relational database system. <br>
  **SQLAlchemy:**  A SQL toolkit and Object-Relational Mapping (ORM) library for Python. <br>
  **Matplotlib:**  A Python 2D plotting library for data visualization. <br>

## Project Structure ##
```
  ├── ml-latest-small/          # Directory containing the movie ratings dataset
  │       ├── movies.csv
  │       ├── ratings.csv
  ├── First_pyspark_to_postgresql.ipynb                       # Main script for executing the data analysis pipeline
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

4. #### Aggregation and Analysis ####
    - Various aggregation operations are performed to extract meaningful insights:
      - **Average Ratings for Each Movie:** The average rating is calculated for each movie using the groupBy and agg functions.
      - **Top 10 Movies with Most Ratings:** Movies with the highest number of ratings are identified using the count function and sorted in descending order.
      - **Average Rating by Genre:** The genres are split into individual entries, and the average rating is calculated for each genre.
      - **Average Rating by Year:** The release year is extracted from movie titles, and the average rating for each year is computed.

5. #### Data Visualization
    - The project includes visualization of key findings using Matplotlib:
      - Top 10 Most Rated Movies: A horizontal bar chart showing the top 10 movies based on the number of ratings.
      - Average Rating by Year: A plot showing the average rating of movies by their release year.


## How to download the project ## 
1. ### Clone the Repository ###
   ```
       git clone https://github.com/yourusername/Movie-Ratings-Analysis-Using-PySpark-and-PostgreSQL.git
       cd to wherever the cloned repo is
   ```
1.1 ##Install Juypter notebook
    - pip install jupyterlab : Work on the project on Juypter notebook.

2. ### Install your dependencies ###
    - pip install pyspark : To download pyspark.
  
3. ### Set Up PostgreSQL
    - Ensure PostgreSQL is installed and running on your machine.
    - Create a database named NewDatabase.
    - Update the connection details (user, password, endpoint) in the main.py script.

4. ### Run the result using Juypter notebook ###
    - Click kernel and select "Restart and run all"

6. ### View Results ###
    - The results will be stored in the PostgreSQL database. You can visualize the data using the provided matplotlib scripts.
    - The results of the graphs will be outputted in juypter notebook.

## Future Enhancements ##

  - **Scalability:**  Implementing the project in a distributed environment using AWS services like S3, EMR, and RDS.
  - **Real-time Analysis:**  Extending the project to perform real-time analysis using streaming data and tools like Apache Kafka.
  - **Advanced Analytics:**  Integrating machine learning models to predict movie ratings based on user behavior and other factors.

## Conclusion ## 
This project demonstrates the application of data engineering concepts using PySpark and PostgreSQL. It showcases how to ingest, clean, transform, and store large datasets, providing valuable insights into movie ratings. The project serves as a strong foundation for more complex data engineering tasks, such as building scalable data pipelines and performing advanced analytics.

## Project Pictures of the database <br>
<img width="432" alt="Pictureforgithub" src="https://github.com/user-attachments/assets/8fd6e16c-2c96-4cc7-992e-590a83fc4c7d"> <br> 

- Picture above shows the creation of the database called newDatabase.

<img width="421" alt="Screenshot 2024-09-03 at 11 14 54 AM" src="https://github.com/user-attachments/assets/d204d9b0-fdfa-4ed8-a489-3aadcbb99b61"> <br>

- Shows the creation of the tables and all of the columns created.

<img width="1440" alt="Screenshot 2024-09-03 at 11 50 06 AM" src="https://github.com/user-attachments/assets/51585a3d-aca3-492f-920d-214ab7cd535c"> <br>

- Shows tables and columns within the tables to show that the pyspark code created columns.
- Query Outputs the results of the first table. 





