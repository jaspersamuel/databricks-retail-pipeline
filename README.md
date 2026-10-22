# Retail Sales Data Pipeline — Databricks

## Project Overview

A portfolio project demonstrating how a retail transaction dataset can be ingested, validated, transformed and aggregated using a Medallion architecture in Databricks.

The project combines data engineering with Technical Business Analysis, including source-to-target mapping, business-rule definition, data-quality investigation, acceptance testing and financial reconciliation.

## Business Problem

Duplicate transaction records and incomplete product descriptions can affect the reliability of sales reporting. Business stakeholders need transparent metrics, traceable data-quality exceptions and clearly defined rules for reporting sales, returns and cancellations.

## Architecture

- **Bronze:** Ingest and preserve source records.
- **Silver:** Standardise fields, parse timestamps, investigate missing descriptions and retain data-quality traceability.
- **Gold:** Aggregate transaction values and quantities by date, country, product and transaction classification.

## Key Findings

- 541,909 source transaction rows ingested.
- 1,454 records initially identified with missing or blank descriptions.
- 135,080 records identified with missing customer IDs.
- 4,879 exact duplicate groups containing 5,268 extra copies identified for investigation.
- Hypothetical exact deduplication changed the signed transaction value by 21,740.98 currency units.
- Silver-to-Gold signed transaction value reconciled with a difference of zero.
- No duplicate keys were found at the defined Gold reporting grain.

## Business and Technical Deliverables

- Source-to-target data maps.
- Documented business rules and assumptions.
- PySpark transformations and Delta tables.
- Data-quality profiling and exception analysis.
- Acceptance criteria and reconciliation tests.
- Gold reporting datasets for country and product analysis.

## Limitations

Exact matching does not prove that every repeated record is erroneous. Sales, returns and cancellations require validated business definitions. Profit cannot be calculated without suitable cost data.

## Reproduction

The notebooks are provided as a learning reference. Reproduction requires a compatible Databricks environment, access to the source dataset and permission to create the required tables.
