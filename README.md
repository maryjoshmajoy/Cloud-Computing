# Cloud-Computing
Hai There ….I am Mary Joshma Joy

Project Introduction: 
The Project titled “"Analysis and Implementation of a Data Analytical Platform for Parks in the City of  Vancouver” features a variety of playing fields, from regulation-sized grass fields and artificial turf to non-regulation-sized gravel fields. All the Park Board's fields, courts, diamonds, and outdoor facilities—aside from synthetic turf fields—are open for casual use on a first-come, first-served basis if they aren't closed for repair or being used by a permit holder. To utilize artificial grass fields, you need a permit. This dataset shows the playfields that are closed for maintenance. Field maintenance personnel inspect all grass fields to assess playability, repairs, and closures. The dataset shows the playfields that are closed for maintenance and the number of people visiting each park on weekends. Field maintenance personnel inspect all grass fields to assess playability, repairs, and closures.
Through the development of an Extract, Transform, and Load (ETL) pipeline, the project ensures efficient data handling while highlighting correlations in the dataset. This analytical platform not only enhances data visualization and decision-making but also contributes to give information regarding the maintenance of the playing fields and turf with maximum clarity to people planning to visit the park. This system balances casual and permitted use while maintaining field conditions for community enjoyment.
Project Objectives:
1.	Data Ingestion and Storage
Efficiently ingest weekend playfield status data into AWS storage buckets to organize raw, transformed, and curated datasets.
2.	Data Profiling and Cleaning
Ensure the dataset's quality by profiling and cleaning, removing redundancies, and resolving formatting issues.
3.	ETL Pipeline Implementation
Design and execute an ETL pipeline to extract, transform, and load data into the curated bucket for analytical purposes.
4.	Trend Analysis
Investigate trends in the number of people visiting each park to derive actionable insights for urban planners.
5.	Scalable Analytical Platform
Develop a scalable and reusable analytical platform using AWS services to handle similar datasets in the future.
6.	Visualization and Reporting
Generate visualizations to communicate key findings effectively, aiding stakeholders in making informed decisions.
7.	Analysis and Implementation of a Data Analytical Platform for Parks in City of  Vancouver- Mary Joshma Joy

The dataset has been extracted from the Vancouver Open Data Portal in Excel (.xlsx) format. While multiple options like .csv and .parquet are available, the Excel format is more suitable for our scenario.

 

Descriptive Analysis
To visualize the difference between the number of open and closed parks in the city as per recent data due to maintenance.
 

Data Analytical Platform
Workflow Description
The following steps outline the data processing workflow:
1.	Raw Bucket: Data ingestion.
2.	Data Brew: Profiling and cleaning.
3.	Transformed Bucket: Storing cleaned data.
4.	ETL Pipeline: Extract, transform, and load processes.
5.	Curated Bucket: Storing results in system and user folders.
 
Data Storage
Three buckets are created in AWS S3 to store:
1.	Raw data.
2.	Transformed data.
3.	Curated data.


 
Data Ingestion
The extracted Excel data is uploaded directly into the raw bucket using AWS's upload functionality.
 
Data Profiling
Data profiling ensures data quality and identifies required changes. The profiling process is executed in AWS Glue DataBrew by creating a dataset and running the profiling process. The results are stored in the transformed bucket.
 
Data Cleaning
Data cleaning involves:
•	Handling missing data.
•	Removing duplicates.
•	Resolving formatting issues.
Unnecessary columns are deleted, and the cleaned data is stored in the curated bucket.
 
 
 
ETL Pipeline Design
The ETL (Extract, Transform, Load) pipeline design involves:
1.	Fetching cleaned data from the transform bucket.
2.	Removing unnecessary columns.
3.	Grouping years of construction and aggregating maximum speed limits.
The final results are stored in the transformed bucket in the system and closer_details folders.
 
 
 
Exploratory Analysis
The exploratory pipeline was to find out the status of the parks based on the weekend status across the city to find out how it can affect the people. In summary, the parks are mostly in the status of’ user discretion’ rather than ‘closed’ status.
 
Figure 16 Diagram of the park’s usage across the city
Data Pipeline:
According to the screenshot, the goal of ETL in AWS Glue is to automatically extract playfield data, clean and standardize parameters like "Site_area" and "Weekend_status," and then load the data into a structured format for analysis. Producing insights, such as recognizing patterns in field availability across various regions, guarantees precise, consistent, and quantifiable data.

 



 
 
As the information from the weekend playfield conditions in different site locations is shown visually in the screenshot, which is divided into two categories: "Closed" and "User discretion.” Interestingly, most playfields are classified as "User discretion," with a smaller percentage designated as "Closed." This implies that most fields are available for conditional use instead of being restricted. The table also illustrates how different site regions have different playfields; for example, "C" has a significantly higher number of playfields than other place.













  





