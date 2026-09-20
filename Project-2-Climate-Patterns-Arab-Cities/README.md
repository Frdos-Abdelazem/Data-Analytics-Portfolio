# 🌡️ Climate Patterns Across Arab Cities (2016-2026)

## 🎯 Core Question
How do temperature and rainfall patterns differ across major Arab cities over the past decade, and is there evidence of a warming trend in any of them?

## 📦 Data Collection
Unlike the first project, this dataset was **not downloaded from a ready-made source** — it was collected live via the **Open-Meteo Historical Weather API** (no API key required), by writing a Python script to:
- Query 10 years of daily weather data (2016–2026) for 4 cities using latitude/longitude coordinates
- Handle the API's nested JSON response structure and convert it into a clean tabular format
- Merge results from 4 separate API calls into a single dataset

**Cities analyzed:** Cairo (Egypt), Riyadh (Saudi Arabia), Dubai (UAE), Khartoum (Sudan)

**Source:** [Open-Meteo Historical Weather API](https://open-meteo.com/en/docs/historical-weather-api)

## 🔍 Analysis Plan
1. Scope the problem: compare average temperature and rainfall across the 4 cities
2. Data cleaning (partial-year exclusion for trend analysis, missing value check)
3. Comparative exploratory analysis:
   - Average max temperature by city
   - Year-over-year temperature trend (linear regression slope + correlation)
   - Seasonal temperature distribution by month
   - Annual rainfall comparison
4. Data-backed analytical insights
5. Actionable, measurable recommendations

## 📊 Key Findings

- **Khartoum is the hottest city on average (37.0°C)**, Cairo the coolest (30.2°C) — expected given geography.
- **Cairo shows a statistically meaningful warming trend: +0.22°C/year (r = 0.81)** — over 9 years, that's roughly +2°C.
- The other three cities (Riyadh, Dubai, Khartoum) show weak correlations (r = 0.29–0.43), consistent with normal year-to-year variability rather than a real trend.
- **Dubai receives the most annual rainfall (~93mm/year)** despite being a desert city — driven by occasional intense rain events, not steady precipitation.

## 💡 Recommendations

1. **Flag Cairo for further climate investigation** — the warming trend has real implications for urban planning (cooling infrastructure, energy demand).
2. **Extend the analysis with more weather stations** around Greater Cairo to rule out a local urban heat-island effect vs. a genuine regional trend.
3. **Track this annually** — recompute the trend each year; a persistent r > 0.7 across more years strengthens the case for a real long-term trend.

## ⚠️ Caveats
- 10 years is a relatively short window for climate trend analysis (meteorological convention typically uses 30-year baselines).
- Single-station time series per city — local factors (e.g., urbanization near the station) could contribute to the trend independent of broader climate change.

## 🛠️ Tools
Python, Requests (API calls), Pandas, NumPy, Matplotlib, Seaborn

---
📂 Files:
- `Climate_Patterns_Arab_Cities.ipynb` — full analysis with executed outputs
- `weather_data_4cities_10years.csv` — collected dataset (15,584 rows)
