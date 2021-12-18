# Movies-ETL

## Background:

Britta is excited to prepare for the hackathon. In data analysis, a hackathon is an event where teams of analysts collaborate to work intensively on a project, using data to solve a problem. Hackathons generally 
last several days, and teams work around the clock on their projects. Britta needs to gather data from both Wikipedia and Kaggle, combine them, and save them into a SQL database so that the hackathon participants have a nice, clean dataset to use. To do this, she will follow the ETL process: extract the Wikipedia and Kaggle data from their respective files, transform the datasets by cleaning up and joining them together, and load the cleaned dataset into a SQL database.

## Tools Used:

### ETL- 
The idea behind ETL is straightforward. Raw data exists in multiple places and needs to be cleaned and structured before it can be analyzed. ETL breaks this problem into three steps, or phases: Extract, Transform, and Load.

![data-8-1-1-1-extract-transform-load](https://user-images.githubusercontent.com/23488019/145751918-99009234-a6a5-450e-80b1-04b82f9e4152.png)

The iterative process for cleaning data can be broken down as follows:

- First, we need to inspect our data and identify a problem.
- Once we've identified the problem, we need to make a plan and decide whether it is worth the time and effort to fix it.
- Finally, we execute the repair.

     #### - Extract -
     In the Extract phase, data is pulled from external or internal sources, possibly disparate. The sources could be flat files, scraped webpages in HTML or JavaScript Object        Notation (JSON) format, SQL tables, or even streams of sensor data. The extracted data is held in a staging area in between the data sources and data targets.
     
     ![extract](https://user-images.githubusercontent.com/23488019/145751835-66b0e98d-f299-41f3-9f15-867ba0bb9b5c.png)

     For Britta, I will extract scraped Wikipedia data stored as a JSON, and Kaggle data stored in CSVs.
     
     
     #### - Transform - 
     
     The transform step is largely spent on data cleaning. There are other transformations that aren't strictly data cleaning, but for the most part, the transformation step is      used to clean up your data.After data is extracted, there are many transformations it may need to go through. The data may need to be filtered, parsed, translated, sorted,      interpolated, pivoted, summarized, aggregated, merged and many such functions. The goal of our project is to create a consistent structure in the data. Without a consistent      structure in our data, it's difficult to perform any meaningful analysis. The transformation phase can be accomplished with Python and Pandas, pure SQL, or specialized ETL      tools like Apache Airflow or Microsoft SQL Server Integrated Services (SSIS). Python and Pandas are especially good for prototyping an ETL transformation because they            provide flexibility and interactivity (especially in a Jupyter Notebook), without enforcing any complicated frameworks. We will use Python and Pandas to explore, document,      and perform our data transformation.

     ![transform](https://user-images.githubusercontent.com/23488019/145751851-9aa93818-689b-4bfb-af47-83e1ed2800d3.png)

     #### - Load -
     Finally, after the data is transformed into a consistent structure, it's loaded into the data target. The data target can be a relational database like PostgreSQL, a non-        relational database like MongoDB that stores individual documents, or a data warehouse like Amazon Redshift that optimizes performance specifically for analytics. Britta        has determined that a SQL database is the best solution for sharing the data in the hackathon, so we'll be loading our data into a PostgreSQL table. SQL databases are often      the targets of ETL processes, and because SQL is so ubiquitous, even databases that don't use SQL often have SQL-like interfaces.
     
     ![load](https://user-images.githubusercontent.com/23488019/145751891-163225fc-0a7a-4f31-9838-0cfa3993af90.png)

## Project Overview:

Wikipedia has a ton of information about movies, including budgets and box office returns, cast and crew, production and distribution, and so much more. Luckily, one of Britta's coworkers created a script to go through a list of movies on Wikipedia from 1990 to 2018 and extract the data from the sidebar into a JSON. Unfortunately, her coworker can't find the script anymore and just has the JSON file. We'll need to load in the JSON file into a Pandas DataFrame.
MovieLens is a website run by the GroupLens research group at the University of Minnesota. The Kaggle dataset pulls from the MovieLens dataset of over 20 million reviews and contains a metadata file with details about the movies from The Movie Database (TMDb). Wikipedia doesn't have strict standards on how movie data is presented, so it needs a lot of work to clean up the data and make it usable. Like most web-scraped data, it's in the flexible JSON format to store all kinds of data, but Britta needs to organize it in a structured format before she can send it to SQL and she's asked me to assist with this task. This new assignment consists of four technical analysis deliverables as follows:

- Deliverable 1: Write an ETL Function to Read Three Data Files
- Deliverable 2: Extract and Transform the Wikipedia Data
- Deliverable 3: Extract and Transform the Kaggle data
- Deliverable 4: Create the Movie Database


## Code and Results:
- Deliverable 1: Write an ETL Function to Read Three Data Files

The code can be found in the ETL_function_test.ipynb file

- Deliverable 2: Extract and Transform the Wikipedia Data

The code can be found in the ETL_clean_wiki_movies.ipynb file


- Deliverable 3: Extract and Transform the Kaggle data

The code can be found in the ETL_kaggle_data.ipynb file


- Deliverable 4: Create the Movie Database

The code can be found in the ETL_create_database.ipynb


## Summary:
Hence after our analysis it can be found out that the movies table has count 6052 entries and the rating table has 26024289 count.

## Note:
Because of the huge size of the .csv files, I have created a sample .csv file with 1000 rows only. It is located in th eResources folder. Please use these files to run the analysis.

## References:

- https://courses.bootcampspot.com/courses/791/pages/8-dot-2-1-extract-the-wikipedia-movies-json?module_item_id=301206

