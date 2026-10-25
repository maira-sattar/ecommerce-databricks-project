# E-Commerce Data Engineering Pipeline | Databricks & Medallion Architecture

An end-to-end data engineering project that processes e-commerce data using **Databricks, PySpark, Apache Spark, Delta Lake, and SQL**. This project implements the Medallion Architecture (Bronze, Silver, and Gold) to ingest, transform, clean, and organize raw data into structured, analytics-ready datasets within Databricks.


## Architecture

The pipeline follows a layered approach to transform raw e-commerce data into structured datasets.

```text
         E-Commerce Source Data
                   |
                   ▼
         Data Ingestion
                   |
                   ▼
         ┌──────────────────┐
         │  Bronze Layer    │
         │    Raw Data      │
         └────────┬─────────┘
                  ▼
         ┌──────────────────┐
         │  Silver Layer    │
         │ Cleaned &         │
         │ Transformed Data │
         └────────┬─────────┘
                  ▼
         ┌──────────────────┐
         │   Gold Layer     │
         │ Fact & Dimension │
         │ Tables           │
         └────────┬─────────┘
                  ▼
         Analytical Queries
         in Databricks SQL
```

## Tech Stack

| Category | Technologies |
|---|---|
| Programming Languages | Python, SQL |
| Big Data Processing | Apache Spark, PySpark |
| Data Lakehouse | Databricks, Delta Lake |
| Data Architecture | Medallion Architecture |
| Data Modeling | Fact Tables, Dimension Tables, Star Schema |
| Development Environment | Databricks Notebooks |

## Project Structure

```text
ecommerce-databricks-project/
│
├── setup/                      # Environment and catalog configuration
│
├── medallion_processing_dim/   # Dimension table processing notebooks
│
├── medallion_processing_fact/  # Fact table processing notebooks
│
├── .gitignore                  # Git ignore rules
└── README.md                   # Project documentation
```

## Pipeline Workflow

### 1. Databricks Environment Setup

- Set up or access a Databricks workspace.
- Configure the required compute resources.
- Organize the project notebooks within the workspace.
- Prepare the catalog, schemas, and storage locations required by the pipeline.

### 2. Data Ingestion — Bronze Layer

- Ingest the source e-commerce datasets into Databricks.
- Read the raw data using PySpark.
- Store the ingested datasets as Delta tables in the Bronze layer.
- Maintain the raw data as the starting point for downstream transformations.

### 3. Data Cleaning — Silver Layer

- Handle missing values and duplicate records where appropriate.
- Standardize data types and formats.
- Apply data cleaning and transformation logic.
- Store the cleaned and validated datasets in the Silver layer.

### 4. Data Modeling — Gold Layer

- Process fact and dimension tables using dedicated notebooks.
- Apply the required business transformations.
- Organize data into a star-schema-style structure where implemented.
- Prepare the final Delta tables for analytical queries.

### 5. Querying and Validation

- Query the processed Gold-layer tables using SQL in Databricks.
- Validate the output of data transformations.
- Inspect the resulting fact and dimension tables to verify that the pipeline produces the expected datasets.

## 🚀 Getting Started

### Prerequisites

- Access to a Databricks workspace.
- Git and a GitHub account.
- Access to the source e-commerce datasets.
- Appropriate permissions for compute, storage, and catalog operations.

### Step 1: Clone the Repository

```bash
git clone https://github.com/maira-sattar/ecommerce-databricks-project.git

cd ecommerce-databricks-project
```

### Step 2: Set Up the Databricks Workspace

1. Sign in to your Databricks workspace.
2. Configure the required compute resources.
3. Import the project notebooks using Git folders, notebook import, or file upload.
4. Ensure that the workspace can access the source data and required storage locations.

### Step 3: Ingest the Source Data

1. Upload the source datasets to an accessible storage location.
2. Verify that the data files are accessible from Databricks.
3. Run the relevant ingestion notebooks or PySpark commands.
4. Store the raw data in the Bronze layer using Delta tables.

*Adjust the source paths and ingestion steps according to the dataset and configuration used in this project.*

### Step 4: Configure the Catalog and Schemas

1. Open the notebooks in the `setup/` directory.
2. Run the catalog and schema configuration notebooks, if applicable.
3. Configure the required database objects and storage locations.
4. Verify that the catalog, schemas, and tables are accessible.

If Unity Catalog is used, ensure that the necessary permissions are available. The configuration may differ depending on the workspace environment.

### Step 5: Execute the Medallion Pipeline

Run the notebooks in the appropriate dependency order:

1. **Bronze Layer:** Ingest the raw source data.
2. **Silver Layer:** Clean and transform the ingested datasets.
3. **Gold Layer:** Build the final fact and dimension tables.

Use the notebooks in `medallion_processing_dim/` and `medallion_processing_fact/` to process the corresponding tables.

### Step 6: Validate the Results

1. Open a Databricks SQL notebook.
2. Query the resulting Gold-layer tables.
3. Verify record counts, column types, and transformation results.
4. Confirm that the fact and dimension tables contain the expected data.

## 📚 Learning Resources and Acknowledgements

This project was completed as a hands-on learning project with guidance from the **Codebasics YouTube channel**.

- **Learning resource:** [Codebasics on YouTube](https://www.youtube.com/@codebasics)
- The tutorial served as a learning reference for understanding the project workflow and implementing the data engineering concepts in Databricks.

*Please refer to the original tutorial for its specific instructions and learning materials.*

## ⭐ Support

If you find this project useful, consider giving the repository a star. Feedback and suggestions are welcome!
