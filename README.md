# Awesome-Self-Service-Data-Preparation-Cleaning

# Awesome Self-Service Data Preparation & Cleaning

> A curated list of top Self-Service Data Preparation and Cleaning platforms — both SaaS/Hosted commercial solutions and open-source alternatives for profiling, transforming, and standardizing messy data without writing code.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Alteryx Designer Cloud](#alteryx-designer-cloud)
  - [Tableau Prep](#tableau-prep)
  - [AWS Glue DataBrew](#aws-glue-databrew)
  - [Zoho DataPrep](#zoho-dataprep)
  - [Datameer](#datameer)
- [Open-Source Software](#-open-source-software)
  - [OpenRefine](#openrefine)
  - [Flowfile](#flowfile)
  - [Ciaren](#ciaren)
  - [DATADOC](#datadoc)
  - [datapill](#datapill)
  - [Open Data Editor](#open-data-editor)
  - [Hermes](#hermes)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Self-Service Data Preparation and Cleaning platforms. These are not open-source but are included as reference points for feature comparison.

### Alteryx Designer Cloud
**Type:** Visual data preparation and analytics automation  
Alteryx Designer Cloud (formerly Trifacta) provides a visual, self-service interface for profiling, cleaning, and transforming data at scale. It is a long-standing enterprise standard for data preparation, with a focus on interactive exploration and automated pattern detection. Pricing is quote-based and targets enterprise analytics teams.

### Tableau Prep
**Type:** Visual data preparation within Tableau ecosystem  
Tableau Prep provides a visual flow-based interface for cleaning, shaping, and combining data before analysis in Tableau. It is the natural choice for organizations already standardized on Tableau, with direct integration into Tableau Desktop and Server.

### AWS Glue DataBrew
**Type:** Managed visual data preparation on AWS  
AWS Glue DataBrew provides a visual interface for cleaning and normalizing data without writing code, with 250+ pre-built transformations. It integrates natively with AWS data services (S3, Redshift, Athena) and is billed per session and data volume.

### Zoho DataPrep
**Type:** Self-service data preparation within Zoho ecosystem  
Zoho DataPrep provides a visual interface for profiling, cleaning, and transforming data as part of the broader Zoho analytics suite. It is the natural choice for organizations already using Zoho Analytics or other Zoho products.

### Datameer
**Type:** Cloud-native data preparation for Snowflake  
Datameer provides a SaaS data preparation platform designed specifically for Snowflake, with a spreadsheet-like interface, formula builder, and data catalog integration. It targets business users and analysts needing self-service transformation within the Snowflake ecosystem.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Self-Service Data Preparation and Cleaning tools. The open-source ecosystem spans **visual pipeline builders**, **CLI-driven automation**, and **privacy-first local editors**.

### OpenRefine
**Stack:** Java | **License:** BSD-3-Clause  
OpenRefine is the most established open-source tool for working with messy data, with 12,000+ GitHub stars and active development (last commit within days as of early 2026) [citation:14]. It runs in a web browser on the user's own machine, providing privacy and comfort while loading, understanding, cleaning, reconciling, and augmenting data with web services and external data [citation:14]. A 2025 benchmark study evaluating five data cleaning tools identified OpenRefine as a primary GUI-based desktop application alongside Dedupe and Great Expectations, noting its strengths in interactive clustering and transformation [citation:2]. It is particularly strong for **value normalization** and fuzzy duplicate detection through clustering [citation:7][citation:12].  
**Best for:** Analysts and data practitioners wanting a proven, browser-based tool for interactive data cleaning and reconciliation without writing code or sending data to a third-party cloud.

### Flowfile
**Stack:** Python / Polars / Delta Lake | **License:** Open Source (per project)  
Flowfile is an open-source data platform combining a **visual pipeline builder** with a data catalog, scheduling, Kafka ingestion, and sandboxed Python execution in a single `pip install` [citation:3][citation:5]. The visual builder offers 30+ nodes for joins, filters, aggregations, fuzzy matching, and pivots, with **code generation** that exports visual flows as standalone Python/Polars scripts — so visual work never traps logic in a proprietary format [citation:3]. It includes a data catalog with Delta Lake storage, version history, and lineage tracking, plus cloud storage connectivity (S3, Azure Data Lake, GCS) and database connectors (PostgreSQL, MySQL, SQL Server, DuckDB) [citation:3][citation:5]. Deploys via desktop app, Docker Compose, or browser-based WASM demo [citation:3].  
**Best for:** Teams wanting a self-hosted visual ETL and data prep tool with Polars performance, code export, and data catalog capabilities, without vendor lock-in.

### Ciaren
**Stack:** Python / Polars / Pandas | **License:** Open Source (per repository)  
Ciaren is an open-source, local-first **visual ETL and data pipeline builder** with drag-and-drop data prep, preview of every step, scheduling, and **export to clean pandas or Polars Python code** [citation:10]. It covers cleaning (drop/fill nulls, remove duplicates, rename/select/drop columns, cast types), transformation (filters, joins, group by, aggregates, calculated columns, pivots, windows), data quality assertions, and lightweight machine learning with MLflow tracking [citation:10]. Every flow exports to a standalone Python script or Jupyter notebook, making it useful for prototyping, teaching, and migrating visual exploration into normal Python projects [citation:10]. It is positioned as a lightweight, single-machine option for small and medium datasets, not a replacement for Airflow or Spark at scale [citation:10].  
**Best for:** Data analysts and Python learners wanting a visual builder whose output is plain pandas/Polars code, with no proprietary workflow format.

### DATADOC
**Stack:** Python / Polars | **License:** Open Source (per PyPI)  
DATADOC is a CLI and Python library for **automated dataset engineering and cleaning**, powered by a Polars backend [citation:4]. It analyzes raw CSV files, diagnoses missing values, outliers, and schema issues, and engineers a machine-learning-ready dataset in milliseconds. Every transformation is strictly mathematical (IQR, medians, mode) and deterministic — no black-box AI — making it safe for production [citation:4]. It exports a standalone, portable Python script to replicate the pipeline anywhere, and includes an **AI Planner and interactive Chat Assistant** for LLM-assisted engineering via tool-calling [citation:4]. CLI commands include `analyze`, `recommend`, `engineer`, `compare`, and `pipeline` [citation:4].  
**Best for:** ML engineers and data scientists wanting automated, deterministic data cleaning with reproducible Python script export and optional AI assistance.

### datapill
**Stack:** Python | **License:** Open Source (per PyPI)  
datapill is a CLI-driven data preparation tool that runs **ingest + profile + transform pipelines** from JSON config files [citation:6]. It provides pre-built steps for missing values (impute mean/median/mode, drop), outliers (clip IQR/Z-score), scaling (standard, minmax, robust), encoding (onehot, ordinal), and structure (select, drop, rename, cast, deduplicate) [citation:6]. Every pipeline run produces artifacts (Parquet files and JSON metadata) stored locally with a registry, and exports to file, PostgreSQL, or S3 with write modes (replace, append, upsert) [citation:6]. Connectors cover PostgreSQL, MySQL, S3, Kafka, and REST APIs with pagination modes [citation:6].  
**Best for:** Data engineers wanting a config-driven, CLI-based approach to repeatable data preparation with artifact tracking and database/S3 write-back.

### Open Data Editor
**Stack:** JavaScript / Frictionless Framework | **License:** Open Source (Open Knowledge Foundation)  
Open Data Editor (ODE) is an open-source, **offline-capable tool designed for non-technical data producers** to validate, correct, and prepare structured datasets before publication [citation:8][citation:11]. It focuses on data quality and FAIR data practices, with local AI features that explain each step rather than acting as a black box, keeping sensitive data on the user's device [citation:8][citation:11]. It is built on the Frictionless Framework, ensuring open standards, and is specifically designed for low-resource and offline contexts where technical capacity and connectivity are constrained [citation:8].  
**Best for:** Government agencies, NGOs, and non-technical users in low-resource or offline environments needing privacy-preserving data validation and cleaning.

### Hermes
**Stack:** Python / Polars / DuckDB | **License:** Open Source (Core)  
Hermes is an open-source **data pipeline layer** that sits around existing tools (Pandas, Polars, PyArrow, DuckDB) rather than replacing them [citation:1]. It provides validation, profiling, entity resolution (connecting records that refer to the same real-world entity), dataset versioning with snapshot/diff, provenance tracking, and lineage recording [citation:1]. It is explicitly **local-first** — `pip install hermes-plt` and start working immediately, with no cloud account or proprietary storage required [citation:1]. Domain packages (Finance, Defense, Healthcare, Trade) provide specialized knowledge on top of the core engine [citation:1].  
**Best for:** Developers building reproducible data pipelines who need provenance, lineage, and entity resolution without adopting a proprietary platform.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Visual Builder | Code Export | Self-Hosted | Best For |
|----------|---------|-------|----------------|-------------|-------------|----------|
| **Alteryx Designer Cloud** | Proprietary | Cloud | ✅ | (Limited) | ❌ | Enterprise visual prep |
| **Tableau Prep** | Proprietary | Cloud/Desktop | ✅ | ❌ | (Desktop) | Tableau ecosystem |
| **AWS Glue DataBrew** | Proprietary | Cloud | ✅ | ❌ | ❌ | AWS-native prep |
| **OpenRefine** | BSD-3-Clause | Java | ✅ (Browser) | (Operations) | ✅ (Local) | Interactive cleaning + reconciliation |
| **Flowfile** | Open Source | Python/Polars | ✅ | ✅ Polars | ✅ | Visual ETL + catalog + lineage |
| **Ciaren** | Open Source | Python/Polars | ✅ | ✅ Pandas/Polars | ✅ | Visual prep → plain Python |
| **DATADOC** | Open Source | Python/Polars | ❌ (CLI) | ✅ Python script | ✅ | Automated deterministic cleaning |
| **datapill** | Open Source | Python | ❌ (CLI) | ❌ | ✅ | Config-driven pipelines |
| **Open Data Editor** | Open Source | JS/Frictionless | ✅ (GUI) | ❌ | ✅ (Offline) | Non-technical FAIR data |
| **Hermes** | Open Source | Python/Polars | ❌ (Library) | ❌ | ✅ | Provenance + lineage + entity resolution |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Self-Service Data Preparation or Cleaning tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem **splits** between **visual pipeline builders** (Flowfile, Ciaren), **CLI automation** (DATADOC, datapill), **interactive desktop tools** (OpenRefine), and **privacy-first editors** (Open Data Editor). **OpenRefine** is the most established option for interactive cleaning and reconciliation, with a long track record and active development [citation:14]. **Flowfile** and **Ciaren** are notable for combining visual builders with code export, avoiding proprietary workflow lock-in [citation:3][citation:10]. For automated, deterministic cleaning with script export, **DATADOC** offers a focused Polars-based solution [citation:4].

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
