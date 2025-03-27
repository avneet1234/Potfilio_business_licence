# Potfilio_business_licence
# Project Description:
This project explores the implementation of AWS cloud computing technologies to enhance data processing, security, and governance. Using the business licenses dataset from the Vancouver Data Portal, the project demonstrates a complete data pipeline using AWS services such as S3, Glue DataBrew, Athena, KMS, CloudWatch, and CloudTrail.

The project focuses on data ingestion, transformation, storage, security, and monitoring, ensuring high data quality and accessibility. A structured ETL (Extract, Transform, Load) pipeline was developed, including data encryption, versioning, cross-region replication, and data validation mechanisms. The system was designed to provide a scalable, cost-effective, and secure cloud-based data processing solution. A Draw.io visualization was created to illustrate the data flow, security measures, and AWS service integrations.

# Project Title:
Implementation of AWS Cloud Services for Secure and Scalable Data Management

# Project Objectives
**Develop a Secure and Scalable Data Pipeline using AWS Cloud Services**

The project aims to design and implement a cloud-based data processing pipeline using AWS services such as S3, Glue DataBrew, Athena, KMS, CloudWatch, and CloudTrail. The pipeline will handle data ingestion, transformation, storage, and retrieval, ensuring that it is efficient, secure, and capable of scaling based on business requirements. The structured approach allows for automated workflows, reducing manual effort and ensuring consistent data handling.

**Implement Data Processing Automation for Structured Storage and Analytics**

To enable seamless data processing, the project automates the extraction, transformation, and loading (ETL) of the business licenses dataset. AWS Glue DataBrew is used to clean and transform raw data before storing it in an optimized format in AWS S3. The transformed data is structured into specific folders based on usability—CSV for analysts and Parquet for system performance optimization. This approach improves data retrieval speed and efficiency for analytics and reporting.

**Ensure Data Security and Governance through Encryption, Versioning, and Access Controls**

Security is a key concern when handling large datasets. The project implements multiple layers of security, including:

AWS Key Management Service (KMS) for AES-256 encryption of data in S3 buckets.

S3 Versioning, which keeps multiple versions of each file, allowing recovery from accidental deletions or modifications.

Access control policies and governance mechanisms to restrict unauthorized access, ensuring data integrity and compliance with security standards.

**Optimize Query Performance and Cost Efficiency Using AWS Athena and Parquet Format**

The project leverages AWS Athena, a serverless interactive query service, to analyze structured data stored in S3. The data is stored in both CSV and Parquet formats—CSV for easy human readability and Parquet for optimized queries. Parquet format significantly reduces query execution time and cost by minimizing the amount of data scanned. This enhances business intelligence and decision-making capabilities.

**Monitor and Audit System Performance Using AWS CloudWatch and CloudTrail**

AWS CloudWatch is used to track key metrics such as S3 storage usage, ETL process performance, and data pipeline health. CloudWatch alarms notify users of anomalies or failures in data processing.

AWS CloudTrail logs all API activities in the cloud environment, providing a detailed audit trail of changes made to datasets and pipeline configurations. This ensures transparency, accountability, and regulatory compliance.

**Enhance Disaster Recovery Capabilities with Cross-Region Replication and Versioning**

To ensure data availability even in case of system failures, the project uses AWS S3 Cross-Region Replication (CRR). This automatically copies data from the primary region to a secondary AWS region, protecting against data loss due to regional outages. Combined with S3 versioning, the system maintains previous versions of files, ensuring robust disaster recovery and business continuity.

# Dataset

The dataset contains the following variables (columns):

**FOLDERYEAR** – The year associated with the business license record.

**LicenceRSN** – A unique identifier for the license record.

**LicenceNumber** – The official license number assigned to the business.

**LicenceRevisionNumber** – The revision number of the license (if updated).

**BusinessName** – The registered name of the business.

**BusinessTradeName** – The trade name under which the business operates (if different from BusinessName).

**Status** – The current status of the license (e.g., Active, Expired).

**IssuedDate** – The date the business license was issued.

**ExpiredDate** – The expiration date of the license.

**BusinessType** – The primary category of the business (e.g., Retail, Food Services).

**BusinessSubType** – A more specific classification of the business type.

**Unit** – The unit number of the business location (if applicable).

