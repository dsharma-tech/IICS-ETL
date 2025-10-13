# IICS-ETL
A mini-project demonstrating data ingestion, transformation, and loading using Snowflake and Informatica IICS.


# ❄️ Snowflake & IICS ETL Automation Project

## 📝 Project Overview
This project presents a fully automated ETL pipeline built using Snowflake and Informatica Intelligent Cloud Services (IICS). It is designed to process customer data efficiently by applying a series of data quality checks, transformations, and routing logic. The goal is to ensure that only clean and validated data is stored in the final target tables, while invalid or duplicate records are isolated for review.

## ❓ Problem Statement
Customer data collected from various sources often contains inconsistencies such as missing values, incorrect formats, and duplicate entries. These issues can lead to inaccurate reporting and poor decision-making. Manual data cleaning is time-consuming and prone to errors. This project solves these challenges by automating the entire ETL process, ensuring high data quality and integrity with minimal human intervention.

## 🌟 Features
### IICS Workflow
- **Source Integration from Snowflake**: Connects to Snowflake source tables to fetch raw customer data.
- **Expression Transformations**:
  - Trims leading and trailing spaces from all fields to standardize input.
  - Converts email addresses to lowercase for consistency.
  - Formats names by capitalizing the first letter and converting the rest to lowercase.
  - Removes non-digit characters from phone numbers.
  - Checks for the presence of country codes in phone numbers.
- **Router Logic for Valid/Invalid Data**:
  - Performs null checks on all fields; records with missing values are routed to an error table.
  - Validates email format using regular expressions.
  - Checks phone number length and structure.
  - Validates date of birth and calculates age.
- **Lookup Enrichment**: Enhances valid records by referencing additional data sources.
- **Sorting and Duplicate Handling**:
  - Sorts customer data for consistency.
  - Identifies and removes duplicate records, storing them in a separate table for review.
- **Target Tables**:
  - Cleaned and validated data is stored in `TARGET 2`.
  - Enhanced data with calculated fields like full name and age group is stored in `TARGET 3`.
  - Invalid data is stored in `TARGET 4`.

## 💼 Use Cases
- **Customer Data Cleansing**: Ensures accurate and standardized customer records.
- **CRM System Integration**: Automates data preparation for CRM platforms.
- **Business Intelligence & Analytics**: Provides clean data for reporting and analysis.
- **Duplicate Detection**: Identifies and isolates duplicate entries for further review.

## 🛠️ Technologies Used
- **Snowflake**: Cloud-based data warehouse for scalable storage and querying.
- **Informatica IICS**: ETL tool for designing and executing data workflows.
- **SQL**: Used for creating schemas, tables, and querying data.
- **CSV**: Format used for source and target data files.


