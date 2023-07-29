# IMDb Movie Dataset ETL and Migration

## Project Overview

The primary goal of this project was to ingest a substantial movie dataset and store it efficiently in two types of databases: SQL and NoSQL. The dataset consisted of raw, uncompressed tsv files totaling approximately 40GB in size. As the data engineer on this project, my role was to tackle the ETL pipeline and ensure the successful migration of the data.

## Technologies Used

For this project, I utilized a variety of technologies to achieve the desired results:

- Java: I leveraged Java programming to perform the data extraction and transformation tasks.
- JDBC (Java Database Connectivity): To interact with the SQL database, I employed JDBC, which allowed me to efficiently insert data into the SQL database tables.
- SQL: SQL (Structured Query Language) served as the primary language for managing and querying the relational database.
- MongoDB: As the NoSQL database, I chose MongoDB due to its flexibility and scalability.
- Java Mongo Driver: I used the Java Mongo driver to interact with MongoDB, handling batch insertions of data into MongoDB collections.

## Extracting the Data

The first crucial step was to extract data from the raw tsv files into both SQL and NoSQL databases. I implemented a Java-based solution using JDBC to read the data in batches. By doing so, I could optimize the performance and avoid overwhelming the system with a large dataset.

For the NoSQL database, the Java Mongo driver came in handy. I efficiently read batches of records and inserted them into MongoDB collections, ensuring a smooth migration process.

## Transformations

The raw dataset required extensive transformation to fit the target database schemas properly. During the ETL process, I performed various transformations, including:

- Cleaning and parsing string fields: I ensured that fields like names and titles were formatted consistently and free of any errors.
- Handling missing data: I addressed missing values, providing default values where appropriate.
- Joining related data: I carefully joined data across multiple tables to create more user-friendly and query-optimized structures.
- Mapping columns: To match the target schemas, I mapped the data columns accordingly.

In the context of the NoSQL migration, I denormalized the data schema to optimize read performance. This involved embedding related data within documents, rather than relying on normalized relationships.

## Additional Features

This data engineering project includes several additional features:

- Loads IMDb data to SQL table via JDBC in accordance with a given schema (IMDBLoader).
- Creates views from IMDb data based on a given query (GenerateMappings).
- Performs data cleaning/integration after creating new sources according to the given query (createsources & FillFromWikidata).
- Performs Association mining using Apriori in numerous steps to generate Lk and Ck after initializing the data (Apriori).
- Performs Kmeans clustering after initializing the data, performing KMeans, and comparing the clusters using silhouette coefficient and mutual information (2 separate metrics for internal and external evaluation), stored in the KMeansClustering folder.

## Optimizations

To enhance the overall ETL process and achieve better performance, I implemented several optimizations:

- Batch loading: I loaded data in batches, reducing the overall time and system load.
- Prepared statements: By using prepared statements, I efficiently executed SQL queries and reduced query compilation overhead.
- Fetch size configuration: I optimized result set fetching by setting an appropriate fetch size for SQL queries.
- Pre-allocated documents: For MongoDB, I pre-allocated documents to minimize overhead during insertions.
- Bulk inserts: I used bulk insertion techniques for MongoDB to improve the speed of data ingestion.

## Conclusion

This data engineering project provided invaluable hands-on experience in dealing with large datasets, performing ETL tasks, and effectively managing database migrations. The combination of SQL and NoSQL databases allowed me to explore different data modeling techniques and optimization strategies.

Feel free to explore the code and documentation in this repository.



