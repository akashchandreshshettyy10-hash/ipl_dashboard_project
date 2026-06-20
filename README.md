# IPL Performance & Insights Dashboard

Data cleaning and visual storytelling on 10 seasons of IPL cricket data (2008-2017) using Pandas, Matplotlib, and Seaborn — 8 charts with business insights, exported as a polished PDF report.

This project performs end-to-end data cleaning and exploratory analysis on a real IPL (Indian Premier League) dataset spanning 636 matches and 150,000+ ball-by-ball deliveries from 2008–2017. It handles missing values and inconsistent team-name entries, then builds 8 visualizations covering team win rates, toss strategy trends, top run-scorers and wicket-takers, and scoring trends over time — each paired with a written business insight. The final output is a presentation-ready PDF report generated entirely with Python (Pandas, Matplotlib, Seaborn, ReportLab).

## Project Structure
ipl_dashboard/

├── data/

│   └── raw/                    matches.csv, deliveries.csv (original data)

├── scripts/

│   ├── 01_data_cleaning.py     loads + cleans both datasets

│   ├── 02_visualizations.py    generates 8 charts + insight text

│   └── 03_build_report.py      assembles everything into a PDF report

├── output/

│   ├── cleaned/                cleaned CSVs (output of step 1)

│   ├── charts/                 8 PNG charts + insights.json (output of step 2)

│   └── report/

│       └── IPL_Insights_Report.pdf   <- final deliverable

└── requirements.txt

## How to Run

```bash
pip install -r requirements.txt
python scripts/01_data_cleaning.py
python scripts/02_visualizations.py
python scripts/03_build_report.py
```

## What Was Cleaned

- Merged inconsistent team name spellings ("Rising Pune Supergiant" / "Rising Pune Supergiants") into one consistent name
- Filled missing `city` values for Dubai-hosted matches using the venue field
- Labeled matches with no winner as "No Result" instead of leaving NaN
- Dropped the fully-empty `umpire3` column
- Removed 1 exact duplicate row in the ball-by-ball data
- Made dismissal-related fields explicit ("Not Out") instead of ambiguous NaNs
- Validated `batsman_runs + extra_runs = total_runs` for every delivery

## The 8 Charts

1. Matches played per season
2. Team win percentage (teams with 30+ matches)
3. Toss decision trend (bat first vs field first) over time
4. Does winning the toss predict winning the match?
5. Top 10 run scorers
6. Top 10 wicket takers
7. Average runs per match by season (scoring trend)
8. Most Player-of-the-Match awards

## Dataset Source

IPL ball-by-ball + match-level data, originally published on Kaggle ("IPL Complete Dataset", manasgarg/ipl), 2008-2017 seasons.
