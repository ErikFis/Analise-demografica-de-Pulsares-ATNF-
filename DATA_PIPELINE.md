# Data Pipeline Architecture

## Workflow Diagram

```
Raw Catalogue Data (CSV / ASCII / FITS)
                 │
                 ▼ (src/ingestion/)
          `data/raw/`
                 │
                 ▼ (src/cleaning/ & src/validation/)
        `data/interim/`
                 │
                 ▼ (src/transformation/)
        `data/processed/`
                 │
                 ├──────────────────────┐
                 ▼ (src/database/)      ▼ (src/analysis/)
        PostgreSQL Database      `data/derived/`
                 │
                 ▼
       Downstream ML Interface (Repo 2)
```

## Stage Descriptions
- **Ingestion**: Reads raw source files and logs download date, version, and file hash.
- **Interim Cleaning**: Normalizes headers, parses string values, converts units to standard SI / Astronomical units.
- **Processing**: Standardizes column schema and validates record bounds.
- **Database Seeding**: Inserts clean data into relational PostgreSQL tables.
- **Derived Calculation**: Applies physical formulas to produce derived quantities.
