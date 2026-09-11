# Data Warehouse & NoSQL Analytics Platform for Retail Supermarket Networks

A enterprise-grade **Data Engineering, Data Warehousing, NoSQL Modeling, Big Data Processing, Machine Learning, and Web Analytics Dashboard** architecture built for retail supermarket chains.

This platform bridges relational Data Warehousing (**Microsoft SQL Server / SSMS**), NoSQL document databases (**MongoDB**), distributed Big Data batch processing (**Apache Spark / PySpark**), predictive Machine Learning models (**Scikit-Learn**), and interactive real-time analytics web dashboards (**Streamlit**, **Plotly**, **ECharts**).

---

## 🏗️ System Architecture & Data Flow

```
                                  +---------------------------------------+
                                  |         Web Scraping & APIs           |
                                  +---------------------------------------+
                                                      |
                                                      v
  +-----------------------+              +--------------------------+              +-----------------------+
  | MongoDB Normalized    | -----------> | PySpark Big Data Engine  | -----------> | MongoDB Denormalized  |
  | (Relational Docs)     |              | (ETL & Aggregations)     |              | (Nested Aggregates)   |
  +-----------------------+              +--------------------------+              +-----------------------+
             |                                        |                                        |
             v                                        v                                        v
  +----------------------------------------------------------------------------------------------------+
  |                                SSMS / MSSQL Data Warehouse (DWH)                                   |
  |                        (Views, Stored Procedures, Comparative Queries, KPIs)                       |
  +----------------------------------------------------------------------------------------------------+
                                                      |
                                                      v
  +---------------------------------------+                        +-----------------------------------+
  | Machine Learning & Latency Analytics  | ---------------------> | Streamlit Interactive Dashboard   |
  | (Regression Models, Performance Tests)|                        | (Real-Time KPI & CRUD Portal)     |
  +---------------------------------------+                        +-----------------------------------+
```

---

## 🛠️ Core Technology Stack

- **Database Management Systems:**
  - **MongoDB**: Primary NoSQL Document Storage containing both Normalized and Denormalized document structures for high-performance read/write evaluation.
  - **Microsoft SQL Server (SSMS)**: Relational Data Warehouse (`DWH_Nr1_Comun`) for executing multi-dimensional queries, business intelligence aggregations, and KPI integrity checks.
- **Big Data Engine & Connectivity:**
  - **Apache Spark (PySpark)**: Distributed ingestion engine, schema harmonization, stream/batch processing, and synthetic retail transaction generator.
  - **PyODBC & SQLAlchemy**: High-throughput database connectors linking Python scripts to Microsoft SQL Server and MongoDB.
- **Data Mining & Scraping:**
  - **Requests & BeautifulSoup4**: Automated web scraping pipeline harvesting physical store locations and promotional catalogs.
- **Machine Learning & Predictive Modeling:**
  - **Scikit-Learn**: Linear Regression modeling (`R²`, `MAE`, `MSE`, `RMSE`) forecasting B2C customer lifetime spending and B2B corporate account contracts.
  - **Pandas & NumPy**: Advanced matrix transformations, data cleansing, and feature engineering.
- **Visualization & Web Interface:**
  - **Streamlit**: Web-based executive management portal (`app.py`).
  - **Plotly & Seaborn / Matplotlib / ECharts**: Dynamic heatmaps, multi-axis scatter plots, radar charts, and CRUD execution time comparisons.

---

## 📁 Repository Structure

```
.
├── INAINTE_DE_BIG_DATA_SI_SPARK/
│   ├── 1. COLECTII_MONGODB/          # JSON collection schemas (Normalized & Denormalized)
│   ├── 2. JSON_IMPORT/               # Pre-processed JSON datasets structured for batch import
│   └── 3. DWH_NR1_BAK/               # MSSQL Data Warehouse Database Backup (`DWH_NR1_Comun.bak`)
├── INTEROGARI_SSMS/                  # Analytical SQL Scripts & KPI Stored Procedures
│   ├── COMPARATIE_INTRE_MODELE.sql  # Cross-model query execution benchmarks
│   ├── TOP_CLIENTI_B2C.sql          # B2C revenue rankings & RFM segmentation analysis
│   ├── TOP_COMPANII_B2B.sql          # Corporate B2B wholesale transaction evaluation
│   └── VERIFICAREA_KPI-ULUI_INTEGRAT.sql # Cross-channel validation scripts
├── PYTHON_SCRIPTURI_PROIECTE/        # Core Data Engineering & ML Pipeline Modules
│   ├── 1. PYTHON_CONVERT_ÎN_DENORMALIZAT/ # JSON schema converter (Normalized to Embedded)
│   ├── 2. PYTHON_SSMS_CONECTOR_MONGODB/   # Automated MongoDB-to-DWH synchronizer
│   ├── 3. PYTHON_SPARK_BIG_DATA/          # PySpark ETL, web scraping, and data synthesis engine
│   ├── 4. PYTHON_CSV_EXPORT/              # Automated CSV metric exporter from DWH views
│   ├── 5. PYTHON_ML + GRAFICE/            # Machine Learning regression scripts & charts
│   ├── 6. PYTHON_REGRESIE_LINIARA_CSV_DWH_MONGODB_GRAFICE/ # Comparative ML evaluation
│   ├── 7. PYTHON_CRUD_LATENTA_NORMALIZAT+DENORMALIZAT/      # Latency & throughput benchmarking suite
│   └── 8. PYTHON_CRUD/                    # Terminal CLI for MongoDB database management
└── STREAMLIT/                         # Streamlit Interactive Web Application
    └── app.py                         # Production Web Interface
```

