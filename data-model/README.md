# Data Model

## Overview

The Qlik application uses an associative analytical model built from multiple prepared datasets covering operational, commercial, financial, opportunity, performance, and reconciliation domains.

The model was designed to allow users to move from executive indicators to detailed operational records without separating each business subject into isolated applications.

## Main analytical datasets

The application contains prepared datasets equivalent to the following subject areas:

### Core operational facts

- `FATO_CONTRATOS`
- `FATO_PROPOSTAS`

These facts provide the foundation for production, proposal funnel, financial, and operational analysis.

### Customer & relationship structures

- `DIM_CLIENTE`
- `INT_VINCULO`

These structures connect customers and portfolio relationships to historical operations and opportunity logic.

### Targets & organizational structure

- `METAS`
- `METAS_GERENTES`
- `REGIONAIS`

These datasets support comparisons between realized production and commercial objectives by region, unit, and manager.

### Opportunity layer

- `INT_OPORTUNIDADE`

This layer consolidates the business signals used to identify and prioritize commercial opportunities.

### Performance layer

- `DIM_GERENTE_PERFORMANCE`
- `FATO_PERFORMANCE_MENSAL`
- `FATO_PERFORMANCE_OPORTUNIDADE`
- `FATO_PERFORMANCE_META`

These datasets support manager-level analysis combining realized results, funnel efficiency, targets, and opportunity potential.

### Reconciliation layer

A dedicated reconciliation dataset supports the comparison between expected, discounted, and transferred financial values together with exception and delinquency analysis.

## Conceptual model

```text
                 DIM_CLIENTE
                      |
                      |
               INT_VINCULO
                /    |    \
               /     |     \
              v      v      v
     FATO_CONTRATOS  FATO_PROPOSTAS  INT_OPORTUNIDADE
             |             |               |
             |             |               |
             +-------------+---------------+
                           |
                           v
                Performance Structures
                           |
                   +-------+-------+
                   |               |
                   v               v
                METAS          REGIONAIS

Reconciliation data is integrated as a complementary operational/financial analytical domain.
```

## Analytical domains

### Contracts

The contract fact includes fields related to:

- production values
- customer income
- installments
- financial rates
- spread
- CET
- operation value
- gross and net values
- insurance
- IOF
- commission
- employer
- agreement / convenio
- commercial partner
- manager and region

### Proposals

The proposal fact supports funnel and SLA analysis through fields related to:

- proposal status
- proposal timestamps
- processing time
- SLA
- operation type
- proposal value
- revenue
- commission
- manager / region

### Opportunities

The opportunity structure includes analytical fields such as:

- maturity
- recurrence flag
- maturity points
- recurrence points
- time-based points
- opportunity score
- priority
- estimated financial potential
- high-priority flag

### Performance

The performance layer combines metrics such as:

- contracts produced
- net production
- revenue
- commission
- average ticket
- proposals received
- approved / rejected proposals
- proposals in progress
- value not converted
- qualified opportunities
- high-priority opportunities
- estimated potential
- manager targets

### Reconciliation

The reconciliation domain supports analysis of:

- expected value
- discounted value
- transferred value
- reconciliation rate
- discount failure
- transfer failure
- financial exposure
- exception cause
- aging
- overdue contracts

## Why the associative model matters

The Qlik associative model allows a user to select a manager, regional structure, operation type, agreement, commercial partner, or time period and see the impact across multiple business views.

This makes it possible to connect:

```text
Production
   ↕
Proposal Funnel
   ↕
Portfolio Potential
   ↕
Financial Return
   ↕
Manager Performance
   ↕
Reconciliation Risk
```

within one analytical application.

## Privacy-aware fields

The analytical model includes masked identifiers for sensitive customer information. Public examples use masked or synthetic values only.
