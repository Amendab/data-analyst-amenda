**Exploratory Data Analysis**


**Project Title:** 

Urban Greenery Insights: An Exploratory Data Analysis of Bowhall Red Maple Trees in Vancouver



**Project Description:** 

This project focuses on analyzing data from the City of Vancouver’s Open Data Portal, specifically on Bowhall Red Maple trees planted between 2014 and 2024. The Exploratory Data Analysis (EDA) process began with examining and transforming raw data into structured, meaningful formats using AWS services. The primary objective was to uncover patterns and trends in tree planting by analyzing height categories, diameters, and annual planting activity. These insights aim to enhance the understanding of urban forestry practices and support the optimization of tree-planting strategies for better greenery management and sustainable urban planning.



**Objective:**


What patterns and insights can be derived from the planting activities of Bowhall Red Maple trees over the past decade (2014–2024)?
The analysis also aims to examine the correlation between Height Range ID and Diameter, offering deeper insights into the characteristics of planted trees. This will support recommendations for enhancing future urban forestry initiatives.

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

**•	Data Collection and Preparation for Analysis:**

- Upload Data to AWS S3: Stored the dataset by creating a raw bucket in Amazon S3 for secure and scalable storage.

**Figure 1:** Data Ingestion for Raw Bucket in S3

**•	Data Profiling**

-  AWS Glue Data Brew was used for data profiling on the dataset we ingested to the S3 raw bucket, and then identify quality issues like missing values and inconsistent formatting. In order to save the profiled data, a bucket was created with subfolders for profiled and cleaned data, and profiling results were stored in the data profiling folder for analysis.

**Figure 2:** Data Profile Overview

**•	Data Cleaning**

- The data cleaning procedure in this step involves handling missing values, correcting data types, renaming columns, and removing irrelevant columns, resulting in seven key fields for analysis.

**Figure 3:** Data cleaning 


•	Data Transformation

- An ETL Pipeline has been created to transform the cleaned data into structured and analyzable format. Under this exploratory analysis, one major goal was to determine whether there is a meaningful relationship between the two variables of the dataset; average Height Range ID and the average Diameter of the planted Bowhall Red Maple trees.

- The output of the pipeline is stored in a bucket created in S3 under 2 folders created as,
  - System Output: Data in Parquet format for efficient querying.
  - User Output: Data in CSV format for interpretation


**Figure 4:**  ETL Pipeline


**•	Obtaining Results**

- To obtain the analytical result, SQL query will be run by using the ETL pipeline output saved under User (with CSV format) in the S3 bucket.

**Figure 5:** Pipeline output – User

- This query result helps in analyzing a meaningful relationship between the key variables of the dataset; average Height range ID and the average diameter of the planted Bowhall Red Maple trees.


**Figure 6:** Analysis result obtained by running SQL query on the ETL pipeline  


**•	Data Visualization and Insights**

- Using the ‘City of Vancouver’s Open Data Portal’, the data has been visualized:

- A Column chart has been used to identify valuable patterns such as the average Height range ID and the average diameter.

- Insights from these visualizations will help to summarize a data set's main characteristics and identify the correlation between variables


**Figure 7**:  Data Visualization for two metrics (average height range ID & average diameter) 


•	Analyze the Outcome and gain Insights of the exploratory analysis:

- A strong correlation was observed between the Height Range ID and Diameter, indicating that taller trees (higher Height Range ID) were associated with larger diameters. For example, in 2015, the average Height Range ID and Diameter peaked, signifying a preference for planting taller and more mature trees.

- Planted tree Size Preferences: Trees in the 10–20 ft range (Height Range ID: 1) were the most commonly planted.

- Yearly Variations: Taller trees were planted in years like 2015 and 2018, reflecting potential strategic shifts.
Tools and Technologies:

•	AWS S3:

- Used for storing the raw, cleaned, and transformed datasets securely.

- Used to run SQL query for user output generated through ETL Pipeline.

•	AWS Glue DataBrew: 

- For profiling and cleaning the data.

•	AWS Glue:

- Facilitates data transformation and ETL (Extract, Transform, Load) processes.

•	City of Vancouver’s Open Data Portal:

- Used to source datasets for analysis and generate data visualization and graphical representation of results.


**Project Deliverables:**

Insights generated from the exploratory analysis, include:

•	Planting Trends: Identification of yearly trends in planting Bowhall Red Maple trees, highlighting years with the highest planting activity.

•	Height and Diameter Patterns: Analysis of height and diameter variations over the years, uncovering preferences for specific tree sizes.

•	Tree Size Preferences: Insights into the most frequently planted height ranges and diameter consistency over time.

•	Planting Strategy Evaluation: Anomalies or shifts in planting strategies, such as years with taller trees or wider diameters being planted.