**UnitType** – The type of unit (e.g., Suite, Floor).

**House** – The building number of the business location.

**Street** – The street name of the business address.

**City** – The city where the business is located.

**Province** – The province where the business operates.

**Country** – The country where the business is registered.

**PostalCode** – The postal code of the business location.

**LocalArea** – The local area within the city where the business is situated.

**NumberofEmployees** – The reported number of employees working at the business.

**FeePaid** – The fee amount paid for the business license.

**ExtractDate** – The date the data was extracted from the system.

**Geom** – Geometric data related to the business location.

**geo_point_2d** – The geographic coordinates (latitude and longitude) of the business location.

# Methodology

# 1. Data Collection and Preparation:
![image](https://github.com/user-attachments/assets/7d1c4816-77d7-488d-ab1c-fe0e17dae4c2)

In this project, the data collection and preparation process involved using various AWS services to ensure the dataset's integrity, security, and accessibility for further analysis. The data source for this project was the business licenses dataset from the Vancouver Data Portal.
# EC2 Instance
![Screenshot 2025-03-03 153251](https://github.com/user-attachments/assets/ea299838-6ce8-4d1f-91fd-574e44199522)

To begin, I utilized Amazon EC2 instances for performing initial data extraction and preprocessing. EC2 instances allowed me to set up a flexible environment for data collection, where I could run custom scripts to access and pull data from the Vancouver Data Portal, preparing it for transfer to the AWS cloud environment. This setup helped manage the data collection process efficiently by enabling the use of diverse tools and libraries.

After gathering the raw data, the next step was to upload it to Amazon S3 buckets, ensuring that the files were organized appropriately for processing and future retrieval. I structured the data into multiple S3 buckets, including Raw, Transformed, and Curated, to ensure proper organization. These buckets also provided a secure storage space for the data, where I implemented KMS encryption to safeguard sensitive information, complying with security standards.

**Data Cleaning:**

Once the data was in S3, I used AWS Glue DataBrew to clean and transform it. DataBrew provided an intuitive visual interface that enabled me to easily identify and rectify missing values, correct data types, and eliminate duplicates. This tool performed a comprehensive set of operations, ensuring that the dataset was free of inconsistencies and ready for deeper analysis.

The cleaned data was then transformed into two different formats: CSV for human-readable use and Parquet for efficient storage and fast querying in analytical applications like AWS Athena. The Parquet format, in particular, helped optimize the query performance and reduced storage costs by minimizing the amount of data scanned.
# Data Profiling
![Screenshot 2025-03-05 135447](https://github.com/user-attachments/assets/99cc931c-8700-4b94-b677-dee6745aa142)

# After Cleaning job, csv and parquet stored in S3 User and System folders
![Screenshot 2025-03-05 191730](https://github.com/user-attachments/assets/a9c968ea-7341-4a65-ac35-5f5088aaca05)
![Screenshot 2025-03-05 191757](https://github.com/user-attachments/assets/b022d83b-4e6e-4b73-b479-9bb63bab36c0)


# 2. Descriptive Statistics
# Data cataloging
![Screenshot 2025-03-05 180031](https://github.com/user-attachments/assets/27e55f4d-f45d-44e2-ae60-407f07922988)
![Screenshot 2025-03-05 191827](https://github.com/user-attachments/assets/9731cdda-bfbd-4ac9-a830-7cd46da8994a)
![Screenshot 2025-03-05 210406](https://github.com/user-attachments/assets/a2a2331d-a770-486e-944a-7bc6058ecda7)

**Querying Data with AWS Athena**
![Screenshot 2025-03-25 112807](https://github.com/user-attachments/assets/910d891a-ff1e-4cdf-87c7-bb00cb34dd92)
![Screenshot 2025-03-25 112821](https://github.com/user-attachments/assets/7d509f4e-63f3-4742-bb17-7f853f9174da)
![Screenshot 2025-03-25 112837](https://github.com/user-attachments/assets/289b5e1b-089c-470b-8076-c6db6754c307)

After cataloging the data using AWS Glue Crawler, AWS Athena was utilized to execute SQL queries on the tables created in the business-licences-data-catalogue database. These queries enabled efficient retrieval of key summary statistics for further analysis.

**Execution of Basic SQL Queries**

To generate descriptive statistics, SQL queries were run on the cataloged tables, focusing on key attributes in the dataset.

**Total Number of Records in Each List**

The COUNT() function was used to determine the total number of records in key tables, including business licenses, business types, and locations.

This provided an overview of the dataset size and completeness.

**Number of Unique Entries**

The DISTINCT function was applied to key columns such as license years, business categories, and city names to count the number of unique values.

This analysis helped in understanding the dataset’s diversity in terms of time range, industry coverage, and geographic distribution.

**Range or List of Values Contained Within Each Dataset**

The MIN() and MAX() functions were used to determine the earliest and latest years in the dataset.

A GROUP BY query was executed to extract distinct business types and cities, providing a categorized list of values present in the dataset.

# 3. Data Visualization

# Visual ETL Pipeline Implementation
![Screenshot 2025-03-05 191019](https://github.com/user-attachments/assets/212cea6c-3efc-4e46-9061-558e71a600b7)
![Screenshot 2025-03-05 191542](https://github.com/user-attachments/assets/ca2179af-e308-4228-9c0a-2ac0675637e8)

The automation of the ETL processing was carried out using AWS Glue to streamline the management of the business license dataset. The dataset, which contains comprehensive business-related variables such as LicenceRSN, BusinessType, Status, NumberofEmployees, and FeePaid, was loaded from the S3 bucket and processed through various transformation steps, including categorization of business types, location data standardization, and adding timestamps for tracking processing time. The transformed data was then stored in CSV and Parquet formats, making it easily accessible for both analysis and reporting purposes.

# 2. Customer Segmentation
![Screenshot 2025-03-25 212142](https://github.com/user-attachments/assets/888c26ee-820b-41d1-a239-ec72ba6bd632)

By analyzing the business license dataset, customer segmentation was done based on business categories such as BusinessType (e.g., Retail, Food Services), BusinessSubType, and NumberofEmployees. This segmentation enabled an in-depth understanding of Vancouver's business landscape. For instance, businesses with Large Numbers of Employees versus Small Businesses could be analyzed to determine differences in fee payments (FeePaid) and business operations. The data also includes PostalCode and geo_point_2d, allowing geographic segmentation, enabling us to analyze trends across different regions of Vancouver. The dataset spans several years, allowing a longitudinal analysis of trends, such as shifts in business categories over time.

# Loading the Dataset:

A Visual ETL pipeline was implemented using AWS Glue. The raw business license data, stored in the S3 bucket (business-licenses-raw-van), was loaded into the ETL pipeline, which was named business-licenses-transformation-vancouver.

# Data Quality Rules

To ensure data integrity and consistency, the following data quality rules were applied:

Completeness: We ensured that columns like BusinessType, BusinessName, and FeePaid had at least 70% non-null values, ensuring critical business information was available for analysis.

Uniqueness: We validated that the LicenceRSN and LicenceNumber columns were unique, preventing duplicates in the dataset.

These quality checks ensured the dataset was clean and accurate for downstream processing.

# Conditional Routing Transformation
![Screenshot 2025-03-25 212031](https://github.com/user-attachments/assets/fda33e04-ad1e-4314-8027-5bf4eec07046)
![Screenshot 2025-03-25 212047](https://github.com/user-attachments/assets/ad79c0b0-e706-4908-9798-ab8e0b369cba)

A Conditional Router transformation was employed to segment the data based on the validation results:

Pass Folder: Data that passed all the quality checks (e.g., non-null FeePaid, unique LicenceRSN) was routed to this folder for further processing.

Fail Folder: Data that didn’t meet the required criteria (e.g., missing BusinessType, duplicate LicenceNumber) was routed here for further review.

Both the Pass Folder and Fail Folder schemas were modified to ensure that the data was compatible with the destination folders, preserving data integrity and making it easier to track the validation outcomes.

# Data Upload to S3 Bucket

After the data passed through the validation and transformation steps, it was uploaded back to the S3 bucket for further use:

Processed and Validated Data: The data that passed all quality checks was uploaded to the business-licenses-transformed-vancouver bucket, ready for analysis and reporting.

Unprocessed Data: Data that failed quality checks was uploaded to the business-licenses-fail-vancouver bucket for further investigation.

# Insights and Findings

# 1. Automated Data Transformation with AWS Glue
AWS Glue automated the ETL (Extract, Transform, Load) pipeline, streamlining the data processing workflow. This automation reduced manual interventions, ensuring accurate and timely transformations. Built-in validation checks for data completeness and uniqueness ensured that the processed data met quality standards, allowing reliable downstream analysis.

# 2. Scalable and Cost-effective Storage with Amazon S3
By storing the processed data in Amazon S3, the project benefited from scalable, cost-effective cloud storage. The use of the Parquet format optimized data storage, enabling faster query processing while minimizing storage costs. This allowed for easy scalability, catering to future data growth needs.

# 3. Real-time Processing and Data Tracking
The real-time capabilities of the cloud infrastructure ensured timely data processing and insights. The system incorporated timestamping for ETL processes, which helped track processing times and ensured the transparency and accountability of data operations.

# 4. Enhanced Data Security and Compliance
AWS's cloud environment provided robust data security through encryption and access control mechanisms. It also offered compliance features, ensuring that the dataset remained secure and that all access and processing actions were auditable.

# 5. Improved Data-Driven Decision Making
The use of cloud services enabled quick access to cleaned and transformed data, facilitating better decision-making. This cloud infrastructure allowed stakeholders to identify trends like license expiry or regional business activity, driving more informed business strategies.

# Recommendations

# 1. Implement Automated Data Quality Checks for Continuous Monitoring
While the current ETL pipeline ensures data quality through validation checks during processing, it's recommended to set up automated, continuous data quality checks. This would enable real-time monitoring for any inconsistencies or discrepancies in the dataset, ensuring the data remains accurate and reliable for business analysis and decision-making.

# 2. Leverage AWS Redshift for Advanced Analytics
To further optimize data processing and querying, integrating AWS Redshift for advanced analytics would allow for complex queries on large datasets with faster performance. Redshift’s scalable architecture would enable more efficient querying for deeper insights, particularly useful when handling larger datasets as the business grows.

# 3. Regularly Review and Update Data Security Protocols
Given the sensitive nature of business data, it's crucial to regularly review and update security protocols. While AWS Key Management Service (KMS) provides strong encryption, enhancing data governance with additional monitoring tools, such as AWS Macie for data privacy, would further secure the dataset and maintain compliance with industry regulations.

# 4. Incorporate Machine Learning for Predictive Analytics
Integrating AWS SageMaker for machine learning models can provide predictive analytics on business trends, such as forecasting license expirations or customer behavior patterns. Machine learning models could uncover hidden patterns that are not immediately visible through traditional data analysis, driving proactive business strategies.

# 5. Expand Cross-Region Replication for Increased Resilience
Currently, the use of S3 Cross-Region Replication (CRR) ensures data availability and disaster recovery. It is recommended to expand this setup to include multiple AWS regions for further enhancing business continuity and reducing the risk of data loss during regional outages, especially as the dataset grows and becomes more critical for operational decisions.

# Tools and Technologies:
**AWS Cloud Services.**
AWS S3 (Simple Storage Service): For raw data ingestion, storage of processed files (CSV, Parquet), and DataBrew/Glue job outputs.
Initial data file staging together with PowerShell script execution takes place on the AWS EC2 (Elastic Compute Cloud) platform.
AWS Glue DataBrew serves as a tool for data profiling and interactive data cleanup in addition to its transformation job execution capabilities.
AWS Glue Data Catalog serves as the central storage facility for metadata organization.
The AWS Glue Crawler function serves as a data catalog population system running automatically.
SQL commands in AWS Athena enable users to extract descriptive statistics from the S3 data that was cataloged through the system.

# Conclusion
In conclusion, the implementation of AWS cloud services for managing business license data has demonstrated a robust, scalable, and secure data pipeline. By leveraging AWS tools like S3, Glue DataBrew, Athena, and KMS, the project successfully automated data processing, ensured data quality, and optimized performance. The system offers enhanced data security, disaster recovery, and cost-efficiency while providing valuable insights for decision-making. With the integration of real-time monitoring and continuous data quality checks, the solution is poised for future growth, driving improved business strategies and data-driven outcomes. Regular updates and the integration of advanced analytics will further enhance its capabilities.



