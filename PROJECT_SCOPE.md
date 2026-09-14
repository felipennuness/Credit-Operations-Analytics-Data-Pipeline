# Verified Project Scope

This file is the source of truth for the public documentation of this portfolio case.

## Confirmed data engineering scope

- Source data originated from structured operational files / spreadsheets.
- Python and Pandas were used for ETL and data preparation.
- SQLAlchemy and PyMySQL were used for relational database loading.
- MySQL was used as the relational database.
- Data quality work included null handling, numeric conversion, date preparation, business-key preservation, and normalization.
- Contract identifiers must be treated as text because the real business key format contains non-numeric characters.
- Repeating release/value columns were transformed into a normalized relational structure.

## Confirmed Qlik analytical scope

The Qlik application includes six major analytical views:

1. Executive Overview
2. Commercial Funnel
3. Portfolio & Opportunities
4. Financial Results
5. Commercial Performance
6. Reconciliation & Delinquency

## Confirmed analytical domains

- Contracts
- Proposals
- Customers / portfolio relationships
- Commercial targets
- Regional structures
- Opportunity scoring / prioritization
- Manager performance
- Financial analysis
- Reconciliation / delinquency

## Confirmed opportunity logic

The application includes analytical fields and rules related to:

- contract maturity
- recurrence
- time since last contract
- opportunity score
- priority
- estimated financial potential
- high-priority opportunities

Exact proprietary scoring weights must not be published.

## Confirmed Qlik preparation structures

The application uses prepared QVD datasets covering subjects such as:

- contract facts
- proposal facts
- customer dimension
- relationship / portfolio linkage
- targets
- manager targets
- regional structures
- opportunities
- manager performance
- monthly performance
- opportunity performance
- target performance
- reconciliation data

## Public documentation restrictions

Do not publish:

- CPF
- customer names
- real customer-linked contract identifiers
- confidential datasets
- production credentials
- internal infrastructure identifiers
- proprietary scoring weights

## Documentation rule

Only implementation details that are verified from the real ETL, Qlik application, QVF structure, or user-provided evidence should be presented as completed work.
