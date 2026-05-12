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