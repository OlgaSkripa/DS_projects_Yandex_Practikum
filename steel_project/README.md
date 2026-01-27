# Steel Temperature Prediction (Final Project)

## Project overview
This project aims to help a steel plant reduce energy consumption during steel processing by predicting the final temperature of steel in a ladle (the temperature measured before the steel is sent to continuous casting).

The work is based on several CSV tables provided by the “client” (project brief). The dataset includes information about heating by electrodes, gas blowing, bulk and wire additives, and temperature measurements.  

**English version:** in progress (the main notebook/report is currently in Russian).

## Business goal
Reduce production costs by lowering electricity usage at the heating stage.  
To support this, we build a model that predicts the **final steel temperature** for each batch.

## Data sources
Input data is provided as multiple CSV files:

- `data_arc.csv` — electrode heating data (start/end time, active and reactive power)
- `data_bulk.csv` — bulk materials added (volumes)
- `data_bulk_time.csv` — bulk materials added (timestamps)
- `data_gas.csv` — inert gas blowing data
- `data_temp.csv` — temperature measurements (value and timestamp)
- `data_wire.csv` — wire materials added (volumes)
- `data_wire_time.csv` — wire materials added (timestamps)

All tables contain a **batch ID** used to merge and aggregate the data.

## Success metric
Model quality is evaluated using **MSE (Mean Squared Error)**.  
The target threshold in the project brief is **MSE ≤ 6.8**.

## Work plan
1. Understand the production process and define what may affect final temperature
2. Review the data and check its quality
3. Perform exploratory data analysis (EDA)
4. Prepare modelling dataset: aggregation by batch, feature engineering, multicollinearity checks
5. Train and compare several models, tune hyperparameters
6. Iterate on the feature set and retrain models
7. Test and evaluate the final model
8. Summarise results and conclusions

## Key steps and methods

### 1) Production process understanding
Final temperature is affected by:
- initial temperature of a batch,
- heating power and heating duration,
- alloying additives (bulk and wire),
- inert gas blowing,
- timing and duration of processing steps.

This understanding was used to design meaningful features rather than relying only on “raw” columns.

### 2) EDA and data quality checks
Typical checks performed:
- converting columns to appropriate types (timestamps, numeric types),
- detecting and removing anomalous batches (e.g., extreme power values),
- handling missing values (e.g., missing additive volumes treated as 0 where appropriate),
- removing anomalous temperature measurements,
- investigating differences in the number of unique batches across tables,
- preparing the data for aggregation by batch ID.

### 3) Feature engineering (examples)
Examples of engineered features:
- **Energy used for heating**
  - `FullPower = sqrt(P^2 + Q^2)` (active `P` and reactive `Q` power)
  - `Energy = FullPower * time` → feature `energy`
- **Total process time** between first and last temperature measurement (`full_time`)
- **Mean ratio of active/reactive power** (`mean_ratio_power`)
- **Initial temperature** of a batch (`init_temp`)
- **Total gas volume** during blowing (`gas`)
- **Total volumes of bulk and wire additives** per type (`bulk_i`, `wire_i`)

### 4) Modelling
Models were trained and compared (with hyperparameter tuning), followed by:
- feature importance analysis,
- iterations on the feature set,
- final evaluation on a test set using MSE.

## Notes
- The original report/notebook is currently in Russian.
- **English version is in progress.**
