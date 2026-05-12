# Project Log — Big Data Tourism & English Proficiency

## Step 1 — MongoDB connection validation

The Jupyter Lab environment was successfully connected to the MongoDB database `turismo_epi`.

## Step 2 — Data extraction to Spark DataFrames

The MongoDB collections were extracted into Pandas DataFrames and then converted into Spark DataFrames for distributed processing with PySpark.

Loaded datasets:

| Dataset | Rows | Columns |
|---|---:|---:|
| English Proficiency Index | 116 | 4 |
| Tourist Arrivals by Region | 189 | 3 |
| International Tourist Departures | 2227 | 4 |
| Tourist Expenditures Abroad | 1358 | 4 |
| Business Trips | 3825 | 4 |
| Personal Trips | 3925 | 4 |
| Business/Personal Ratio | 3825 | 4 |

Note: the arrivals dataset is aggregated by region, so it will be used as complementary contextual analysis rather than as the main country-level join dataset.

## Step 3 — Preprocessing, cleaning and data integration

In this stage, the project moved from raw extracted datasets to an integrated analytical dataset.

The main operations performed were:

- Null value checks across all original datasets;
- Conversion of the English Proficiency dataset country codes from ISO2 to ISO3;
- Removal of the unnecessary `flagCode` column after creating `country_code`;
- Selection of the most recent available year per country for each tourism indicator;
- Integration of the tourism datasets using `country_code`;
- Join between the integrated tourism table and the English Proficiency dataset;
- Removal of redundant country-name columns;
- Creation of derived variables:
  - `total_inbound_trips`;
  - `expenditure_per_departure`.

The final processed dataset was exported as:

`data/processed/features_country_level.csv`

This dataset will be used for exploratory analysis, visualisation, clustering and the Streamlit dashboard.