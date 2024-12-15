# Cloud-Computing
Heey There ….I am Mary Joshma Joy

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
7.	Analysis and Implementation of a Data Analytical Platform for Parks in City of  Vancouver.
   ![Screenshot 2024-12-14 165142](https://github.com/user-attachments/assets/b3026e44-4a7d-48d3-9836-c57979f4bec4)

   

The dataset has been extracted from the Vancouver Open Data Portal in Excel (.xlsx) format. While multiple options like .csv and .parquet are available, the Excel format is more suitable for our scenario.


Tools and technologies used:
S3 buckets for data storage, AWS Data Brew for data cleaning and  AWS Glue to design Pipeline



 
Exploratory Analysis
The exploratory pipeline was to find out the status of the parks based on the weekend status across the city to find out how it can affect the people. In summary, the parks are mostly in the status of’ user discretion’ rather than ‘closed’ status.
![image](https://github.com/user-attachments/assets/efc7e432-1c45-43ec-822b-1f1b27a7b981)

 
Data Pipeline:
According to the screenshot, the goal of ETL in AWS Glue is to automatically extract playfield data, clean and standardize parameters like "Site_area" and "Weekend_status," and then load the data into a structured format for analysis. Producing insights, such as recognizing patterns in field availability across various regions, guarantees precise, consistent, and quantifiable data.

 ![image](https://github.com/user-attachments/assets/3865dac8-4ab9-4bd7-a831-dd2bebb2e6f2)
 
 ![image](https://github.com/user-attachments/assets/c5c12b17-1411-4fd5-9e41-9ca29a6b7a1b)
 
 ![image](https://github.com/user-attachments/assets/fb2c2591-bcdf-48b5-993e-8b88d787663a)

 
Descriptive Analysis
To visualize the difference between the number of open and closed parks in the city as per recent data due to maintenance.
![image](https://github.com/user-attachments/assets/9173b330-5266-4912-bf75-6704ed45d562)

Data Analytical Platform
Workflow Description
The following steps outline the data processing workflow:
1.	Raw Bucket: Data ingestion.
2.	Data Brew: Profiling and cleaning.
3.	Transformed Bucket: Storing cleaned data.
4.	ETL Pipeline: Extract, transform, and load processes.
5.	Curated Bucket: Storing results in system and user folders.
   ![image](https://github.com/user-attachments/assets/a5fe91ae-e070-493f-a151-57dbed067ed6)
 
Data Storage
Three buckets are created in AWS S3 to store:
1.	Raw data.
2.	Transformed data.
3.	Curated data.
   ![image](https://github.com/user-attachments/assets/dbc078db-732c-4f98-ac53-cde54154521d)

Data Ingestion
The extracted Excel data is uploaded directly into the raw bucket using AWS's upload functionality.
![image](https://github.com/user-attachments/assets/110af2b2-467b-4216-8a6b-9c75cbb7233e)

 
Data Profiling
Data profiling ensures data quality and identifies required changes. The profiling process is executed in AWS Glue DataBrew by creating a dataset and running the profiling process. The results are stored in the transformed bucket.
![image](https://github.com/user-attachments/assets/540b9af7-daff-445e-bf32-32f95091f610)

 
Data Cleaning
Data cleaning involves:
•	Handling missing data.
•	Removing duplicates.
•	Resolving formatting issues.
Unnecessary columns are deleted, and the cleaned data is stored in the curated bucket.
![image](https://github.com/user-attachments/assets/1b2ff723-fd24-4c88-898d-18baf89e10f2)
![image](https://github.com/user-attachments/assets/32e1f3a6-7f8c-479c-b9c8-9a017b3bb06f)
![image](https://github.com/user-attachments/assets/fa52f964-fee4-4d31-9253-621560692098)
 
ETL Pipeline Design
The ETL (Extract, Transform, Load) pipeline design involves:
1.	Fetching cleaned data from the transform bucket.
2.	Removing unnecessary columns.
3.	Grouping years of construction and aggregating maximum speed limits.
The final results are stored in the transformed bucket in the system and closer_details folders.
![image](https://github.com/user-attachments/assets/9a1b2201-51be-4b8f-8ddb-50508d3d0ec9)

![image](https://github.com/user-attachments/assets/d1c4ffd6-0279-482c-b33b-99f3d6f66eba)

![image](https://github.com/user-attachments/assets/73fe28c8-5e22-4453-b8be-f43e018d1b9e)


Tools and technologies used:
S3 buckets for data storage, AWS Data Brew for data cleaning and  AWS Glue to design Pipeline

Data Wrangling
Objective: 
Adding more information to Weekend -playfield -status raw data to make it more valuable is known as data enrichment in AWS. 
Tools and Technologies:
To combine external datasets with raw data, use AWS Glue. AWS Lambda allows you to process data in real-time, while Amazon Athena will enable you to examine it afterward. Store extra data in DynamoDB, RDS, or Amazon S3 for convenient access. By fusing raw data with insightful context, enrichment enhances decision-making, allows you to personalize user experiences, and improves insights. Data Crawler is the program that connects to the data source, scans data from various data sources to determine its schema and creates metadata tables in the AWS glue data catalog.
Methodology:
Data stored in sources such as S3 and DynamoDB the connections can be automatically scanned by an AWS crawler to identify its schema and build or update tables in the Glue Data Catalog, preparing the data for processing and querying. This process can help to add easily, delete, rather than RDBMS and easily understand the data.
 
![image](https://github.com/user-attachments/assets/8e2820ef-6f9f-4334-a6c8-f7bd83d64f48)
![image](https://github.com/user-attachments/assets/6a83539f-268a-4f9a-b02c-989f1eaf6073)
![image](https://github.com/user-attachments/assets/326d725c-2554-4f8f-bddd-b44aa36f60bd)
Amazon Athena SQL: 
AWS Athena is a serverless interactive query solution that lets you use standard SQL to analyze data directly in Amazon S3. To query the data stored in S3 without having to move or load it, you must first specify the schema for your data with the help of the AWS Glue Data Catalog and fetch the data using a simple SQL query such as select * from “raw data.”
Amazon Athena SQL
 
![image](https://github.com/user-attachments/assets/ac710f22-2b3d-476b-b0ad-4bf92747203d)
Web Server Connection:
Creating a web server and general server for the data team and users to access data is the alternative technique for data enrichment. We created our own VPC with private and public subnets for this.In the public subnet projects subnet public1 us east 1a had a configuration for private access for the data team and secure and insecure access to the public. The public subnet hosts the resources that can be accessed from anywhere, while the private subnet hosts the data and protects the sensitive data from direct exposure to the internet. The NAT gateway protects from public access to the data  for the private subnet.

![image](https://github.com/user-attachments/assets/d8a26190-560f-4736-bf77-c05421b12383)
![image](https://github.com/user-attachments/assets/fd69f4f7-8248-468a-985d-2323ef0134a3)
![image](https://github.com/user-attachments/assets/0bb5bd71-59ad-4171-9c0c-d8d8dcbe0af3)
![image](https://github.com/user-attachments/assets/98a8701d-9754-4f80-8a29-85054718e924)
Modifying the HTML file in the directory C:/inetpub/wwwroot so that it would greet visitors to Vancouver Parks' public webpage converting the html file to txt and then save the file and convert file back to html.
Data Quality Control 
Project Description: Data Quality Control Initiative at City of Vancouver
Project Title: Implementation of Data Quality Control Measures at City of Vancouver
Objective: The primary objective of this project is to establish a comprehensive Data Quality Control (DQC) framework at City of Vancouver. This framework will ensure the organization's data's accuracy, completeness, consistency, and reliability, enhancing decision-making processes and overall business performance.

Background: To ensure data security, the AWS Key Management  Service and Bucket Versioning
Scope: The project will focus on the following key areas:
•	Data Profiling: Analyzed the existing weekend play status datasets to assess quality levels 
•	Data Cleansing: Developing processes to correct inaccuracies, eliminate duplicates, and handle null values in the dataset.

Methodology:

Bucket Versioning:
Multiple versions of an object are stored in a bucket using AWS S3's bucket versioning functionality. It improves data protection and recovery by retaining older versions of files, enabling you to recover deleted or overwritten. “playsta-raw-mary” is backed up using the versioning technique to prevent from data manipulation and it is stored in different zone as a backup.
![image](https://github.com/user-attachments/assets/0bf33ba0-e05f-43f8-8018-6555dde6c69b)

![image](https://github.com/user-attachments/assets/4cd22cae-44ec-4ca4-a6ae-5b9c596bed7c)
AWS KMS (Key Management Service) is a managed service that generates, maintains, and regulates encryption keys to secure data across AWS services and apps. The parks-mary is the key created to do KMS encryption with Labrole. 
![image](https://github.com/user-attachments/assets/c012f8cc-2090-4268-afc3-eb537215a6b7)
Data Replication:
The process of duplicating and saving ‘data’ in data servers in different geographical locations to enhance availability, fault tolerance, and disaster recovery is known as data replication. The “playsta-raw-mary-backup” is used to back up the “playsta-raw-mary”.

![image](https://github.com/user-attachments/assets/7365f8e9-e867-4ac3-81d3-d3b8c7c0d41d)
Data Governance
Every stage in the AWS Glue pipeline for quality assurance and data governance helps to manage and improve the data for safe and dependable use. At each stage of the pipeline seen in the screenshot, data governance is implemented as follows:
•	An S3 bucket is used to begin data import, guaranteeing that permissions and access control are implemented to prevent unwanted access. This is the cornerstone of safe data management. The pipeline retrieves data from the S3 bucket specified in the Glue catalog.
•	Change Schema guarantees that data follows a specified schema or structure, essential for interoperability and consistency. Glue's transformation features modify the schema to conform to the desired format.
•	Detect Sensitive Data: To comply with privacy regulations, identify private data. Sensitive fields in the dataset are determined by AWS Glue and flagged for additional processing, such as encryption or masking.
•	Data Quality: Verifies the data's accuracy, completeness, and consistency before it is processed further to ensure it satisfies quality requirements. To look for missing values, improper formats, or other quality problems. Whenever the data quality is ensured an another node creates automatically to transform.
•	Conditional router: Data is categorized according to predetermined criteria, allowing for specific governance actions for various data types (such as reporting rejected data).
How to do it: routes data into two distinct paths: flagged data with defects or problems ("Failed") which is in the path https://playsta-trf-mary.s3.us-east-1.amazonaws.com/park-info/dataquality/failed/ and clean, processed data ("default_group") is saved in the following path https://playsta-trf-mary.s3.us-east-1.amazonaws.com/park-info/dataquality/passed/
As a summary, the above paths keep rejected or flagged data for auditing and reprocessing and make sure that only validated and transformed data is delivered as the final output. Thus the “park.stat.mary” was created to ensure the quality.

![image](https://github.com/user-attachments/assets/9b9cdcc3-face-4057-8653-aca2e70647dc)
![image](https://github.com/user-attachments/assets/0e56cfcf-f01d-4381-9d54-060a7363de88)


















    

 














  





