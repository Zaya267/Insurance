# Insurance Data Engineering – Life, Funeral & RA Analytics with Geospatial Insights

## Overview
ETL + analytics pipeline for insurance policies to identify trends, risk, and opportunities.

## Architecture
RAW → Staging → Fact/Dimension → Analytics → Geospatial Insights

## Data Sources
- Mockaroo: generate synthetic policy datasets
- Kaggle Insurance Datasets: https://www.kaggle.com/datasets

## Environment Setup (Free Tier)
1. AWS S3 buckets: insurance-raw, insurance-staging, insurance-curated
2. Snowflake: XSMALL warehouse, AUTO_SUSPEND = 60s, Database INSURANCE_DB, schema PUBLIC

## Steps
1. Create file format and stage in Snowflake pointing to S3
2. Create RAW_POLICIES table and load CSV
3. Create staging table STG_POLICIES with proper types
4. Create dimension and fact tables: DIM_CLIENT, DIM_POLICY_TYPE, FACT_POLICY
5. Apply business rules: normalize policy types, handle missing data
6. Create STREAM and TASK for incremental loads
7. Geospatial: CLIENT_LOCATION → GEOGRAPHY, map high-value clusters
8. Dashboard: policies per location, risk segmentation

## Cost Control
- XSMALL warehouse
- AUTO_SUSPEND = 60s
- TASK scheduled hourly

## Scripts
01_create_file_format_and_stage.sql
02_create_raw_table.sql
03_load_raw.sql
04_create_staging_table.sql
05_create_fact_dim_tables.sql
06_apply_business_rules.sql
07_create_stream_and_task.sql
08_geospatial_analysis.sql