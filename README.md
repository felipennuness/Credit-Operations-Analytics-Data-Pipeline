# Credit Operations Analytics & Data Pipeline

![Status](https://img.shields.io/badge/status-portfolio%20case-success)
![Qlik](https://img.shields.io/badge/Qlik-Sense%20%7C%20Cloud-009845)
![Python](https://img.shields.io/badge/Python-ETL-3776AB)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Transformation-150458)
![MySQL](https://img.shields.io/badge/MySQL-Relational%20Database-4479A1)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-Database%20Loading-D71F00)

> **Public portfolio case study based on a real credit operations analytics project.** Personal data, client information, confidential identifiers, production credentials, and proprietary data are excluded or anonymized. Dashboard values shown in the public evidence are simulated.

## Overview

This project documents an end-to-end **credit operations analytics solution** combining data engineering, relational modeling, Qlik data preparation, business rules, opportunity scoring, financial analysis, commercial performance, and reconciliation monitoring.

The solution was designed to transform operational credit data into an analytical environment capable of supporting both **management visibility** and **action-oriented commercial decisions**.

The project covers two complementary layers:

1. **Data pipeline and preparation** — ingestion, cleaning, typing, transformation, normalization, and relational loading.
2. **Qlik analytics application** — associative modeling, KPIs, business rules, opportunity prioritization, financial analysis, commercial performance, and reconciliation.

## End-to-end architecture

```text
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
     Relational Modeling
              |
              v
 SQLAlchemy / PyMySQL
              |
              v
           MySQL
              |
              v
   Qlik Preparation Layer
              |
              v
             QVDs
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

## Data engineering work

The data pipeline includes practical ETL work such as:

- Spreadsheet ingestion with **Python / Pandas**
- Data type validation and normalization
- Null and empty-string treatment
- Date and numeric field preparation
- Credit contract normalization
- Transformation of repeating release fields into a relational structure
- Relational database loading with **SQLAlchemy / PyMySQL**
- MySQL target modeling
- Data validation before and after load
- Troubleshooting of schema and type incompatibilities

A representative example from the ETL involved contract identifiers that contained characters such as hyphens and slashes. These identifiers had to be modeled as **text rather than numeric values** to preserve the original business key.

Another transformation converted repeating release fields into a normalized release fact structure, avoiding a wide spreadsheet-style model in the analytical database.

See [ETL & Data Engineering](etl/README.md).

## Qlik analytical model

The Qlik application consolidates multiple subject areas, including:

- Contracts
- Proposals
- Customers
- Commercial links / portfolio relationships
- Targets and regional structure
- Opportunity scoring
- Manager performance
- Financial metrics
- Reconciliation and delinquency monitoring

The model uses a QVD-based analytical layer and an associative Qlik model to connect operational, commercial, financial, and management views.

See [Data Model](data-model/README.md).

## Analytical application

The application is organized into six business views.

### 1. Executive Overview

Provides a consolidated management view of the credit operation, including net production, contracts produced, customers served, estimated revenue, total commission, recurrence, production evolution, operation mix, regional target performance, and target gaps.

### 2. Commercial Funnel

Focuses on proposal conversion and operational bottlenecks through proposals received, volume, decision and approval rates, non-converted value, in-progress proposals, SLA monitoring, and regional/manager analysis.

### 3. Portfolio & Opportunities

Transforms portfolio behavior into actionable commercial opportunities through qualified opportunities, estimated financial potential, priority classification, maturity and recurrence signals, opportunity radar, and capture simulation.

### 4. Financial Results

Analyzes the economics of originated operations through production, estimated revenue, commission, spread, CET, operation mix, partner commission weight, and financial evolution.

### 5. Commercial Performance

Combines realized results, funnel efficiency, and portfolio potential to support manager-level performance analysis and prioritization.

### 6. Reconciliation & Delinquency

Monitors expected, discounted, and transferred values, financial exposure, failures, overdue contracts, reconciliation causes, aging, reconciliation performance, and action queues.

See [Dashboard & Business Views](dashboards/README.md).

## Dashboard gallery

### Executive Overview

![Executive Overview](screenshots/consignado_portfolio_screenshots_sanitized/01-executive-overview.png)

### Commercial Funnel

![Commercial Funnel](screenshots/consignado_portfolio_screenshots_sanitized/02-commercial-funnel.png)

### Portfolio & Opportunities

![Portfolio and Opportunities](screenshots/consignado_portfolio_screenshots_sanitized/03-portfolio-opportunities.png)

### Financial Results

![Financial Results](screenshots/consignado_portfolio_screenshots_sanitized/05-financial-results.png)

### Commercial Performance

![Commercial Performance](screenshots/consignado_portfolio_screenshots_sanitized/06-commercial-performance.png)

### Reconciliation & Delinquency

![Reconciliation Overview](screenshots/consignado_portfolio_screenshots_sanitized/07-reconciliation-overview.png)

> Additional sanitized evidence, including the **Opportunity Radar** and **Reconciliation Monitoring** views, is available in [Screenshot Evidence](screenshots/README.md).

## Opportunity scoring

A dedicated analytical layer identifies and prioritizes commercial opportunities based on portfolio behavior.

The model includes signals such as:

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

The public portfolio documents the concepts and analytical design without exposing proprietary scoring weights or confidential business rules.

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
| Business analytics | KPIs, calculated measures, commercial scoring |

## Key technical challenges

The project required solving practical data and modeling problems, including:

- Incorrect source data types
- Empty strings mixed with numeric values
- Nullable integer handling
- Normalization of repeated spreadsheet columns
- Preservation of business identifiers
- Relational loading errors
- Data validation between source, database, and analytical layers
- Integration of operational, commercial, financial, and reconciliation perspectives
- Converting portfolio behavior into actionable opportunity signals

## Privacy & portfolio safety

The original project contains sensitive credit and customer information. Public screenshots were curated and sanitized before publication, and the analytical values displayed in this portfolio version are simulated.

The public repository does **not** publish:

- CPF or personal identifiers
- Customer names
- Real contract identifiers tied to customers
- Production credentials
- Connection strings
- Internal database/server information
- Confidential business datasets
- Proprietary scoring weights

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
