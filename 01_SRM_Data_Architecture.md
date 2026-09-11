# Service Request Management & Analytics Platform — Data Architecture

## Purpose
End-to-end service request management and analytics using Dataverse, Microsoft Fabric Medallion Architecture, Power BI, DAX, row-level security, and governance.

## Architecture
Dataverse / operational source → Fabric Bronze → Fabric Silver → Fabric Gold → Power BI semantic model → governed dashboards.

## Bronze
Source-oriented copies of five operational tables:
- Service Requests
- Employees
- Service Teams
- Request Categories
- Request History

## Silver
Completed Dataflow Gen2 transformations:
- silver_service_requests
- silver_employees
- silver_service_teams
- silver_request_categories
- silver_request_history

Silver standardizes names, data types, option-set values, null handling, and business-friendly fields. Columns initially typed as Any were explicitly converted before destination mapping.

## Gold
Fact:
- gold_fact_service_requests

Dimensions:
- gold_dim_employees
- gold_dim_service_teams
- gold_dim_request_categories
- gold_dim_date

The Gold fact was enriched by merges with request categories, service teams, employees for assigned agent, and employees for requester.

## Power BI star schema
The central fact is gold_fact_service_requests. Dimensions provide date, employee, team, and category slicing. Employee role relationships distinguish assigned agent from requester analysis; alternate role relationships may be inactive and activated by DAX when required.

## Security
Power BI RLS uses a security mapping table with TEAM001, TEAM002, and TEAM003. Security was tested using Power BI's View as functionality.

## Report pages
1. Service Request Management Dashboard
2. SLA & Performance Dashboard
3. Request & Workload Analysis

## Rebuild
The Silver and Gold data backups preserve the data layer. The PBIX preserves the Power BI solution layer. This architecture document, data dictionary, DAX reference, and governance document preserve the rebuild knowledge.
