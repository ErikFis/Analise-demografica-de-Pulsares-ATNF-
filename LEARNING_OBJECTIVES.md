# Learning Objectives: Data Engineering & Analysis

Every milestone in this project is designed to develop practical data science and data engineering capabilities.

---

### Module 1: Raw Data Ingestion & Provenance
- **TASK**: Download and parse raw astronomical catalog data.
- **LEARN**: File I/O in Python, parsing structured/unstructured text, metadata retention, data provenance tracking.
- **DELIVERABLE**: Python ingestion module in `src/ingestion/` saving output to `data/raw/`.
- **VALIDATION**: Check raw checksums and line counts against source records.

---

### Module 2: Exploratory Data Analysis & Astropy Coordinates
- **TASK**: Explore distributions and build an all-sky celestial map.
- **LEARN**: Pandas profiling, NumPy log transformations, Astropy `SkyCoord`, Mollweide projection plotting.
- **DELIVERABLE**: `notebooks/01_data_exploration/` and `notebooks/02_sky_map/`.
- **VALIDATION**: Sky map matches known Galactic plane concentration of observed objects.

---

### Module 3: Data Cleaning & Validation
- **TASK**: Handle missing values, duplicate records, and unit conversions.
- **LEARN**: Data validation rules, explicit missing value conventions (NaN/NULL handling), unit standardization.
- **DELIVERABLE**: `src/cleaning/` and `src/validation/` scripts.
- **VALIDATION**: Automated pytest suite in `tests/` verifying data types and ranges.

---

### Module 4: Relational Database Modeling & SQL
- **TASK**: Design and build a normalized PostgreSQL database.
- **LEARN**: Database normalization (1NF, 2NF, 3NF), ER diagramming, DDL, Primary Keys, Foreign Keys, SQL JOINs, CTEs.
- **DELIVERABLE**: PostgreSQL DDL schema in `database/schema/` and seed scripts in `database/seeds/`.
- **VALIDATION**: SQL constraints prevent duplicate primary keys or invalid foreign key relationships.

---

### Module 5: Analytical SQL Queries & Export Interface
- **TASK**: Write SQL queries filtering arbitrary parameter combinations.
- **LEARN**: Advanced SQL aggregations, window functions, exporting structured interfaces for downstream applications.
- **DELIVERABLE**: Query library in `database/queries/`.
- **VALIDATION**: Query execution returns consistent data subsets for any combination of parameters.
