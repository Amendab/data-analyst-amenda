**Diagnostic Analysis**


**A Diagnostic Data Analysis of UCW's Student Academic Integrity Dataset**


**Project Description**: 

This project focuses on conducting a diagnostic analysis to identify and address data quality issues in the academic integrity dataset from University Canada West (UCW) by using AWS services. Using AWS Glue DataBrew, the primary objective is to profile the data and diagnose missing values, outliers, and inconsistent formatting. Once the areas are diagnosed, they can be cleaned. This will ensure that the dataset is clean, structured, and ready for analysis, enabling the extraction of insights into academic integrity trends and issues, and facilitating informed actions.


![DiagAn_Analysis Process (F0)](https://github.com/user-attachments/assets/cdde3916-c8d9-4fb1-92d0-b6593f775547)


**Objective:** 

The primary objective is to profile the UCW dataset to detect data quality issues such as missing values, inconsistencies, and outliers. By using AWS Glue DataBrew's profiling features, the project ensures the dataset is refined and well-documented for further analytical use.


**Background:** 

Data profiling is a crucial step in data analysis that provides a detailed understanding of a dataset's structure and quality. This project focuses on the UCW dataset, which contains records related to academic performance and integrity. Using AWS Glue DataBrew, the project identifies key data quality issues and suggests potential improvements to prepare the dataset for future analysis.

**Dataset**: 

The UCW Academic Integrity dataset hat has been used for this analysis is a CSV file containing academic integrity data for MBA students in 2024. It includes 10 columns and 50 records, providing insights into integrity trends across the MBA program. The dataset includes details such as:

•	Student ID: Unique identifier for each student.

•	Course Code: The course associated with the assignment. This includes six course codes; MBA601, MBA602, MBA603, and MBA604.

•	Assignment Type: The type of academic work. This includes three types; essay, group project, and presentation.

•	Turnitin Score: Percentage of similarity detected in the assignment.

•	Violation Occurrence: Whether a violation occurred (Yes/No).

•	Violation Type: Type of violation. This includes plagiarism and collusion.

•	Sanction Imposed: Penalty for the violation. This includes Grade Reduction, Warning, Expulsion, and None.

•	Appeal Status: Whether the sanction was appealed (Yes/No).

• Final Decision: Outcome of the appeal (Pending, Dismissed or Upheld).


**Methodology**:

**•	Data Collection and Preparation for Analysis:**

- Upload Data to AWS S3: Stored the dataset by creating a raw bucket in Amazon S3 for secure and scalable storage.

**Figure 1**: Data Ingestion for Raw Bucket in S3
<img width="956" alt="DiagAn_Data Ingestion for Raw Bucket in S3 (F1)" src="https://github.com/user-attachments/assets/fe297f5e-3f67-4387-b6c6-f784608ec043" />

 
**•	Data Profiling with AWS Glue DataBrew:**

- Configure AWS Glue DataBrew to profile the dataset.

- Missing values (e.g., 10% missing in the Violation Type column).

- Outliers in numerical fields (e.g., Turnitin Score).

- Formatting inconsistencies (e.g., column names having extra spaces in between).

- Review the completeness, accuracy, and distribution of data
 

**Figure 2:** Data Profiling overview
![DiagAn_Data Profiling overview (F2)](https://github.com/user-attachments/assets/1f6ce57d-9c88-412f-a5d3-6ca8ce5d260c)


**Figure 3:** Data Profiling column statistics
<img width="955" alt="DiagAn_Data Profiling column statistics (F3)" src="https://github.com/user-attachments/assets/7911268c-f018-426a-8593-8623dc806d13" />


**•	Gather Insights from the Data Profiling overview:**

- Identify missing or inconsistent data columns, identify common violation types, and understand data variability, including Turnitin score distributions.


**•	Provide Data Cleaning Suggestions**
- Based on profiling results, outline steps to clean and standardize the data by filling missing values with appropriate defaults or estimates, removing duplicates and correcting formatting errors, and standardizing column names and data types.


**Tools and Technologies:**

•	AWS S3:

Used for storing the raw, cleaned, and transformed datasets securely.

•	AWS Glue DataBrew: 

For Data profiling and diagnosing issues in the dataset.


**Project Deliverables:**

•	Data Profiling insights:
- Details on missing values, inconsistencies, and outliers.
- Visualizations (e.g., histograms, box plots) summarizing data quality insights.

•	Insights or Recommendations for Cleaning and further analyzing practices:
- Specific steps to address identified quality issues.
- A documented DataBrew recipe highlighting all profiling and suggested cleaning actions.


**Timelines:**

•	Data Upload to S3: Day 1
The raw academic integrity dataset will be uploaded to an AWS S3 bucket for secure and structured storage. This step sets the foundation for the analysis process.

•	Data Profiling and Cleaning: Days 2–3
AWS Glue DataBrew will be used to perform data profiling, identifying issues such as missing values, outliers, and inconsistent formatting. Data cleaning will address these issues by standardizing formats, correcting errors, and ensuring data quality.

•	Data Transformation and Storage: Days 4–5
The cleaned dataset will be transformed into a Parquet format for optimized querying and stored in a separate S3 bucket designated for processed data.

•	Data Cataloging: Day 6
An AWS Glue Crawler will be used to catalog the transformed dataset, registering metadata such as column names, data types, and file paths to ensure readiness for further analysis.

•	Diagnostic Report Creation: Day 7
A comprehensive diagnostic report will be generated, summarizing findings from the data profiling and cleaning steps, and confirming the dataset's quality and readiness for advanced analysis.
