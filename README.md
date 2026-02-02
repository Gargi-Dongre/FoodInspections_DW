# 🍽️ Chicago & Dallas Food Inspection Data Engineering & BI Project  

This repository contains an end-to-end **data engineering and business intelligence solution** that integrates, cleans, models, and analyzes food inspection data from the cities of **Chicago and Dallas**.  

The project transforms messy, heterogeneous public datasets into a unified, analytics-ready data platform and delivers interactive visual insights through Power BI dashboards.

---

## 📌 Project Overview  

Food inspection data from different cities often comes in varying formats, schemas, and quality levels, making cross-city analysis difficult. This project addresses that challenge by building a standardized data pipeline and dimensional model to enable meaningful comparisons and trend analysis across both cities.

### What this project achieves:
- Harmonizes two independent municipal datasets into a single analytical model  
- Implements scalable cloud-based ETL pipelines  
- Ensures data quality, consistency, and referential integrity  
- Supports data-driven insights into public health and regulatory compliance  

---

## 🎯 Objectives  

The primary goals of this project were to:

- **Integrate** food inspection datasets from Chicago and Dallas with different structures  
- **Profile, clean, and flatten** raw data to handle missing values, inconsistencies, and multi-valued fields  
- **Design a unified dimensional model** for efficient analytical querying  
- **Build automated ETL pipelines** for cloud-based data processing  
- **Create an interactive Power BI dashboard** for exploratory and business analysis  

---

## 🏗️ Architecture & Workflow  

### 🔹 Step 1 — Data Ingestion  
Raw datasets from Chicago and Dallas were ingested into Azure Data Lake via Azure Data Factory (ADF).

### 🔹 Step 2 — Data Profiling, Cleaning & Flattening  
Using **Alteryx and ADF**, the data was:
- Profiled for quality issues  
- Standardized across both cities  
- Cleaned for missing values and inconsistencies  
- **Flattened** to normalize multi-valued fields (especially inspection violations), converting one inspection record with multiple violations into multiple rows  

This ensured the data was truly tabular and analytics-ready.

### 🔹 Step 3 — Dimensional Modeling  
A star-schema data model was designed in **ER/Studio**, consisting of:

**Fact Table**
- `FCT_INSPECTION`

**Dimension Tables**
- `DIM_LOCATION`
- `DIM_DATE`
- `DIM_BUSINESS`
- `DIM_VIOLATION`
- `DIM_RISK`

**Bridge Table**
- Used to resolve many-to-many relationships between inspections and violations  

### 🔹 Step 4 — ETL & Cloud Data Warehouse  
Automated ETL pipelines in **Azure Data Factory**:
- Extracted data from Azure Data Lake  
- Transformed it to conform to the dimensional model  
- Loaded standardized data into **Azure Synapse Analytics**  

Key data engineering principles applied:
- Data consistency  
- Referential integrity  
- Source lineage tracking  
- Scalable cloud storage  

### 🔹 Step 5 — Visualization & Analytics  
An interactive **Power BI dashboard** was built to enable:

- Violation frequency analysis by city, ZIP, and risk level  
- Trend analysis of inspection outcomes over time  
- Interactive geospatial risk maps  
- Heatmaps by business category and location  

---

## 🛠️ Tools & Technologies  

| Layer | Technology |
|------|------------|
| Data Cleaning | Alteryx |
| Data Modeling | ER/Studio |
| ETL Orchestration | Azure Data Factory (ADF) |
| Data Storage | Azure Data Lake |
| Data Warehouse | Azure Synapse Analytics |
| Visualization | Power BI |
| Querying | SQL |

---

## 📊 Key Business Insights  

The dashboard helps answer questions such as:

- What are the most common food safety violations?  
- Which ZIP codes have the highest risk levels?  
- How does compliance vary by business type?  
- Are violations increasing or decreasing over time?  
- Which facilities require stricter monitoring?  

---

## 📁 Repository Structure  
├── ADF_Pipelines/          
├── Alteryx_Workflows/       
├── ER_Studio_Model/        
├── Snowflake_SQL/            
├── PowerBI_Dashboard/      
├── Data_Dictionary.xlsx     
└── README.md               