---

## ⚡ Core Subsystems & Components

### 1. Data Normalization & Denormalization Pipeline
- Transmutes flat relational tables into rich nested document hierarchies (embedding customer purchase histories, itemized invoices, and wholesale contracts directly into parent records).
- Reduces multi-table JOIN operations and improves retrieval speed for complex user profiles.

### 2. NoSQL & Relational Data Warehouse Integration
- Extracts raw transaction logs from MongoDB collections (`nr1_clienti` and `nr1_denormalizat`).
- Normalizes unstructured data into structured tabular representations and stages them into Microsoft SQL Server Data Warehouse tables.

### 3. Big Data Processing Engine (PySpark)
- Leverages **PySpark** to ingest, cleanse, and aggregate large-scale transaction logs.
- Features web scraping routines (`BeautifulSoup`) to pull online promos and store locations.
- Includes a scalable data synthesizer to test cluster performance under heavy data volume.

### 4. Predictive Machine Learning Suite
- **B2C Customer Spending Model**: Fits multiple linear regression models predicting customer lifetime value (LTV) using order frequency, average basket size, and promotional item ratio.
- **B2B Corporate Account Forecast**: Fits models predicting commercial wholesale contract values based on order volume and discount schedules.
- **Cross-Engine Performance Evaluation**: Benchmarks regression training speed and accuracy across flat CSV files, SSMS relational tables, and MongoDB denormalized collections.

### 5. Database Latency Benchmarking
- Measures read/write operational latencies (`Create`, `Read`, `Update`, `Delete`) comparing MongoDB normalized collections against embedded denormalized documents across varying batch sizes.

### 6. Interactive Executive Dashboard
- Unified **Streamlit** dashboard integrating real-time KPI metrics, live PySpark ETL execution triggers, interactive ML scenario calculators, Plotly visualization charts, and a built-in MongoDB Document CRUD manager.

---

## 🚀 Deployment & Setup Guide

### Prerequisites

- **Python**: Version `3.10` or higher
- **MongoDB Server**: Listening on `localhost:27017`
- **Microsoft SQL Server / SSMS**: SQL Server instance with `ODBC Driver 17 for SQL Server` installed
- **Database Backup**: `DWH_NR1_Comun.bak` (available under `INAINTE_DE_BIG_DATA_SI_SPARK/3. DWH_NR1_BAK/`)

### 1. Environment Setup

```bash
# Clone repository
git clone <repository_url>
cd <repository_directory>

# Create and activate virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install required dependencies
pip install pymongo pyodbc pyspark requests bs4 pandas numpy scikit-learn matplotlib seaborn sqlalchemy streamlit plotly streamlit-echarts prettytable
```

### 2. Database Restoration (MSSQL)

1. Open Microsoft SQL Server Management Studio (SSMS).
2. Restore `DWH_NR1_Comun.bak` as a new database named `DWH_Nr1_Comun`.
3. Verify connection string parameters in `PYTHON_SCRIPTURI_PROIECTE/2. PYTHON_SSMS_CONECTOR_MONGODB/main.py`.

---

## 📊 Running System Modules

### Execute Big Data ETL Pipeline
```bash
python PYTHON_SCRIPTURI_PROIECTE/3.\ PYTHON_SPARK_BIG_DATA/nr1_bigdata_spark.py
```

### Train Machine Learning Models
```bash
python PYTHON_SCRIPTURI_PROIECTE/5.\ PYTHON_ML\ +\ GRAFICE/Y1_KPI_CLIENTI_B2C.py
python PYTHON_SCRIPTURI_PROIECTE/5.\ PYTHON_ML\ +\ GRAFICE/Y2_KPI_COMPANII_B2B.py
```

### Run Latency Benchmarks
```bash
python PYTHON_SCRIPTURI_PROIECTE/7.\ PYTHON_CRUD_LATENTA_NORMALIZAT+DENORMALIZAT/main.py
```

### Launch Interactive Web Application
```bash
cd STREAMLIT
streamlit run app.py
```

---

## 📈 Summary of Technical Insights

1. **Denormalization Performance**: Embedded document schemas in MongoDB reduce read query latency up to 4-5x for full transactional history fetches by removing expensive `$lookup` aggregation stages.
2. **Predictive Accuracy**: B2C revenue prediction models yield high coefficient of determination scores ($R^2 > 0.85$), highlighting order frequency and promotion adoption as primary drivers of customer LTV.
3. **Data Quality & Auditability**: Dual-layer architecture allows cross-validation of NoSQL document aggregations directly against SSMS relational Data Warehouse views.
