# Business Rules & Opportunity Scoring

## Purpose

The analytical application goes beyond descriptive reporting by applying business rules that transform operational portfolio behavior into commercial prioritization signals.

The public portfolio documents the logic conceptually without exposing proprietary weights, thresholds, or confidential commercial policies.

## Opportunity scoring concept

The opportunity layer combines multiple portfolio signals to create a prioritization score.

Conceptually:

```text
Contract Maturity
      +
Recurrence Signal
      +
Time Since Last Contract
      +
Portfolio Relationship
      ↓
Opportunity Score
      ↓
Priority Classification
      ↓
Estimated Financial Potential
```

## Main opportunity signals

### Contract maturity

Maturity measures how far an existing relationship or contract has progressed and helps identify accounts that may be eligible for a new commercial approach.

The application groups the portfolio into maturity bands and compares the estimated potential associated with each band.

### Recurrence

Historical recurrence is used as another signal of commercial propensity.

Customers or relationships with repeated historical operations can be analyzed separately from one-time relationships.

### Time since last contract

The time elapsed since the most recent operation is used to identify relationships that have remained inactive for a relevant period.

This signal is combined with maturity and recurrence rather than being treated as an isolated rule.

### Priority classification

The combined score is converted into an actionable priority classification.

The analytical application highlights high-priority opportunities and their estimated financial potential so commercial teams can focus attention where the expected return is greater.

## Estimated financial potential

Potential is used to translate an opportunity signal into an estimated business value.

The application analyzes:

- total estimated potential
- high-priority potential
- potential by region
- potential by manager
- potential by maturity level
- portfolio percentage with identified potential
- average potential ticket

## Capture simulation

The Portfolio & Opportunities view includes a simple scenario mechanism that allows users to evaluate how much potential could be captured under different assumed conversion rates.

This turns a static opportunity estimate into a business-planning tool.

## Commercial funnel rules

The funnel view classifies proposals by operational status and evaluates processing performance.

Key rules include:

- received proposals
- approved proposals
- rejected proposals
- withdrawals / desistências
- proposals in progress
- value not converted
- time in progress
- proposals above the defined SLA threshold

The application separates quantity-based funnel metrics from value-based funnel exposure.

## Target performance

Production is compared against commercial targets at organizational levels such as region, unit, and manager.

The model calculates target attainment and target gap so management can identify both over-performance and the units requiring intervention.

## Financial rules

Financial analysis combines operational volume with economic measures including:

- estimated revenue
- commission
- commission weight over production
- spread
- CET
- average ticket
- operation mix

These metrics help distinguish high-volume operations from operations with different return or commercial cost profiles.

## Reconciliation rules

The reconciliation flow compares three main stages:

```text
Expected Value
      ↓
Discounted Value
      ↓
Transferred Value
```

Differences between the stages are classified into operational exception categories such as discount failure or transfer failure.

The remaining difference is used to measure financial exposure and support a priority action queue.

## Action-oriented design

A recurring principle throughout the application is to move from summary indicators to a practical action list.

Examples include:

- units with the largest target gap
- managers with high value stuck in the funnel
- high-priority commercial opportunities
- manager performance radar
- reconciliation exception queue

The goal is not only to describe what happened, but to indicate **where action is required next**.
