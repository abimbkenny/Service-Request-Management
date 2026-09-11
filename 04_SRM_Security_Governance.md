# SRM Security and Data Governance

## Row-Level Security
A Power BI security mapping table maps users to permitted service teams:
- TEAM001
- TEAM002
- TEAM003

The RLS design restricts team-scoped service request information according to the authenticated user's mapping.

## Governance principles

### Bronze
Preserve source-oriented data and source identifiers for traceability.

### Silver
Standardize data types, translate option-set codes, normalize naming, handle nulls, and validate destination mappings.

### Gold
Produce business-ready fact and dimension structures, enrich facts with descriptive attributes, and maintain consistent KPI definitions.

### Power BI
Use a star schema, centralized measures, dimensions for filtering, role-aware relationships, and RLS.

## Data quality
Validation checks were completed during Dataflow Gen2 development. Completed Silver and Gold tables were validated before Power BI consumption.

## Backup
Keep Silver data, Gold data, PBIX, data dictionary, architecture, DAX reference, and security/governance documentation together.
