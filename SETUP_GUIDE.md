
# 🛠️ ETL Project Setup Guide: Snowflake & IICS

This guide provides step-by-step instructions to replicate the ETL automation project using Snowflake and Informatica Intelligent Cloud Services (IICS).

---

## ❄️ Snowflake Setup

### 1. Create Database
### 2. Create Schemas
### 3. Create Source Tables
### 4. Load Data into Source Table

## ⚙️ IICS Workflow Setup

### 1. Create New Mapping
- Open IICS and create a new mapping.

### 2. Add Source
- Configure source object to connect to Snowflake `CUSTOMER_DATA` table.

### 3. Add Expression Transformation
Apply the following transformations:
- Trim leading/trailing spaces from all fields.
- Convert email to lowercase.
- Format names: capitalize first letter, lowercase the rest.
- Remove non-digit characters from phone.
- Check for country code presence.

### 4. Add Router Transformation
Split data into valid and invalid paths:
- Null check on all fields → invalid to ERROR table.
- Email format validation using regex.
- Phone number length check.
- Validate DOB and calculate age.

### 5. Add Lookup Transformation
- Enrich valid data using lookup tables if available.

### 7. Remove Duplicates
- Use aggregator or expression logic to identify duplicates.
- Route duplicates to `TARGET 1`.

### 8. Configure Target Tables
- `TARGET 1`: Cleaned and validated data.
- `TARGET 2`: Invalid records.

### 9. Deploy and Run
- Validate the mapping.
- Deploy and run the workflow.
- Monitor results in Snowflake.

---

## ✅ Completion
You now have a fully functional ETL pipeline that automates customer data processing using Snowflake and IICS.
