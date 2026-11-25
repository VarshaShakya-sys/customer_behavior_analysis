# Data Analytics Project

An end-to-end data analytics project covering data loading, exploratory data analysis, data cleaning, SQL analysis, dashboard development, reporting, and presentation design.

## Overview

This project demonstrates a complete analytics workflow using Python, SQL, Power BI, and Gamma. The goal is to transform raw data into actionable insights through structured analysis and clear business communication.

The project includes:

- Loading and inspecting a dataset with Python
- Performing exploratory data analysis (EDA)
- Cleaning and preparing data for analysis
- Running analytical SQL queries
- Building an interactive Power BI dashboard
- Creating a written analytical report
- Preparing a presentation using Gamma

## Dataset

The project uses a structured dataset containing business or operational records. The dataset may include fields such as:

- Dates and time periods
- Customer, product, or transaction details
- Geographic or category information
- Revenue, cost, quantity, or performance metrics
- Status and descriptive attributes

> **Note:** Replace this section with the actual dataset name, source, size, and business context before publishing the project.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Data loading, exploration, cleaning, and analysis |
| Pandas | Data manipulation and preparation |
| NumPy | Numerical operations |
| Matplotlib / Seaborn | Data visualization during EDA |
| PostgreSQL / MySQL / SQL Server | Relational database analysis and SQL querying |
| Power BI | Interactive dashboard development |
| Gamma | Presentation and visual storytelling |
| Microsoft Excel or CSV | Source data and intermediate files, where applicable |

## Project Steps

### 1. Load the Dataset in Python

The dataset is imported into Python using Pandas. Initial checks are performed to understand its structure, size, data types, and quality.

Typical checks include:

- Number of rows and columns
- Column names and data types
- Missing values
- Duplicate records
- Summary statistics
- Unique values in categorical columns

```python
import pandas as pd

# Load the dataset
df = pd.read_csv("data/dataset.csv")

# Inspect the data
print(df.head())
print(df.shape)
print(df.info())
print(df.describe(include="all"))
```

### 2. Perform Exploratory Data Analysis

EDA is used to identify patterns, trends, relationships, and potential data-quality issues.

The analysis may include:

- Distribution of numerical variables
- Category and frequency analysis
- Trend analysis over time
- Correlation analysis
- Outlier detection
- Comparison of key performance metrics

Example visualizations include:

- Histograms
- Bar charts
- Line charts
- Box plots
- Heatmaps
- Scatter plots

### 3. Clean and Prepare the Data

The data is cleaned and transformed to make it suitable for analysis and reporting.

Common cleaning activities include:

- Handling missing values
- Removing duplicate records
- Correcting data types
- Standardizing column names
- Formatting dates
- Treating outliers where appropriate
- Removing invalid or inconsistent records
- Creating calculated columns

```python
# Example cleaning steps
df.columns = df.columns.str.strip().str.lower().str.replace(" ", "_")
df = df.drop_duplicates()
df["date"] = pd.to_datetime(df["date"], errors="coerce")
df = df.dropna(subset=["date"])
```

### 4. Run SQL Queries

The cleaned data is loaded into a relational database such as PostgreSQL, MySQL, or SQL Server. SQL queries are then used to answer business questions and validate findings from Python.

Typical analysis includes:

- Total sales or revenue
- Monthly or yearly performance
- Top customers or products
- Category comparisons
- Regional performance
- Growth rates
- Average order or transaction value
- Ranking and trend analysis

Example SQL query:

```sql
SELECT
    category,
    SUM(revenue) AS total_revenue,
    COUNT(*) AS transaction_count,
    AVG(revenue) AS average_revenue
FROM sales
GROUP BY category
ORDER BY total_revenue DESC;
```

The same analytical logic can be adapted for PostgreSQL, MySQL, or SQL Server, with minor syntax adjustments where needed.

### 5. Build the Power BI Dashboard

The cleaned dataset and SQL results are connected to Power BI to create an interactive dashboard.

The dashboard may include:

- KPI cards for key metrics
- Time-based trend charts
- Category and product performance
- Geographic analysis
- Filters and slicers
- Drill-down views
- Comparative charts

The dashboard is designed to help users quickly understand performance, identify trends, and explore the data interactively.

### 6. Create the Analytical Report

A written report summarizes the methodology, analysis, findings, and recommendations.

The report includes:

1. Business objective
2. Dataset description
3. Data preparation process
4. EDA findings
5. SQL analysis results
6. Dashboard insights
7. Key conclusions
8. Business recommendations
9. Limitations and possible next steps

### 7. Create the Presentation in Gamma

A PowerPoint-style presentation is created using Gamma to communicate the project clearly to stakeholders, hiring managers, or business users.

The presentation highlights:

- The business problem
- The analytics approach
- Key findings
- Dashboard visuals
- Important trends and patterns
- Recommendations
- Final conclusions

Gamma is used to organize the story into a concise, visually engaging presentation.

## Dashboard

The Power BI dashboard provides an interactive view of the main business metrics and analytical findings.

Suggested dashboard pages include:

- **Executive Summary:** High-level KPIs and headline insights
- **Trend Analysis:** Performance over time
- **Category or Product Analysis:** Comparison across segments
- **Customer or Regional Analysis:** Detailed breakdowns by business dimension
- **Detailed View:** Filterable table for deeper investigation

> Add a screenshot or link to the published Power BI dashboard here.

## Results

The project converts raw data into practical insights through a repeatable analytics workflow.

Key outcomes include:

- A structured and cleaned analytical dataset
- Reproducible Python-based data preparation
- SQL queries for business-focused analysis
- An interactive Power BI dashboard
- A documented analytical report
- A professional Gamma presentation
- Clear findings and recommendations for decision-making

> Replace this section with the project’s actual results, such as the main trend discovered, strongest-performing category, key performance change, or business recommendation.

## How to Run

### Prerequisites

Install the following before running the project:

- Python 3.9 or later
- PostgreSQL, MySQL, or SQL Server
- Power BI Desktop
- A database client such as pgAdmin, MySQL Workbench, or SQL Server Management Studio

### 1. Clone the Repository

```bash
https://github.com/VarshaShakya-sys/customer_behavior_analysis.git
cd /customer_behavior_analysis
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

**Windows**

```bash
venv\Scripts\activate
```

**macOS / Linux**

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

Example `requirements.txt`:

```text
pandas
numpy
matplotlib
seaborn
sqlalchemy
psycopg2-binary
pymysql
pyodbc
jupyter
```

Install only the database driver required for your chosen database system.

### 4. Add the Dataset

Place the source file in the project data directory:

```text
data/dataset.csv
```

Update the file path in the Python notebook or script if your dataset has a different name or location.

### 5. Run the Python Analysis

```bash
jupyter notebook
```

Open the analysis notebook and run the cells in order to:

1. Load the dataset
2. Explore the data
3. Clean and transform the data
4. Export the cleaned dataset

### 6. Set Up the Database

Create a database and load the cleaned dataset into a table. Update the connection details in the SQL scripts or configuration file.

Example connection pattern:

```python
from sqlalchemy import create_engine

engine = create_engine("your_database_connection_string")
df.to_sql("analytics_data", engine, if_exists="replace", index=False)
```

Do not commit passwords, API keys, or other credentials to the repository. Use environment variables or a local `.env` file instead.

### 7. Run the SQL Queries

Open the SQL files in the `sql/` directory and run them in your selected database environment.

Save important query outputs in the `outputs/` directory for use in the report and dashboard.

### 8. Open the Power BI Dashboard

Open the Power BI file from the `powerbi/` directory and update the data source connection if required.
