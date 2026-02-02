# QM640 Scania Component X Analysis

Capstone project for Walsh College **QM640 Data Analytics Capstone** (Winter 2025). Investigates operational drivers of Component X failures in Scania heavy-duty trucks using the [Scania predictive maintenance dataset](https://researchdata.se/en/catalogue/dataset/2024-343).

## Project Objectives
- Identify key sensor predictors of imminent failure (RQ1).
- Compare temporal degradation vs. static specs (RQ2).
- Estimate Remaining Useful Life (RUL) via Cox Proportional Hazards and Kaplan-Meier (RQ3).
- Assess truck spec impacts on failure risk (RQ4).
- Support risk-informed maintenance with cost-sensitive metrics (RQ5).

## Dataset (1.53GB)
- **Source**: Swedish National Data Service – anonymized time-series from Scania fleet.
- **Features**: 200+ operational sensors/counters (e.g., families 167x, 272x), specs, time-to-event (TTE).
- **Size**: 23k+ vehicles, 1M+ observations; imbalanced (9.6% failures).
- **Details**: Train/val/test CSVs; sensors (170+), specs, TTE; DOI:10.5878/bnh5-ka7
- **Official**: Download from [Swedish National Data Service](https://api.researchdata.se/dataset/2024-34/3/file/zip) (SCANIA Component X: multivariate time-series for PdM).
- **Mirror**: My Google Drive(https://drive.google.com/drive/folders/1Ji7N7gwyQPdgn2pF3kyNLuvJjFcRCSHr?usp=sharing)

## Methods
- **RQ1**: Random Forest feature importance, cost-sensitive classification (SMOTE).
- **RQ2-3**: Survival analysis (Cox PH, Kaplan-Meier), rolling-window features.
- **RQ4**: Stratified Cox, ANOVA/Kruskal-Wallis.
- **RQ5**: Expected cost, Net Benefit vs. reactive baseline (CFN=500, CFP=7-10).

| Metric | Purpose |
|--------|---------|
| AUC, F1, Brier | Model discrimination[web:10] |
| Hazard Ratios | Time-varying risk |
| Cost Savings | PdM vs. reactive |

## Setup & Usage
1. Clone: `git clone https://github.com/omaswi/qm640-scania-componentx-analysis.git`
2. Install: `pip install -r requirements.txt` (pandas, scikit-survival, lifelines, etc.)
3. Run analysis: Jupyter notebooks in `/notebooks/` or `python src/main.py`

**Author**: Odisitse Maswibilili | DBA | Walsh College
