**Descriptive Data Analysis**


**A Descriptive Analysis of Bowhall Red Maple Trees using Height Trends and Insights**


**Project Description:**

This project leverages the City of Vancouver’s Streets and Transportation dataset, detailing public boulevard trees, including species, locations, and characteristics. Utilizing AWS services for data ingestion, profiling, cleaning, and transformation, the analysis focuses on Bowhall Red Maple trees planted between 2014 and 2024. By categorizing Height Range IDs, the descriptive analysis explores trends in yearly planting patterns and average height distributions. The insights aim to support urban forestry practices, sustainable city planning, and improved environmental management for a greener urban future.

![DA_Analysis Process (F0)](https://github.com/user-attachments/assets/da0f20cf-f5b4-4916-9a33-1d36686251e2)



**Objective:**

To perform a descriptive analysis of Bowhall Red Maple trees, specifically investigating the yearly planting trends and average Height Range ID of trees planted in 2015. This metric aims to offer valuable insights into planted tree patterns and urban forestry decisions.



**Dataset:**

The dataset file used in this exploratory analysis had 21 columns and 429 records detailing the Bowhall Red Maple trees planted in Vancouver between 2014 and 2024. This comprehensive dataset provides a detailed overview of planting trends, tree sizes, and locations, serving as a foundation for evaluating urban forestry strategies to implement in the city of Vancouver. 
Out of the 21 columns, the analysis mainly focused on the most relevant fields related to answering the business question and calculating the correlation between Height Range ID and Diameter

-	Student ID: Unique identifier for each student.

-	Tree ID: A unique identifier for each tree.

-	Civic Number: Specifies the tree's location.

-	Common Name: Identifies the species as Bowhall Red Maple.

-	Height Range ID: Assigns trees to predefined height categories.

-	Height Range: Describes the height range (e.g., 0–10 ft, 10–20 ft).

-	Diameter: Represents the tree trunk diameter in inches.

-	Date Planted: Records the planting date for each tree

  

**Methodology:**

  •	Data Collection and Preparation for Analysis:
- Upload Data to AWS S3: Stored the dataset by creating a raw bucket in Amazon S3 for secure and scalable storage. 

**Figure 1:** Data Ingestion for Raw Bucket in S3
![DA_Data Ingestion for Raw Bucket in S3 (F1)](https://github.com/user-attachments/assets/5216375f-81ef-41af-937f-f53677f50156)


•	**Data Profiling**
-  AWS Glue Data Brew was used for data profiling on the dataset we ingested to the S3 raw bucket, and then identify quality issues like missing values and inconsistent formatting. In order to save the profiled data, a bucket was created with subfolders for profiled and cleaned data, and profiling results were stored in the data profiling folder for analysis.

**Figure 2:** Data Profile Overview
![DA_Data Profiling  (F2)](https://github.com/user-attachments/assets/195824d0-4165-4524-9e06-30e0111850e8)


**•	Data Cleaning**

- The data cleaning procedure in this step involves handling missing values, correcting data types, renaming columns, and removing irrelevant columns, resulting in seven key fields for analysis.

**Figure 3:** Data cleaning 
![DA_Data Cleaning (F3)](https://github.com/user-attachments/assets/29dd655d-1089-4ba2-ab78-d04e6fc153ed)


**•	Data Transformation**
- An ETL pipeline was designed to transform the cleaned data into a structured and analyzable format. In this descriptive analysis, the primary goal was to analyze the Height Range IDs of Bowhall Red Maple trees planted specifically in 2015. The pipeline focuses on summarizing and categorizing the data to identify trends in tree height distributions over time, providing actionable insights into urban forestry practices.
- The output of the pipeline is stored in a bucket created in S3 under 2 folders created as,
    - System Output: Data in Parquet format for efficient querying
    - User Output: Data in CSV format for interpretation.
    
**Figure 4:** ETL Pipeline
![DA_ETL Pipeline (F4)](https://github.com/user-attachments/assets/d4996889-0b10-4a70-8808-afe847504e71)


**•	Obtain the Results**

- To obtain the analytical result, SQL query will be run by using the ETL pipeline output saved under User (with CSV format) in the S3 bucket.

**Figure 5**: Pipeline output – User
![DA_Pipeline output – User (F5)](https://github.com/user-attachments/assets/a744b4b3-c3ab-4024-9f78-b2c97614d3bb)


- This query result aids in analyzing the distribution of Height Range IDs of the planted Bowhall Red Maple trees, providing valuable insights into tree height trends and urban forestry practices.

**Figure 6**: SQL Results

<img width="683" alt="DA_SQL Results (F6)" src="https://github.com/user-attachments/assets/6af22a3e-401c-4dd1-9abf-d0eefbc45133" />


**•	Data Visualization and Insights**

- Using the ‘City of Vancouver’s Open Data Portal’, the data has been visualized:

- A Column chart has been used to identify valuable patterns such as the average Height range ID.

- Insights from these visualizations will help to summarize a data set's main characteristics and identify trends and patterns of data.

**Figure 7:** Height ID Categories based on year
<img width="923" alt="DA_Data Visualization (F6)" src="https://github.com/user-attachments/assets/76af31b8-dc82-4387-b910-1e4634a2c33c" />


**•	Analyze the Outcome and gain Insights of the descriptive analysis:**

- Average Height Range ID in 2015: The average Height Range ID of Bowhall Red Maple trees planted in 2015 was calculated as 1.769 through the SQL result. This result is consistent with the analysis from the City of Vancouver Open Data Portal, which confirms the accuracy and reliability of the pipeline and analysis process
- Tree Planting Trends (2014–2024): The highest number of Bowhall Red Maple trees was planted in 2015, with a steady decline observed in subsequent years.
- Height Range ID #1 (trees with heights between 10' and 20') dominated the planting trends, reflecting a preference for smaller to medium-sized trees.
- Categorical Insights on height Range ID Distribution:
- Height Range ID #1: The most planted category.
- Height Range ID #2: The second most common, suggesting a focus on moderate-height trees.
- Height Range IDs #0 and #3: Fewer trees planted in these categories, indicating they are less favored by the city's urban forestry practice



**Tools and Technologies:**

**• AWS S3:**

•	Used for storing the raw, cleaned, and transformed datasets securely.

•	Used to run  SQL query for user output generated through ETL Pipeline.

**• AWS Glue DataBrew:**

•	For profiling and cleaning the data.

**• AWS Glue:**

•	Facilitates data transformation and ETL (Extract, Transform, Load) processes.

**• City of Vancouver’s Open Data Portal:**

•	Used to source datasets for analysis and generate data visualization and graphical representation of results.



**Project Deliverables:**

Insights generated from the Descriptive analysis, include:

•	Planting Trends: Identification of yearly trends in planting Bowhall Red Maple trees, highlighting years with the highest planting activity.

•	Descriptive Analysis:

- Insights into yearly planting trends 
- Analysis of Height Range ID categories
- Metric: Average Height Range ID for trees planted in 2015.

