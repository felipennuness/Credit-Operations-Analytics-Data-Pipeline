# Architecture

## Overview

This project combines a data engineering pipeline with a Qlik analytical application for credit operations.

The architecture separates operational ingestion, transformation, relational storage, analytical preparation, and business consumption.

## End-to-end flow

```text
Operational Files / Spreadsheet Sources
                 |
                 v
         Python / Pandas ETL
                 |
                 v
       Data Cleaning & Typing
                 |
                 v
      Business Transformations
                 |
                 v
       Relational Normalization
                 |
                 v
     SQLAlchemy / PyMySQL Load
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
      Qlik Associative Model
                 |
                 v
     Business Rules & Measures
                 |
                 v
          Qlik Application
```

## Architecture layers

### 1. Operational source layer

The original operational data contained credit contracts, proposals, customer information, financial values, rates, commissions, release data, organizational attributes, and other business fields.

The public portfolio does not include the original confidential dataset.

### 2. ETL layer

Python and Pandas were used to clean and structure source data before relational loading.

Key responsibilities included:

- source column validation
- data type conversion
- null handling
- numeric normalization
- date preparation
- business key preservation
- repeated-column normalization
- creation of relational output structures

### 3. Relational database layer

The transformed datasets were loaded into MySQL through SQLAlchemy / PyMySQL.

The relational layer provides a structured foundation for downstream analytical preparation and validation.

### 4. Analytical preparation layer

The Qlik application consumes prepared analytical datasets through QVD-based structures.

The QVD layer separates operational preparation from final dashboard consumption and supports a cleaner analytical model.

### 5. Qlik associative model

The application combines facts, dimensions, relationship/intermediate tables, targets, regional structures, opportunity logic, performance data, and reconciliation information.

The model supports cross-analysis between:

- contracts
- proposals
- customers
- managers
- regional structures
- commercial portfolios
- opportunities
- financial measures
- reconciliation events

### 6. Business consumption layer

The final application provides six analytical views:

1. Executive Overview
2. Commercial Funnel
3. Portfolio & Opportunities
4. Financial Results
5. Commercial Performance
6. Reconciliation & Delinquency

## Design principles

- Preserve business identifiers correctly
- Validate data before database loading
- Normalize spreadsheet-style structures
- Separate preparation from presentation
- Avoid duplicated metrics across analytical layers
- Convert operational data into action-oriented business signals
- Protect personal and confidential information in public documentation
