##Real-Time Azure Data Engineering Pipeline for Netflix Datasets
Welcome to the Azure Data Engineering Pipeline project for streaming and transforming real-time Netflix datasets! 🚀 This solution leverages a modern medallion architecture across Azure services to ingest, validate, transform, and serve analytics-ready data for dashboarding and insights.

##🔧 Tech Stack & Services Used
Azure Data Factory (ADF) – Orchestrates data ingestion & validation

GitHub – Source of Netflix datasets

Azure Data Lake Storage Gen2 – Storage across raw, bronze, and silver layers

Azure Databricks (w/ Unity Catalog) – Streaming ETL, transformations & Delta Live Tables

Delta Lake + Delta Pipelines – Reliable, versioned storage for the silver layer

Power BI – Data visualization & dashboarding

##🧠 Architecture Overview (Medallion Style)
Raw Layer (📥 ADF ➡️ ADLS Gen2):

Data is ingested weekly from GitHub using ADF pipelines.

Master data validation ensures only quality data flows into the next stage.

Validated files are stored in the raw container.

###Bronze Layer (📦 Storage):

ADF pushes the cleansed files into the bronze container.

This stage acts as the staging area for further processing.

###Silver Layer (⚙️ Databricks Magic):

Databricks (Unity Catalog-enabled) reads the streaming data from the bronze layer.

Transformations are applied using read & write streaming jobs.

Jobs are triggered every Sunday using Databricks Workflows.

Transformed, ready-to-consume data is written to Delta Live Tables.

##Power BI Integration (📈):

Delta tables from the silver layer feed into Power BI dashboards.

This enables real-time, actionable insights on Netflix data.

##📌 Highlights
Fully automated ETL flow with minimal manual intervention 💡

Real-time streaming logic using Databricks and Delta Live Tables ⚡

Weekly refresh with scalable workflows and clean separation of concerns 🎯

Follows the Medallion Architecture pattern for modular, layered data management 🧱

