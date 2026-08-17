# Neutron Star Observational Database

## 1. Project Overview
This repository contains a dedicated data engineering and data science project focused on building a structured, reproducible, and queryable relational database of observed **Neutron Star** properties from public astronomical catalogs.

The primary goal of this repository is to demonstrate practical mastery of data engineering, data cleaning, relational data modeling, SQL/PostgreSQL database construction, exploratory data analysis, and statistical visualization using Python.

```
Public Astronomical Catalogs (e.g., ATNF)
                 │
                 ▼
       ┌───────────────────┐
       │   Raw Data Ingest │
       └─────────┬─────────┘
                 │
                 ▼
       ┌───────────────────┐
       │ Data Validation & │
       │    Cleaning       │
       └─────────┬─────────┘
                 │
                 ▼
       ┌───────────────────┐
       │ Relational Model  │
       │   & PostgreSQL    │
       └─────────┬─────────┘
                 │
                 ▼
       ┌───────────────────┐
       │ Analytical SQL &  │
       │ Scientific Outputs│
       └───────────────────┘
```

## 2. Motivation & Technical Context
- **Professional Objectives**: Build an end-to-end data pipeline demonstrating core Data Analyst / Data Engineer competencies: SQL, PostgreSQL, Python (Pandas, NumPy, Astropy, SciPy), normalization, data provenance tracking, and data cleaning.
- **Scientific Context**: While initial datasets draw heavily from pulsar catalogs (such as the ATNF Pulsar Catalogue), the database architecture is designed for neutron stars broadly—including pulsars, millisecond pulsars, magnetars, isolated neutron stars, and binary neutron star systems.
- **Data Provenance & Rigor**: Raw data is never modified. Direct observational measurements are strictly separated from physical derived parameters (e.g., characteristic age, magnetic field estimates).

## 3. Key Target Observational Properties
- **Identification & Coordinates**: Name, RA/DEC, Galactic Coordinates ($l, b$), Distance.
- **Rotational Parameters**: Period ($P$), Period derivative ($\dot{P}$), Frequency ($f$).
- **Physical Quantities**: Mass ($M$), Radius ($R$), Thermal Temperature ($T$), Magnetic Field ($B$), Luminosity ($L$).
- **Environmental & Companion Data**: Binary companion type, orbital period, eccentricity.
- **Metadata**: Uncertainties, measurement references, and data sources.

## 4. Technologies Used
- **Language**: Python 3.10+
- **Data Engineering & Analysis**: Pandas, NumPy, Astropy, SciPy
- **Database**: PostgreSQL, SQL, SQLAlchemy, Alembic / psycopg2
- **Visualization**: Matplotlib, Seaborn
- **Testing & Quality**: pytest, flake8, black

## 5. Repository Structure
```
neutron-star-observational-database/
├── README.md
├── PROJECT_PLAN.md
├── LEARNING_OBJECTIVES.md
├── DATA_DICTIONARY.md
├── DATABASE_DESIGN.md
├── DATA_PIPELINE.md
├── SCIENTIFIC_METHODOLOGY.md
├── STATISTICAL_ANALYSIS.md
├── LIMITATIONS.md
├── DECISIONS.md
├── CHANGELOG.md
├── data/
│   ├── raw/
│   ├── interim/
│   ├── processed/
│   └── derived/
├── database/
│   ├── schema/
│   ├── migrations/
│   ├── seeds/
│   └── queries/
├── notebooks/
├── src/
│   ├── ingestion/
│   ├── cleaning/
│   ├── transformation/
│   ├── validation/
│   ├── database/
│   └── analysis/
├── tests/
├── figures/
└── docs/
```

## 6. Reproducibility & Setup
Detailed instructions for setting up the Python virtual environment and local PostgreSQL database instance will be documented progressively as ingestion scripts are finalized.

## 7. Project Limitations
- **Selection Biases**: Observed populations do not equal intrinsic physical populations due to observational flux/distance cutoffs.
- **Missing Data**: Not all neutron stars have measured masses, radii, or thermal emissions. Missing parameters are handled explicitly without artificial imputation in the core database.
