# Database Design & Architecture

## Conceptual Entity-Relationship Overview

The database is modeled around a central `neutron_star` table, connected to relational tables storing measurements, physical parameters, classifications, and reference sources.

```
+--------------------+           +------------------------+
|    neutron_star    | 1       N |      measurement       |
+--------------------+-----------+------------------------+
| id (PK)            |           | id (PK)                |
| name_j2000         |           | neutron_star_id (FK)   |
| name_b1950         |           | parameter_name         |
| galactic_l         |           | value                  |
| galactic_b         |           | uncertainty            |
| distance           |           | unit                   |
+--------------------+           | reference_id (FK)      |
                                 +------------------------+
                                              | N
                                              |
                                              | 1
                                 +------------------------+
                                 |       reference        |
                                 +------------------------+
                                 | id (PK)                |
                                 | bibcode / doi          |
                                 | catalogue_version      |
                                 +------------------------+
```

## Core Design Principles
1. **Normalization**: Primary entities avoid duplicate attribute storage.
2. **Explicit Nullability**: Non-existent parameters are stored as `NULL` rather than default values (e.g. `0.0` or `-999`).
3. **Data Provenance**: Every physical parameter measurement references a data source or publication bibcode.
4. **Derived Separation**: Tables distinguish raw observational values from physical derived parameters.
