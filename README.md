# Migraine Symptom Visualization

Interactive analysis of how sensory symptoms relate to migraine intensity and duration.

<!-- Add 1-2 screenshots or a GIF of the dashboard here once deployed -->
<!-- ![dashboard preview](results/visualizations/dashboard_preview.png) -->

## Overview
Migraine triggers and symptom patterns are hard to see in raw data. This project explores a 400-patient migraine dataset to surface which sensory symptoms correlate most strongly with migraine intensity and duration, then makes those patterns explorable through an interactive dashboard.

## Key Findings
Analyzed 400 patients (mean age 32, range 15–77) across six migraine types.

- **59% of patients reported severe migraines** (intensity level 3); only 5% reported no pain
- **Vertigo (50 patients) and tinnitus (24 patients)** were the most common sensory symptoms and showed the strongest correlation with both migraine intensity and duration
- **Symptom count scales with severity** — patients with severe migraines consistently reported more concurrent sensory symptoms than those with mild or moderate cases
- **Diplopia, visual defects, and paresthesia** were most frequent specifically in severe and longer-lasting migraines, despite being rarer symptoms overall
- **Basilar-type aura and familial hemiplegic migraine** showed the highest symptom diversity among the six migraine types studied

**Takeaway:** sensory symptom presence and count could serve as a low-cost, objective signal for migraine severity — of practical interest for triage or as a feature set in a future predictive model (see Future Work in the full report).

## Live Dashboard
- **Tableau Public:** *[add link once published]*
- **Dash app (run locally):** see [Running the Dash App](#running-the-dash-app) below

> Tableau Public is the recommended way to share this — it's free to host indefinitely and viewable without anyone cloning the repo. The Dash app is kept for anyone who wants to run the fuller interactive version locally.

## Dataset
- **Source:** [Migraine Dataset, Kaggle](https://www.kaggle.com/datasets/ranzeet013/migraine-dataset)
- **Size:** 400 records · 24 attributes
- **Contents:** sensory symptoms, migraine intensity/characteristics, patient demographics
- Full attribute definitions: [source materials](https://codeocean.com/capsule/1269964/tree/v1)

## Methodology
1. **Preprocessing** — cleaned and encoded the dataset (`notebooks/01_data_preprocessing.ipynb`)
2. **Exploratory analysis** — heatmaps, scatter plots, box plots, and stacked bar charts to surface correlations (`notebooks/02_exploratory_analysis.ipynb`)
3. **Interactive dashboard** — Plotly Dash app for open-ended exploration (`scripts/dash_app.py`)

## Repository Structure
```
├── data/                          # Dataset
├── notebooks/
│   ├── 01_data_preprocessing.ipynb
│   └── 02_exploratory_analysis.ipynb
├── scripts/
│   ├── data_processing.py
│   ├── eda.py
│   ├── visualizations.py
│   └── dash_app.py
├── results/
│   └── visualizations/            # Exported charts
└── requirements.txt
```

## Running the Dash App
```bash
git clone https://github.com/dpounds24/migraine-symptom-visualization.git
cd migraine-symptom-visualization
pip install -r requirements.txt
cd scripts
python dash_app.py
```
Then open `http://localhost:8050`.

## Tech Stack
Python · Pandas · NumPy · Plotly · Dash · Matplotlib · Seaborn

## Limitations
- Self-reported symptom and intensity data; no clinical verification
- 400-record dataset from a single source (findings are exploratory)
- Limited variability for some symptoms (e.g., ataxia, dysarthria) constrained their statistical power; addressed by aggregating into a total symptom count
- High prevalence of general symptoms like nausea and phonophobia reduced their discriminative value for distinguishing severity

## Acknowledgments
- [Migraine Dataset](https://www.kaggle.com/datasets/ranzeet013/migraine-dataset) via Kaggle
- Dr. Qian, for guidance throughout the project
- Meharry Medical College

## Author
Destiny Pounds — [portfolio](https://dpounds24.github.io/portfolio/) · [LinkedIn](https://linkedin.com/in/destiny-pounds)
