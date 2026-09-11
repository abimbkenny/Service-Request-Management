# SRM Power BI DAX Measures — Backup Reference

The saved PBIX is the authoritative source for exact DAX expressions. This document records the measure layer and intended business purpose.

## Core measures
- Total Requests — total service requests at the fact grain.
- Open Requests — requests currently considered open under the project's status definition.
- Unresolved Requests — requests without a resolution date.
- Pending Approval Requests — requests in Pending Approval status.
- Average Request Age Hours — average request age using the project's request-age logic.
- Requests by Assigned Agent — request workload using the assigned-agent relationship.
- Requests by Requester — request volume using the requester relationship.
- Requests Submitted — request volume by submission date.

## SLA / performance
SLA-related measures and calculations support Page 2 for SLA status, breach monitoring, and performance analysis.

## Relationship guidance
The employee dimension is used for multiple business roles. The model can keep one employee relationship active as the default path and use an inactive alternate relationship for requester analysis when appropriate.

## Authoritative source
Use the saved PBIX for the exact current expressions.
