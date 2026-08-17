# Project Plan: Neutron Star Observational Database

## Phase 1 Execution Roadmap

### Stage 1: Data Source Selection & Raw Ingestion
- Document exact source catalogue versions (e.g., ATNF Pulsar Catalogue v2.7.0).
- Preserve raw data files untouched in `data/raw/`.
- Establish automated ingestion scripts with clear provenance tracking.

### Stage 2: Exploratory Data Analysis & Understanding
- Inspect raw column definitions, measurement units, and missing value patterns.
- Perform initial statistical profiling (distributions, ranges, log scales).
- Generate initial sky map visualizations using Astropy.

### Stage 3: Data Cleaning, Standardization & Validation
- Standardize physical units (e.g., periods in seconds, coordinates in degrees/radians, masses in $M_\odot$).
- Detect and flag duplicates, inconsistencies, or invalid physical values.
- Save intermediate clean datasets in `data/processed/`.

### Stage 4: Relational Database Design & Schema Construction
- Design normalized ER diagram (Neutron Star core entity, Measurements, Sources, References).
- Implement DDL scripts for PostgreSQL in `database/schema/`.
- Apply primary key, foreign key, and check constraints.

### Stage 5: Database Population & SQL Query Suite
- Populate PostgreSQL database via reproducible seeding scripts (`database/seeds/`).
- Develop analytical SQL queries (`database/queries/`) to filter dynamic parameter combinations (e.g., $M + T$, $M + B$, $P + \dot{P}$).

### Stage 6: Derived Physical Parameters & Statistical Reporting
- Compute derived parameters (e.g., characteristic age, spin-down luminosity, dipoles) into `data/derived/`.
- Document physical assumptions and formulas used.
- Finalize Phase 1 documentation and dataset exports for Phase 2 consumption.
