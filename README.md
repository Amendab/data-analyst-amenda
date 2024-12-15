**Data Wrangling**

**Academic Integrity Wrangling at UCW for Preparing Data to gain valuable Insights**

**Project Description**: 

This project focuses on data wrangling to prepare a clean and structured dataset to analyze academic integrity violation insights at the University Canada West (UCW). 
![DW_Analysis Process (F0)](https://github.com/user-attachments/assets/499f1b1a-3672-4205-8a34-07b818669051)


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

• **Data Collection and Preparation for Analysis:**

- Upload Data to AWS S3: Stored the dataset by creating a raw bucket in Amazon S3 for secure and scalable storage. 

**Figure 1**: Data Ingestion for Raw Bucket in S3
<img width="956" alt="DW_Data Ingestion for Raw Bucket in S3 (F1)" src="https://github.com/user-attachments/assets/8880af7b-7b90-4cc2-818e-aec53cc7c7e2" />

 
• **Data Profiling:**

- AWS Glue Data Brew was used for data profiling on the dataset we ingested to the S3 raw bucket, and then detected data quality issues such as missing values, outliers, and inconsistent formatting. In order to save the profiled data, a bucket was created with subfolders for profiled data.

**Figure 2**: Data Profiling 
![DW_Data Profiling  (F2)](https://github.com/user-attachments/assets/144793f1-56dc-4be2-9507-d8397e7871fa)

 
**• Data Cleaning:**

- The data cleaning procedure in this step involves handling missing values, correcting data types, renaming columns, and removing irrelevant columns,

**Figure 3:** Data Cleaning
![DW_Data Cleaning (F3)](https://github.com/user-attachments/assets/e9f3c76f-14e2-4d40-a003-444ec5e44a7e)

 
- By publishing a recipe, we can refer to what changes we have made to the dataset

**Figure 4**: Data Cleaning recipe
![DW_Data Cleaning Receipe (F4)](https://github.com/user-attachments/assets/bebc39be-6e78-41e7-b724-1fed3b66549a)


**• Data Cataloging**

- After cleaning, the transformed data is stored in a separate S3 bucket created for transformed data in the form of Parquet format, which is suitable for efficient querying in AWS Athena.

- **Figure 5**: Cleaning output – System
 <img width="959" alt="DW_Cleaning output _System (F5)" src="https://github.com/user-attachments/assets/218c0741-8971-49dd-85d6-e793016b5cad" />


- An AWS Glue Data Catalog is then created using Crawler to register the metadata for the cleaned dataset, including column names, data types, and file paths.

**Figure 6:** Crawler
<img width="959" alt="DW_Crawler (F6)" src="https://github.com/user-attachments/assets/f4275ace-b2fc-474e-be05-236cfe662430" />

 **Figure 7:** Data Cataloge
![DW_Data Catalog (F7)](https://github.com/user-attachments/assets/0bc67890-8c53-4fac-8be2-ef4e47034e04)


**• Data Discovery and Querying with AWS Athena:**

- Using AWS Athena, SQL queries will be run on the transformed data stored in the S3 bucket. The queries will explore relationships between variables such as Turnitin similarity scores, violation types, and sanctions

- This query result helps in analyzing patterns by course code and identifying trends related to academic integrity violations.

**Figure 8**: AWS Athena for running SQL

![DW_AWS Athena for running SQL (F8)](https://github.com/user-attachments/assets/f9e0d9e1-1015-4b4e-aaaf-04675325f312)

 
**• Data Visualization and Insights**

- Query result is then exported to Microsoft Excel for data visualization:

- A Bar chart is generated visually to compare the number of violations rate across course Codes. Insights from these visualizations will help identify key trends, such as the course code that has the highest number of violation rate or the trends of violation types in which most students are involved.

**Figure 9:** Data Visualization

<img width="359" alt="DW_Data Visualization (F9)" src="https://github.com/user-attachments/assets/15228774-53cb-4d9d-8b56-37ff8bbd85e9" />



**• Analyzing the Outcome and Generate Insights:**

- Interpret the query results and identify departments with the highest concentration of violations.
- Analyze potential reasons for the courses involved with violations, what sanctions has the universities imposed, etc.


**Tools and Technologies:**

**• AWS S3:**
- Used for storing the raw, cleaned, and transformed datasets securely.

**• AWS Glue:**
- Used to create the Data Catalog and define metadata for the academic integrity dataset.
- Facilitates data transformation and ETL (Extract, Transform, Load) processes.

**• AWS Athena:**
- Allows querying the dataset using SQL for analysis of academic violations by department and course code.

**• Microsoft Excel:**
- Used for additional data visualization and graphical representation of results.

**• SQL:**
- The primary language for querying and analyzing the dataset in AWS Athena.

**Project Deliverables:**

Insights generated from the exploratory analysis, including:

• Identification of potential patterns and trends, such as course codes with higher violation rates.

• Trends related to Turnitin score ranges and the frequency of academic violations.

• Insights into how different courses are affected by academic integrity violations.

**Timelines:**

• Data Upload to S3: Day 1

• Data Profiling and Cleaning: Days 2–3

• Data Transformation and Cataloging: Days 4–5

• Athena Query Validation: Day 6

• Report and Deliverables Submission: Day 7

The project will be completed within 7 days, following a structured timeline to ensure efficient progress and delivery. On Day 1, the raw dataset will be uploaded to AWS S3 for secure storage, setting up the foundation for subsequent steps. Day 2 focuses on data profiling using AWS Glue DataBrew to identify quality issues such as missing values, outliers, and inconsistent formatting. Over Days 3 and 4, data cleaning will be conducted to address these issues, standardizing formats and ensuring the dataset is well-structured. On Day 5, the cleaned data will be transformed into a Parquet format and stored in a dedicated bucket for optimized querying. Day 6 involves cataloging the data using AWS Glue Crawlers, enabling metadata registration and preparation for further analysis. Finally, on Day 7, a comprehensive diagnostic report will be generated, detailing the findings and ensuring the dataset's readiness for advanced analysis and insights.
