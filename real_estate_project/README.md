# Real estate listings analysis (Yandex.Realty)
(Notebook is currently in Russian; English version in progress.)

### Overview
Exploratory analysis of apartment listings in Saint Petersburg and nearby areas. The goal is to identify the key factors that drive market price and support automated anomaly/fraud detection. The dataset includes both user-entered listing attributes and geo features (distance to the city centre, airport, parks, water).

### What was done
- Data cleaning and preprocessing
- Feature engineering (additional parameters for analysis)
- Exploratory data analysis with visualisations
- Outlier handling
- Analysis of the main price drivers and seasonal trends

### Key findings
- **Size matters:** larger total area and living area are associated with higher prices.
- **Location matters:** apartments closer to the city centre tend to be more expensive; ceiling height is also higher closer to the centre.
- **Rooms & layout:** most listings (≈90%) are 1–3 room apartments; more rooms generally means a higher price; the kitchen area share depends on the number of rooms.
- **Floor effect:** first-floor apartments are cheaper; last-floor apartments are more expensive than first-floor ones but cheaper than apartments on middle floors.
- **Seasonality:** listings posted in summer months and in January are, on average, cheaper than listings posted in other months.
- **Time trend:** prices were highest in 2014, declined during 2015–2018, and started to rise again in 2019.
