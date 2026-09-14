# ETL & Data Engineering

## Purpose

The ETL layer prepares operational credit data for relational storage and analytical consumption.

The original source contained a large number of columns with mixed data types, repeated structures, nullable numeric fields, date fields, financial values, rates, commissions, and business identifiers.

## Technology stack

- Python
- Pandas
- SQLAlchemy
- PyMySQL
- MySQL
- Excel / spreadsheet sources

## Main ETL stages

```text
Read source file
      ↓
Validate expected columns
      ↓
Clean empty strings / nulls
      ↓
Convert dates and numeric fields
      ↓
Correct business key types
      ↓
Apply business transformations
      ↓
Normalize repeating structures
      ↓
Validate transformed datasets
      ↓
Load into MySQL
      ↓
Post-load validation
```

## Business key preservation

One important data quality issue involved the contract identifier.

Examples of the original format included values similar to:

```text
20-77774/16006
21-00037/16003
```

Because the identifier contains hyphens and slashes, it must be modeled as a **text field**, not as a numeric `BIGINT`.

Treating the contract as text preserves the original business key and prevents invalid conversions or missing identifiers.

## Nullable integer treatment

Some operational fields contained a mixture of numbers and empty strings.

For fields such as the number of settled installments, the transformation process:

1. replaced empty values with nulls;
2. converted valid values to numeric;
3. used a nullable integer representation;
4. converted missing values into database-compatible null values before loading.

This avoided invalid inserts while preserving the semantic difference between zero and missing information.

## Release normalization

The spreadsheet contained repeating release columns such as:

```text
liberacao_1 / valor_1
liberacao_2 / valor_2
liberacao_3 / valor_3
...
```

Instead of keeping this wide structure, the ETL transforms the releases into a relational fact structure with fields equivalent to:

```text
contract
release_number
release_type
release_value
```

Conceptually:

```text
Wide Spreadsheet

contract | release_1 | value_1 | release_2 | value_2
----------------------------------------------------
A        | Type X    | 1000    | Type Y    | 500

                ↓

Normalized Release Fact

contract | release_number | release_type | release_value
---------------------------------------------------------
A        | 1              | Type X       | 1000
A        | 2              | Type Y       | 500
```

This improves scalability, querying, and analytical modeling.

## Numeric validation

Financial release values required explicit numeric conversion because source files could contain blank strings mixed with valid numbers.

The ETL removes invalid blanks and converts valid release amounts to numeric values before database insertion.

## Null handling

A reusable null-conversion step prepares Pandas dataframes for relational insertion by replacing `NaN` / `NaT` values with Python `None` where appropriate.

This prevents spreadsheet-specific null representations from being incorrectly written to the database.

## Database loading

The relational load uses SQLAlchemy with PyMySQL and chunked inserts.

Chunking allows the process to load large datasets in manageable batches while making troubleshooting easier when a specific transformation or database constraint fails.

## Validation & troubleshooting

The implementation included explicit diagnostic checks for:

- missing contract identifiers
- unexpected dtypes
- empty strings inside numeric columns
- invalid date conversion
- relational schema mismatch
- database insertion failures
- transformed row counts

The ETL was iteratively adjusted until key validation checks returned clean results before the final relational load.

## Public portfolio scope

The actual production dataset is not published.

Any future example code or sample data in this repository will use synthetic or anonymized values while preserving the same transformation patterns.
