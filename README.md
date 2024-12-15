**Data Quality Control**

**A Data Quality Control Initiative, Ensuring Reliable and Actionable Insights for Urban Forestry Analysis**


**Project Description:** The Data Quality Control Initiative focuses on ensuring the integrity, accuracy, and relevance of datasets used for analyzing Bowhall Red Maple trees in the City of Vancouver. This project leverages AWS services to establish robust data governance practices by implementing a structured ETL pipeline to evaluate and enhance data quality. 


**Objective:** 
 The primary objective of this project is to create an efficient data quality control pipeline that validates critical variables, such as Height ID range, Diameter, Tree ID, and planted date, to maintain high standards of data accuracy, completeness, and freshness. By ensuring the quality of the dataset, the project aims to support meaningful analysis and decision-making processes for urban forestry practices.
 
![DQ_Analysis Process (F0)](https://github.com/user-attachments/assets/0d0ba94f-30cd-47cc-957e-7b9f3f90f2d9)


**Background:** 

Urban forestry management requires high-quality data to plan and maintain city greenery effectively. Public datasets, such as the one used for Bowhall Red Maple trees, can suffer from issues like missing values, duplicates, and outdated information. By addressing these challenges, this initiative ensures that only reliable data is used for further analysis, supporting sustainable city planning efforts and environmental studies.


**Dataset:** 

The dataset file used in this exploratory analysis had 21 columns and 429 records detailing the Bowhall Red Maple trees planted in Vancouver between 2014 and 2024. This comprehensive dataset provides a detailed overview of planting trends, tree sizes, and locations, serving as a foundation for evaluating urban forestry strategies to implement in the city of Vancouver. 
Out of the 21 columns, the analysis mainly focused on the most relevant fields related to answering the business question and calculating the correlation between Height Range ID and Diameter

•	Student ID: Unique identifier for each student.

•	Tree ID: A unique identifier for each tree.

•	Civic Number: Specifies the tree's location.

•	Common Name: Identifies the species as Bowhall Red Maple.

•	Height Range ID: Assigns trees to predefined height categories.

•	Height Range: Describes the height range (e.g., 0–10 ft, 10–20 ft).

•	Diameter: Represents the tree trunk diameter in inches.

•	Date Planted: Records the planting date for each tree


**Methodology:**

**• Data Collection and Preparation for Analysis:**

- Upload Data to AWS S3: Stored the dataset by creating a raw bucket in Amazon S3 for secure and scalable storage. 

**Figure 1:** Data Ingestion for Raw Bucket in S3
![DQ_Data Evaluated with ETL Pipeline (F5)](https://github.com/user-attachments/assets/7e29b11d-33a6-4c26-92d8-3fb447906bb3)


**• Data Profiling**

-  AWS Glue Data Brew was used for data profiling on the dataset we ingested to the S3 raw bucket, and then identify quality issues like missing values and inconsistent formatting. In order to save the profiled data, a bucket was created with subfolders for profiled and cleaned data, and profiling results were stored in the data profiling folder for analysis.

**Figure 2:** Data Profile Overview
![DQ_Data Profiling  (F2)](https://github.com/user-attachments/assets/4bbfb14b-fe43-4ff2-96e8-3c18ec8c6d38)


**• Data Cleaning**

- The data cleaning procedure in this step involves handling missing values, correcting data types, renaming columns, and removing irrelevant columns, resulting in seven key fields for analysis.


**Figure 3:** Data cleaning 
![DQ_Data Cleaning (F3)](https://github.com/user-attachments/assets/235ac6fe-8b57-4111-8ad0-91cf039e66f0)

 
• **Data Quality Evaluation using ETL Pipeline**

- In this step of the process, An ETL Pipeline is created to evaluate the quality of the cleaned dataset stored in the raw bucket.

**Figure 4:** ETL pipeline for Data Governance
![DQ_ETL Pipeline for Data Governance (F4)](https://github.com/user-attachments/assets/152595c4-35e6-4950-868e-9059c3c129d8)


- The pipeline involves quality checks for completion, uniqueness, and freshness, ensuring that Height ID range and Diameter fields have 99% or greater completion, Tree IDs have a uniqueness rate of 99% or higher and data records are fresh (updated within the last 24 hours).
 
 
 **Figure 5:** Data Evaluated with ETL Pipeline 
 ![DQ_Data Evaluated with ETL Pipeline (F5)](https://github.com/user-attachments/assets/272fa220-9c7b-4e33-82f8-8276f3121ff9)


- The results of this ETL pipeline are stored in two subfolders created as Passed and Failed in a new S3 transform bucket created as ‘Data-Quality.’

**Figure 6**: Pipeline output in S3 Bucket – Quality Passed 
![DQ_Pipeline output- System – Quality Passed (F6)](https://github.com/user-attachments/assets/93874c57-ba7f-4711-a1ce-0e6ef192b9a8)


- As per the Pipeline output in the S3 transform Bucket, there are no failed data recorded.

**Figure 7:** Pipeline output in S3 Bucket – Quality Failed
![DQ_Pipeline output- System – Quality failed (F7)](https://github.com/user-attachments/assets/d595f2e8-36e8-4c7a-8af3-d8ca9dce5b09)

 
 
 **Tools and Technologies:**

**• AWS S3:**

- Used for storing the raw, cleaned, and transformed datasets securely.

**• AWS Glue DataBrew:** 

- For profiling and cleaning the data.

**• AWS Glue:**

- Facilitates data transformation and ETL (Extract, Transform, Load) processes.


**Project Deliverables:**

Insights generated from the exploratory analysis, including:
• A fully implemented ETL pipeline for data quality control.
• Organized S3 bucket with subfolders for passed and failed records.
• Quality assurance report summarizing the completeness, uniqueness, and freshness metrics

**Timelines:**

• Data Upload to S3: Day 1

• Data Upload to S3: Day 1

• Data Profiling and Quality Evaluation: Days 2–3

• ETL Pipeline Implementation: Days 4–5

• Data Validation and Categorization: Day 6

• Report and Deliverables Submission: Day 7

The project will be completed within seven days, following a structured timeline to ensure efficient execution and delivery. On Day 1, the raw dataset will be uploaded to AWS S3 for secure storage, laying the foundation for quality control. During Days 2–3, data profiling will be conducted using AWS Glue DataBrew to evaluate data quality through completeness, uniqueness, and freshness rules, ensuring that key variables like Height ID range and Diameter meet accuracy and reliability standards. Over Days 4–5, the ETL pipeline will be implemented to process the cleaned data, applying quality rules and categorizing high-quality records into appropriate subfolders (Passed and Failed) within an S3 bucket. Day 6 will focus on data validation, ensuring compliance with quality rules and reviewing categorized outputs for completeness and accuracy to prepare them for advanced analysis. Finally, on Day 7, a detailed quality assurance report will be generated, summarizing the evaluation process and outcomes, ensuring the dataset is ready for subsequent analysis and decision-making.
