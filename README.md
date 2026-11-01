# scotland-tourism-analytics
MSc consultancy project for VisitScotland: Python analysis of four public datasets, using K-Means clustering and regression to show how Scotland can balance tourism demand across regions and seasons.
# Driving Sustainable Tourism Growth in Scotland through Data Analytics

MSc Data Science for Business consultancy project, University of Stirling (September 2026).

**Question (set by VisitScotland):** How can VisitScotland optimise tourism demand across regions and seasons while maximising economic value?

## Approach

The work follows the CRISP-DM framework and uses only public, aggregated secondary data, with no personal data.

| Dataset | Source | Used for |
|---|---|---|
| Great Britain Tourism Survey (overnight trips) | VisitScotland | Domestic overnight trends and seasonality |
| Great Britain Day Visits Survey | VisitScotland | Day-visit patterns and the overnight vs day comparison |
| International Passenger Survey | ONS / VisitBritain | International growth, markets and spend |
| Regional domestic tourism | statistics.gov.scot | Council-area analysis, clustering and regression |

**Data handling:** the council-level CSV (2,673 rows, 32 council areas, nine rolling three-year periods) is loaded and cleaned in code. Figures from the GBTS, GB Day Visits and IPS publications come as PDF and Excel summary reports, so key statistics were extracted manually into dataframes and cross-checked against the originals.

**Methods:** feature engineering (spend per visit, nights per visit), exploratory analysis, K-Means clustering (features standardised, k = 3 chosen with the elbow method) and simple linear regression (R², RMSE, MAE).

**Tools:** Python 3, pandas, Matplotlib, Seaborn, scikit-learn, Jupyter Notebook.

## Key findings

- **Regional concentration:** Edinburgh had about 372 times the domestic visits of the least visited council area (2017–2019 data).
- **Seasonality:** Q3 accounted for 46.2% of year-to-date overnight visitor spend in 2025.
- **Volume to value:** domestic overnight trips fell 14.5% in 2024 while total spend rose 4.7% and spend per trip rose from £258 to £315.
- **International:** 4.4 million visits generated about £4.0 billion in 2024. North American visitors spent about £1,434 per trip against £639 for European visitors.
- **Clusters:** High Volume Hubs (3 areas), High Value Destinations (3 island authorities) and Emerging/Undervisited (26 areas).
- **Regression:** visit volume explained 97.2% of variation in regional spend (R² = 0.972). The model suggests doubling an average emerging region's visits would add about £63.9 million a year.

## Recommendations

1. Regional dispersal strategy for the 26 emerging council areas
2. Dedicated shoulder-season programme
3. Prioritise North American market development
4. Adopt a visitor-yield framework alongside volume metrics
5. Differentiated management strategies for each cluster type

## Limitations

The regional dataset ends at 2017–2019, before the pandemic, and the regression assumes a linear, constant relationship between visits and spend. The regression is fitted on all periods pooled together and evaluated in-sample, so it describes the relationship in this data rather than forecasting future spend.

## Repository contents

```
├── scotland_tourism_analysis.ipynb   # full analysis: cleaning, EDA, K-Means, regression
├── requirements.txt
├── data/
│   └── download3544804378906531173.csv   # statistics.gov.scot regional domestic tourism
├── figures/                              # charts exported by the notebook
└── report/                               # dissertation PDF
```

## How to run

1. Download the regional domestic tourism CSV from [opendata.scot](https://opendata.scot/datasets/visitscotland-regional+domestic+tourism/) and put it next to the notebook (or edit the path in Section 2).
2. `pip install -r requirements.txt`
3. Open the notebook in Jupyter and run the cells from top to bottom. Charts are saved as PNG files in the working folder.

## Author

Abisola Akinbobola | [LinkedIn](https://www.linkedin.com/in/abisola-t-akinbobola-4024a1219) | atakinbobola@gmail.com
