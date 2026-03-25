TL;DR: I created an end-to-end data pipeline using Python and pandas to clean, transform, and model Netflix content data for analytics and dashboarding.

# 🎬 Netflix Data Engineering Pipeline

## 📌 Overview

This project demonstrates an **end-to-end data engineering pipeline** built using Python and pandas to transform raw Netflix content data into **clean, structured, and analytics-ready datasets**.

The goal of this project is to simulate a real-world data engineering workflow — from raw data ingestion to transformation, validation, and delivery for downstream analytics and dashboards.

---

## 🏗️ Architecture

```
Raw CSV → Pandas ETL Pipeline → Cleaned Tables → SQL / BI Ready Outputs
```

---

## 🎯 Project Objectives

- Clean and standardize messy, real-world data
- Handle missing and inconsistent values
- Normalize multi-value columns into relational structures
- Create reusable datasets for analytics and dashboards
- Apply data quality checks and validation

---

## 📂 Project Structure

```
netflix-data-engineering-pipeline/
│
├── data/
│   ├── raw/                # Raw dataset (not modified)
│   └── processed/          # Cleaned & transformed outputs
│
├── scripts/
│   └── netflix_pipeline.py # Main ETL pipeline
│
├── notebooks/              # Optional EDA
├── sql/                    # Analytics queries
├── README.md
├── requirements.txt
├── .gitignore
└── LICENSE
```

---

## 🔄 Pipeline Steps

### 1. Data Ingestion
- Load raw Netflix dataset from CSV
- Preserve raw data integrity (no direct modifications)

### 2. Data Cleaning
- Standardize column names
- Trim whitespace and normalize text fields
- Handle missing values
- Remove duplicates

### 3. Feature Engineering
- Extract year and month from `date_added`
- Parse `duration` into numeric value + unit
- Create data quality flags (missing director, cast, country)

### 4. Data Modeling
- Normalize multi-value columns into bridge tables:
  - Genres
  - Countries
  - Cast

### 5. Data Quality Reporting
- Generate column-level missing value report
- Track data completeness and schema consistency

### 6. Data Export
- Output clean datasets for downstream use

---

## 📊 Output Datasets

| File | Description |
|------|------------|
| `netflix_cleaned.csv` | Main cleaned dataset |
| `dim_genre_bridge.csv` | Genre mapping table |
| `dim_country_bridge.csv` | Country mapping table |
| `dim_cast_bridge.csv` | Cast mapping table |
| `data_quality_report.csv` | Data quality metrics |
| `content_by_type_summary.csv` | Movies vs TV Shows summary |
| `yearly_additions_summary.csv` | Titles added over time |
| `top_genres_summary.csv` | Most common genres |

---

## 💡 Example Business Questions

This pipeline enables analysis such as:

- How has Netflix content grown over time?
- What are the most popular genres?
- Which countries produce the most content?
- What is the distribution of Movies vs TV Shows?
- What trends exist in content additions by year?

---

## 🚀 How to Run

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Run the pipeline

```bash
python scripts/netflix_pipeline.py \
  --input data/raw/netflix_titles.csv \
  --output data/processed
```

---

## 🧠 Key Engineering Concepts Demonstrated

- ETL pipeline design (Extract, Transform, Load)
- Data cleaning and standardization
- Handling semi-structured data
- Data normalization (bridge tables)
- Data quality validation
- Analytics-ready data modeling

---

## 📈 Future Improvements

- Load transformed data into PostgreSQL
- Add Airflow for pipeline orchestration
- Containerize with Docker
- Implement automated data validation tests
- Integrate with cloud storage (AWS S3 / Azure Blob)

---

## 📚 Dataset Source

Netflix dataset sourced from public datasets (e.g., Kaggle).

---

## 👤 Author

Your Name

---

## ⭐ Why This Project Matters

This project demonstrates the ability to:

- Build structured, production-style data pipelines
- Transform raw data into business-ready insights
- Apply best practices used in real-world data engineering roles

---

## 📬 Feedback

If you have suggestions or improvements, feel free to open an issue or contribute.
