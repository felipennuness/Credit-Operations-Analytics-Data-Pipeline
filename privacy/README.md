# Privacy & Anonymization

## Why this matters

This project is based on a real credit operations implementation and therefore involves data categories that must not be exposed in a public portfolio.

The GitHub version is designed to demonstrate architecture, analytical reasoning, data engineering decisions, Qlik modeling, and dashboard design without publishing confidential production information.

## Information excluded from the public repository

The public case study must not expose:

- CPF or equivalent personal identifiers
- customer names
- real customer contract numbers
- dates or values that can identify an individual customer when combined
- employee personal information where unnecessary
- production credentials
- passwords or tokens
- database connection strings
- server hostnames / IP addresses
- proprietary company infrastructure
- internal URLs
- confidential source datasets
- client-specific documentation
- proprietary scoring weights

## Screenshot sanitization

Before a screenshot is published, the following items should be reviewed and replaced or hidden when present:

- customer identifiers
- contract identifiers tied to individuals
- unmasked personal information
- real internal usernames or emails
- confidential organization / client identifiers
- infrastructure or connection details

Names used only to demonstrate dashboard layout may also be generalized to neutral labels when the real identity does not add technical value.

## Masked analytical fields

The Qlik analytical model already includes masked customer/CPF fields in parts of the application.

Even when a value is masked in the analytical layer, screenshots are reviewed again before public publication.

## Synthetic examples

Any sample datasets or code examples added to this repository should use synthetic values while maintaining the same:

- data types
- table relationships
- transformation patterns
- business-rule structure
- analytical behavior

## Portfolio principle

The public repository should be detailed enough to demonstrate the technical implementation while remaining impossible to use as a reconstruction of confidential customer or company data.
