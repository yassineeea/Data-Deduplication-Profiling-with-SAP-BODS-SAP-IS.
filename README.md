# Data Quality and Deduplication Project

## Tools Used

- **SAP Business Object Data Services (BODS)**: ETL tool for data integration, data quality, data profiling, and data cleansing.
- **SAP Information Steward (IS)**: Tool for data profiling, data quality monitoring, metadata management, and data governance.
- **Power BI**: Business analytics tool for data visualization, reporting, and interactive dashboards creation.
- **Hana Database**: In-memory, column-oriented, relational database management system for real-time data processing and analytics.

## Data Description

The dataset analyzed comprised 13 columns and 21,748 rows, focusing on customer data from the SAP system, stored in the HANA database. It included customer information and demographics related to various business operations. The dataset was extracted from the HANA DB of SANOFI Client.

## Data Extraction

In the data extraction phase, we connected SAP ECC to the HANA database and created a job in SAP BODS to extract essential customer data (KNA1). We focused on customers with open items, recent sales documents, or cleared items, following the client's specific requirements to ensure only relevant data was migrated.

## Data Profiling

During the data profiling phase, we implemented various types of profiling, including:

1. **Uniqueness Profiling**: Conducted using Information Steward, identifying that 34.38% of entries in the 'NAME' and 'ADDRESS' columns were exact duplicates. This indicated areas requiring attention for data quality improvement.

2. **Redundancy Profiling**: Assessed the degree of overlap and duplication of data values between two sets of columns.

3. **Columns Profiling**: Determined the values and characteristics of data elements, including string lengths for each column to verify data consistency and compliance.

## Data Deduplication

To address manual data entry duplications, we used two approaches:

1. **SAP BODS MatchBatch Component**:
   - Configured matching criteria based on NAME and ADDRESS.
   - Used methods such as Rule Based, Weighted Score, and Combination.
   - Explored matching options including Match Score, No Match Score, and Contribution.

2. **SAP Information Steward Data Cleansing Advisor Component**:
   - Identified matching clusters and displayed matching records with confidence levels (High, Medium, and Low).

## Data Analysis and Visualization

The deduplication results were made more readable using dashboards developed with Microsoft Power BI. Main dashboard indicators included:

1. **Number of Duplicates**: Displays the total number of duplicates present in the system.
2. **Clusters**: Lists or visually represents the clusters identified in the data.
3. **Location by Break Key**: Shows the geographic distribution or location of records within each cluster.

## Findings

1. **Comparison between BODS & IS**:
   - SAP BODS offers flexibility and precision but requires technical expertise.
   - SAP Information Steward provides better visibility of results and is suitable for users prioritizing data governance.

2. **Data Quality Improvement**:
   - Implementing robust data profiling and deduplication measures significantly improved dataset quality, leading to better decision-making and more reliable insights.

3. **Enhanced Data Governance**:
   - SAP Information Steward helped establish better data governance practices, ensuring data accuracy, consistency, and compliance across the organization.
