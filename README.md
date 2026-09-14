# Credit Operations Analytics & Data Pipeline

![Status](https://img.shields.io/badge/status-portfolio%20case-success)
![Qlik](https://img.shields.io/badge/Qlik-Sense%20%7C%20Cloud-009845)
![Python](https://img.shields.io/badge/Python-ETL-3776AB)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Transformation-150458)
![MySQL](https://img.shields.io/badge/MySQL-Relational%20Database-4479A1)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-Database%20Loading-D71F00)

> **Public portfolio case study based on a real credit-operations analytics project.** Personal data, client information, confidential identifiers, production credentials, and proprietary data are excluded or anonymized. Dashboard values shown in the public evidence are simulated.

## Overview

This project documents a credit-operations solution that combines practical **data-engineering work** with a **Qlik analytical application** for executive monitoring, commercial analysis, opportunity prioritization, financial performance, and reconciliation.

The portfolio intentionally documents two complementary components:

1. **Data engineering** — spreadsheet/operational ingestion, cleaning, typing, normalization, relational modeling, and MySQL loading with Python / Pandas and SQLAlchemy / PyMySQL.
2. **Qlik analytics** — prepared analytical datasets, QVD structures, associative modeling, business rules, opportunity scoring, KPIs, and dashboards.

> The public documentation does **not** claim a directly validated automated lineage from the MySQL staging layer into the QVD layer unless that connection is explicitly verified.

## Solution components

```text
DATA ENGINEERING COMPONENT
Operational / Spreadsheet Sources
              |
              v
      Python + Pandas ETL
              |
              v
 Cleaning / Type Validation
              |
              v
 Business Transformations
              |
              v
 Relational Normalization
              |
              v
 SQLAlchemy / PyMySQL
              |
              v
            MySQL

QLIK ANALYTICS COMPONENT
Prepared Analytical Sources
              |
              v
     QVD / Preparation Layer
              |
              v
 Qlik Associative Data Model
              |
              v
 Business Rules / Measures
              |
              v
     Analytical Application
```

See [Architecture](architecture/README.md).

## Data engineering work

The data-engineering component includes practical ETL work such as:

- spreadsheet ingestion with **Python / Pandas**;
- data-type validation and normalization;
- null and empty-string treatment;
- date and numeric field preparation;
- preservation of credit-contract identifiers;
- normalization of repeating release fields;
- relational database loading with **SQLAlchemy / PyMySQL**;
- MySQL target modeling and validation;
- troubleshooting of schema and type incompatibilities.

One representative issue involved contract identifiers containing hyphens and slashes. These identifiers had to be modeled as **text rather than numeric values** to preserve the original business key.

Another transformation converted repeating release fields into a normalized release structure instead of keeping a wide spreadsheet-style model.

See [ETL & Data Engineering](etl/README.md).

## Qlik analytical model

The analytical application consolidates subject areas including:

- contracts;
- proposals;
- customers;
- commercial links / portfolio relationships;
- targets and regional structures;
- opportunity scoring;
- manager performance;
- financial metrics;
- reconciliation and delinquency monitoring.

The Qlik layer uses prepared analytical datasets and QVD-based structures to support an associative model across operational, commercial, financial, and management perspectives.

See [Data Model](data-model/README.md).

## Analytical application

The application is organized into six business views:

1. **Executive Overview** — production, contracts, customers, revenue, commission, recurrence, evolution, operation mix, target performance, and target gaps.
2. **Commercial Funnel** — proposal volume, decision and approval rates, non-converted value, in-progress proposals, SLA monitoring, and regional/manager analysis.
3. **Portfolio & Opportunities** — qualified opportunities, estimated financial potential, priority classification, maturity, recurrence, and opportunity radar.
4. **Financial Results** — production, estimated revenue, commission, spread, CET, operation mix, partner weight, and financial evolution.
5. **Commercial Performance** — realized results, funnel efficiency, opportunity potential, and manager-level prioritization.
6. **Reconciliation & Delinquency** — expected, discounted, and transferred values, exposure, failures, aging, reconciliation causes, and action queues.

See [Dashboard & Business Views](dashboards/README.md).

## Dashboard gallery

### 1. Executive Overview

![Executive Overview](screenshots/consignado_portfolio_screenshots_sanitized/01-executive-overview.png)

![Executive Regional Performance](screenshots/consignado_portfolio_screenshots_sanitized/09-executive-regional-performance.png)

### 2. Commercial Funnel

![Commercial Funnel](screenshots/consignado_portfolio_screenshots_sanitized/02-commercial-funnel.png)

![Funnel Manager Priorities](screenshots/consignado_portfolio_screenshots_sanitized/10-funnel-manager-priorities.png)

### 3. Portfolio & Opportunities

![Portfolio and Opportunities](screenshots/consignado_portfolio_screenshots_sanitized/03-portfolio-opportunities.png)

![Opportunity Radar](screenshots/consignado_portfolio_screenshots_sanitized/04-opportunity-radar.png)

### 4. Financial Results

![Financial Results](screenshots/consignado_portfolio_screenshots_sanitized/05-financial-results.png)

![Financial Detail by Operation](screenshots/consignado_portfolio_screenshots_sanitized/11-financial-detail-by-operation.png)

### 5. Commercial Performance

![Commercial Performance](screenshots/consignado_portfolio_screenshots_sanitized/06-commercial-performance.png)

![Commercial Performance Radar](screenshots/consignado_portfolio_screenshots_sanitized/12-commercial-performance-radar.png)

### 6. Reconciliation & Delinquency

![Reconciliation Overview](screenshots/consignado_portfolio_screenshots_sanitized/07-reconciliation-overview.png)

![Reconciliation Monitoring](screenshots/consignado_portfolio_screenshots_sanitized/08-reconciliation-monitoring.png)

> Screenshots are sanitized for public presentation and use simulated analytical values.

## Opportunity scoring

The analytical model includes an opportunity-prioritization layer using signals such as:

```text
Contract Maturity
      +
Recurrence
      +
Time Since Last Contract
      +
Portfolio Relationship
      ↓
Opportunity Scoring
      ↓
Priority Classification
      ↓
Estimated Financial Potential
```

The public portfolio documents the analytical concept without exposing proprietary scoring weights.

See [Business Rules & Opportunity Scoring](business-rules/README.md).

## Technologies

| Layer | Technologies |
|---|---|
| Data ingestion | Excel / structured operational files |
| ETL | Python, Pandas |
| Database integration | SQLAlchemy, PyMySQL |
| Relational database | MySQL |
| Analytical preparation | QVD, Qlik Script |
| Analytics | Qlik Sense / Qlik Cloud |
| Modeling | Associative Data Model |
| Business analytics | KPIs, calculated measures, opportunity scoring |

## Key technical challenges

- Incorrect source data types
- Empty strings mixed with numeric values
- Nullable integer handling
- Preservation of business identifiers
- Normalization of repeated spreadsheet columns
- Relational loading errors
- Data validation across engineering and analytical components
- Integration of operational, commercial, financial, and reconciliation perspectives
- Converting portfolio behavior into actionable opportunity signals

## Privacy & portfolio safety

The original project contains sensitive credit and customer information. Public screenshots were curated and sanitized before publication, and the analytical values shown in this portfolio version are simulated.

The repository does **not** publish CPF/personal identifiers, customer names, production credentials, internal infrastructure details, confidential datasets, or proprietary scoring weights.

See [Privacy & Anonymization](privacy/README.md).

## Repository structure

```text
.
├── README.md
├── PROJECT_SCOPE.md
├── architecture/
│   └── README.md
├── etl/
│   └── README.md
├── data-model/
│   └── README.md
├── business-rules/
│   └── README.md
├── dashboards/
│   └── README.md
├── privacy/
│   └── README.md
└── screenshots/
    ├── README.md
    └── consignado_portfolio_screenshots_sanitized/
```

## Documentation

- [Verified Project Scope](PROJECT_SCOPE.md)
- [Architecture](architecture/README.md)
- [ETL & Data Engineering](etl/README.md)
- [Data Model](data-model/README.md)
- [Business Rules & Opportunity Scoring](business-rules/README.md)
- [Dashboard & Business Views](dashboards/README.md)
- [Privacy & Anonymization](privacy/README.md)
- [Screenshot Evidence](screenshots/README.md)

---

**Portfolio project by Luiz Felipe Nunes — BI Developer | Qlik | SQL | Python | Data Analytics**
