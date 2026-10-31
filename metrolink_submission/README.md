# MetroLink Public Transport Insight — Submission Pack

## Included deliverables
- `MetroLink_Public_Transport_Insight.ipynb` — EDA, data quality, cleaning, joins, feature engineering, visual analysis and feature selection.
- `MetroLink_Analysis_Workbook.xlsx` — executive summary, cleaned data sample, route/period/stop/day-type/delay/event summaries, formulas and charts.
- `MetroLink_Business_Insights_Presentation.pptx` — short management pitch with findings and recommendations.
- `data/` — raw synthetic source tables and full cleaned/prepared dataset.
- `outputs/` — CSV summary tables used by the workbook and pitch.
- `CH16_Assessment_Brief.pdf` — supplied assessment instructions.

## Reproducibility
Synthetic data generated with NumPy random seed `20261031`; coverage is 05-Jan-2026 to 29-Mar-2026. The analysis fact grain is trip-stop. The cleaned dataset includes engineered fields such as `period`, `day_type`, `total_passengers`, `event_flag`, `delay_flag`, `passenger_per_km`, `is_peak`, and categorical integer codes.

## Cleaning decisions
1. Standardized route IDs to uppercase.
2. Removed duplicate `(trip_id, route_id, stop_id)` records.
3. Excluded negative boarding/alighting counts.
4. Replaced missing stop IDs with `UNKNOWN_STOP` to retain records without pretending the stop identity is known.
5. Imputed missing average delay using the median delay for that route.
6. Joined trip, route, calendar and daily operations data.

## Interpretation cautions
- All data and results are synthetic and intended for assessment demonstration only.
- Event-weekend comparisons use non-event weekends as the reference because the generated event dates fall on weekends; the sample contains few event dates, so the comparison is directional, not causal.
- Excel contains pivot-style summary tables and charts. The workbook does not contain native refreshable PivotTable cache objects; create/refresh native PivotTables in Excel if the assessor specifically checks that feature.
- Validate all findings against real operational data before operational use.

## Suggested submission check
Open the notebook and run cells from top to bottom. Open the Excel workbook and inspect the Executive Summary and analysis tabs. Present the PowerPoint as the Round 4 pitch.
