# Architecture Decision Records (ADR)

## ADR 001: Separation of Data Infrastructure & Machine Learning
- **Status**: Accepted
- **Context**: The project spans data engineering, SQL database design, statistical analysis, and machine learning.
- **Decision**: Split the project into two distinct repositories:
  1. `neutron-star-observational-database` (Data Engineering & Analysis)
  2. `neutron-star-theoretical-model-validation` (Machine Learning Application)
- **Consequences**: Clear separation of concerns, cleaner repository structures, better portfolio presentation.

## ADR 002: PostgreSQL as Core Relational Database
- **Status**: Accepted
- **Context**: Need a robust relational database supporting complex queries, constraints, and standard SQL.
- **Decision**: Select PostgreSQL for core database storage.
