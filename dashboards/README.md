# Dashboard & Business Views

## Overview

The Qlik application is organized into six analytical views that move from executive monitoring to operational action.

The public portfolio will use sanitized screenshots so the design and analytical structure can be demonstrated without exposing personal or confidential business information.

## 1. Executive Overview

The executive page provides a consolidated view of the operation.

### Main KPIs

- Net Production
- Contracts Produced
- Customers Served
- Estimated Revenue
- Total Commission
- Portfolio Recurrence

### Main analyses

- monthly production evolution
- operation-type mix
- target attainment by region
- units with the largest target gaps
- portfolio recurrence profile
- detailed unit performance table

### Business objective

Give management a fast view of scale, financial result, customer reach, target performance, and portfolio recurrence.

---

## 2. Commercial Funnel

The commercial funnel page analyzes proposals from intake through decision.

### Main KPIs

- Proposals Received
- Proposal Volume
- Decision Rate
- Approval Rate
- Non-Converted Value
- Value in Progress Above SLA

### Main analyses

- proposal outcome distribution
- financial value by SLA range
- percentage of delayed in-progress value by region
- non-converted value by operation type
- concentration of delayed pipeline value
- manager action-priority table

### Business objective

Identify process bottlenecks and quantify the financial value trapped in the proposal pipeline.

---

## 3. Portfolio & Opportunities

This page transforms historical portfolio behavior into an opportunity pipeline.

### Main KPIs

- Qualified Opportunities
- Estimated Financial Potential
- High-Priority Opportunities
- High-Priority Potential
- Portfolio with Potential
- Average Potential Ticket

### Main analyses

- commercial potential by region
- capture-rate simulation
- opportunity signals
- potential by contract maturity
- potential concentration by region / manager
- opportunity radar with priority, potential, maturity, last contract, and recurrence context

### Business objective

Support proactive commercial action using portfolio behavior instead of waiting only for new incoming proposals.

---

## 4. Financial Results

The financial page evaluates the economics of originated operations.

### Main KPIs

- Net Production
- Estimated Revenue
- Total Commission
- Commission / Production
- Average Spread
- Average CET

### Main analyses

- estimated revenue versus commission by operation type
- spread versus CET by operation type
- commission weight by region
- commission weight by commercial partner
- estimated revenue and commission evolution
- detailed financial comparison by operation type

### Business objective

Understand not only production volume, but also revenue, commercial cost, pricing characteristics, and operation mix.

---

## 5. Commercial Performance

The performance page combines realized result, funnel efficiency, and future portfolio potential at manager level.

### Main KPIs

- Net Production
- Approval Rate
- Non-Converted Value
- Qualified Opportunities
- Estimated Financial Potential
- Portfolio with Potential

### Main analyses

- realized production versus opportunity potential by manager
- funnel efficiency by manager
- portfolio potential rate by manager
- concentration of high-priority potential
- volume efficiency
- action-oriented performance table

### Business objective

Avoid evaluating commercial performance only through historical production. The page combines what the manager produced, how efficiently the funnel was handled, and how much potential remains in the portfolio.

---

## 6. Reconciliation & Delinquency

This page monitors post-origination financial reconciliation and exception exposure.

### Main KPIs

- Expected Value
- Reconciliation Rate
- Financial Exposure
- Discount Failure
- Transfer Failure
- Contracts with Overdue Installments

### Main analyses

- expected → discounted → transferred flow
- causes of financial divergence
- reconciliation rate evolution
- overdue exception aging
- reconciliation performance by payroll/reconciliation entity
- priority action queue

### Business objective

Identify where expected cash flow diverged from actual discount or transfer behavior and prioritize cases requiring operational treatment.

## Navigation philosophy

The application is structured to support a natural management workflow:

```text
Executive Overview
        ↓
Commercial Funnel
        ↓
Portfolio Opportunities
        ↓
Financial Results
        ↓
Commercial Performance
        ↓
Reconciliation & Delinquency
```

This allows the user to move from **what happened** to **why it happened**, **where potential exists**, and finally **where action is required**.

## Screenshot publication plan

The repository will publish selected sanitized screenshots rather than every screen capture.

The goal is to show one strong visual example from each business view while keeping the main README concise.
