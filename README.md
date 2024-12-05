# data-analyst-amenda

**Exploratory Data Analysis**

Project Description: The project analyzed academic integrity data from the MBA program at University Canada West (UCW) for 2024, focusing on understanding the distribution of academic violations across different course codes. The aim was to use AWS tools for data storage, processing, and visualization to identify and evaluate courses with the highest violation rates and recommend improvements for promoting academic honesty.

Project 1 Title: Maintaining Integrity: An Exploratory Data Analysis of Academic Violations at UCW
Objective: To address the question: Which Course accounts for the highest number of academic integrity violations?
This analysis aims to help UCW understand the distribution of violations across courses and recommend tailored strategies for improvement.
Dataset: The UCW Academic Integrity dataset is a CSV file containing academic integrity data for MBA students in 2024. It includes 10 columns and 50 records, providing insights into integrity trends across the MBA program. The dataset includes details such as:
•	Student ID: Unique identifier for each student.
•	Course Code: The course associated with the assignment. This includes six course codes; MBA601, MBA602, MBA603, and MBA604.
•	Assignment Type: The type of academic work. This includes three types; essay, group project, and presentation.
•	Turnitin Score: Percentage of similarity detected in the assignment.
•	Violation Occurrence: Whether a violation occurred (Yes/No).
•	Violation Type: Type of violation. This includes plagiarism and collusion.
•	Sanction Imposed: Penalty for the violation. This includes Grade Reduction, Warning, Expulsion, and None.
•	Appeal Status: Whether the sanction was appealed (Yes/No).
•	Final Decision: Outcome of the appeal (Pending, Dismissed or Upheld)
Methodology:
1-	Data Collection and Storage in AWS:
o	Upload Data to AWS S3: Store your dataset (e.g., CSV file containing academic integrity data) in Amazon S3 for secure and scalable storage.
 
2-	Data Cleaning and Profiling: 
o	AWS Glue DataBrew was used for data profiling and data cleaning. 
- Data Profiling Steps allowed to perform data profiling and detect data quality issues such as missing values, outliers, and inconsistent formatting.
 
-  Data Cleaning Steps cleaned the dataset by handling missing values, correcting data types, and renaming column
 

3-	Data Transformation and Pipeline Creation
o	After cleaning, the transformed data is stored in a separate S3 bucket named ‘academic-transformed-amenda’. 
o	This transformed data is optimized and stored in a Parquet format, which is suitable for efficient querying in AWS Athena.
 
o	An AWS Glue Data Catalog is created using Crawler to register the metadata for the cleaned dataset, including column names, data types, and file paths.
 

4-	Data Discovery and Querying with AWS Athena:
o	Compare Using AWS Athena, SQL queries will be run on the transformed data stored in the S3 bucket. The queries will explore relationships between variables such as Turnitin similarity scores, violation types, and sanctions
 
- This query result helps in analyzing patterns by course code and identifying trends related to academic integrity violations.
 

5-	Data Visualization and Insights
o	Query result is then exported to Microsoft Excel for data visualization:
- A Bar chart is generated visually to compare the number of violations rate across course Codes.
 
Table generated with summarized data generated with Athena
Course Code	Total Violations #	Total # of Students in each Course 	Violation Percentage from total
MBA603	12	12	52%
MBA601	12	13	48%
MBA604	0	12	0%
MBA602	0	13	0%

- Insights from these visualizations will help identify key trends, such as whether higher Turnitin similarity scores are correlated with higher violation rates or if certain departments experience more violations.

6-	Outcome and Insights:
o	Interpret the query results and identify departments with the highest concentration of violations.
o	Analyze potential reasons for the distribution, considering factors like department size or assignment complexity.
Tools and Technologies:
AWS S3:
•	Used for storing the raw, cleaned, and transformed datasets securely.

AWS Glue:
•	Used to create the Data Catalog and define metadata for the academic integrity dataset.
•	Facilitates data transformation and ETL (Extract, Transform, Load) processes.
AWS Athena:
•	Allows querying the dataset using SQL for analysis of academic violations by department and course code.
Microsoft Excel:
•	Used for additional data visualization and graphical representation of results.
SQL:
•	The primary language for querying and analyzing the dataset in AWS Athena.
Deliverables:
Insights generated from the exploratory analysis, including:
•	Identification of potential patterns and anomalies, such as departments or course codes with higher violation rates.
•	Trends related to Turnitin score ranges and the frequency of academic violations.
•	Insights into how different departments and courses are affected by academic integrity violations.
