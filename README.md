**Data Wrangling**

**Academic Integrity Wrangling at UCW for Preparing Data to gain valuable Insights**

**Project Description**: 

This project focuses on data wrangling to prepare a clean and structured dataset to analyze academic integrity violation insights at the University Canada West (UCW). 

**Objective:** 
The primary objective is to ensure the dataset is optimized using cleaning, profiling, and transforming techniques so that it can be used in SQL querying with AWS Athena to analyze trends in violations across courses and recommend strategies for improvement
Background: Academic integrity is a critical issue in higher education, and identifying patterns in violations can help develop strategies for promoting honesty and ethical behavior. This project addresses data preparation challenges, ensuring that raw data from UCW’s MBA program is refined and ready for analysis. The wrangled dataset will enable the identification of key areas such as courses which are having high trends of academic integrity violations, trends on Violation Type, and what Sanction the university has enforced so far.

**Dataset:**

The UCW Academic Integrity dataset hat has been used for this analysis is a CSV file containing academic integrity data for MBA students in 2024. It includes 10 columns and 50 records, providing insights into integrity trends across the MBA program. The dataset includes details such as:

•	Student ID: Unique identifier for each student.

•	Course Code: The course associated with the assignment. This includes six course codes; MBA601, MBA602, MBA603, and MBA604.

•	Assignment Type: The type of academic work. This includes three types; essay, group project, and presentation.

•	Turnitin Score: Percentage of similarity detected in the assignment.

•	Violation Occurrence: Whether a violation occurred (Yes/No).

•	Violation Type: Type of violation. This includes plagiarism and collusion.

•	Sanction Imposed: Penalty for the violation. This includes Grade Reduction, Warning, Expulsion, and None.

•	Appeal Status: Whether the sanction was appealed (Yes/No).

•	Final Decision: Outcome of the appeal (Pending, Dismissed or Upheld).


**Methodology:**
•	Data Collection and Preparation for Analysis:
- Upload Data to AWS S3: Stored the dataset by creating a raw bucket in Amazon S3 for secure and scalable storage. 

Figure 1: 
Data Ingestion for Raw Bucket in S3
 
•	Data Profiling:
- AWS Glue Data Brew was used for data profiling on the dataset we ingested to the S3 raw bucket, and then detected data quality issues such as missing values, outliers, and inconsistent formatting. In order to save the profiled data, a bucket was created with subfolders for profiled data.
Figure 2: 
Data Profiling 
 
•	Data Cleaning: 
- The data cleaning procedure in this step involves handling missing values, correcting data types, renaming columns, and removing irrelevant columns,
Figure 3: 
Data Cleaning
 
	- By publishing a recipe, we can refer to what changes we have made to the dataset
Figure 4: 
Data Cleaning recipe
 

•	Data Cataloging
- After cleaning, the transformed data is stored in a separate S3 bucket created for transformed data in the form of Parquet format, which is suitable for efficient querying in AWS Athena.
 
Figure 5: 
Cleaning output – System
 
- An AWS Glue Data Catalog is then created using Crawler to register the metadata for the cleaned dataset, including column names, data types, and file paths.
Figure 6: 
Data Catalog
 
•	Data Discovery and Querying with AWS Athena:
- Using AWS Athena, SQL queries will be run on the transformed data stored in the S3 bucket. The queries will explore relationships between variables such as Turnitin similarity scores, violation types, and sanctions
- This query result helps in analyzing patterns by course code and identifying trends related to academic integrity violations.
Figure 7: 
AWS Athena for running SQL
 
•	Data Visualization and Insights
o	Query result is then exported to Microsoft Excel for data visualization:
- A Bar chart is generated visually to compare the number of violations rate across course Codes. Insights from these visualizations will help identify key trends, such as the course code that has the highest number of violation rate or the trends of violation types in which most students are involved.
Figure 8: 
Data Visualization 
 

Table generated with summarized data generated with Athena
Course Code	Total Violations #	Total # of Students in each Course 	Violation Percentage from total
MBA603	12	12	52%
MBA601	12	13	48%
MBA604	0	12	0%
MBA602	0	13	0%
•	Analyzing the Outcome and Generate Insights:
- Interpret the query results and identify departments with the highest concentration of violations.
- Analyze potential reasons for the courses involved with violations, what sanctions has the universities imposed, etc.
Tools and Technologies:
AWS S3:
- Used for storing the raw, cleaned, and transformed datasets securely.

AWS Glue:
- Used to create the Data Catalog and define metadata for the academic integrity dataset.
- Facilitates data transformation and ETL (Extract, Transform, Load) processes.
AWS Athena:
- Allows querying the dataset using SQL for analysis of academic violations by department and course code.
Microsoft Excel:
- Used for additional data visualization and graphical representation of results.
SQL:
- The primary language for querying and analyzing the dataset in AWS Athena.
Deliverables:
Insights generated from the exploratory analysis, including:
•	Identification of potential patterns and trends, such as course codes with higher violation rates.
•	Trends related to Turnitin score ranges and the frequency of academic violations.
•	Insights into how different courses are affected by academic integrity violations.
Timelines:
•	Data Upload to S3: Day 1
•	Data Profiling and Cleaning: Days 2–3
•	Data Transformation and Cataloging: Days 4–5
•	Athena Query Validation: Day 6
•	Report and Deliverables Submission: Day 7.

The project will be completed within 7 days, following a structured timeline to ensure efficient progress and delivery. On Day 1, the raw dataset will be uploaded to AWS S3 for secure storage, setting up the foundation for subsequent steps. Day 2 focuses on data profiling using AWS Glue DataBrew to identify quality issues such as missing values, outliers, and inconsistent formatting. Over Days 3 and 4, data cleaning will be conducted to address these issues, standardizing formats and ensuring the dataset is well-structured. On Day 5, the cleaned data will be transformed into a Parquet format and stored in a dedicated bucket for optimized querying. Day 6 involves cataloging the data using AWS Glue Crawlers, enabling metadata registration and preparation for further analysis. Finally, on Day 7, a comprehensive diagnostic report will be generated, detailing the findings and ensuring the dataset's readiness for advanced analysis and insights.
