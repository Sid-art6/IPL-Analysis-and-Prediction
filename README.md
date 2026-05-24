# 🏏 IPL Analytics

**From Descriptive Insights to Predictive Strategy: A Two-Phase Analysis of 18 Seasons of IPL Cricket**

🚀 **[Live Dashboard →](https://ipl-analysis-and-prediction-yusttzsxkgccxppkg49sx4.streamlit.app/)**

---

## The Journey

| Phase | Question | Method | Key Finding |
|-------|----------|--------|-------------|
| [**Phase_1**](https://github.com/Sid-art6/IPL-Analysis-and-Prediction/tree/main/Phase_1) | How has IPL batting evolved over 18 seasons? | Descriptive analytics | Aggression doubled (sixes: 9→18/match) but dismissals stayed flat at ~12 — the "Free Lunch" |
| [**Phase_2**](https://github.com/Sid-art6/IPL-Analysis-and-Prediction/tree/main/Phase_2) | Is the aggression free lunch real? When should teams attack vs defend? | Predictive modeling (Random Forest Classifier) | Aggression helps in death overs (+3.5%) but **hurts** in the powerplay (-10.9%) |

### The Answer

> **Survive early. Attack late.**

---

## Dataset

- **Source:** IPL ball-by-ball data (2008–2025) from [Cricsheet](https://cricsheet.org/)
- **Deliveries:** 278,205 rows — every ball bowled across 18 IPL seasons
- **Matches:** 1,169 rows — match-level metadata (teams, venue, toss, result)
- **Seasons:** 2008–2025 (18 seasons)
- **Key columns used:**

| Column | Description |
|--------|-------------|
| `match_id` | Unique match identifier |
| `innings` | Innings number (1 or 2) |
| `over` | Over number (0–19) |
| `ball` | Ball number within the over |
| `batsman_runs` | Runs scored by the batsman on this delivery |
| `total_runs` | Total runs including extras |
| `is_wicket` | Whether a wicket fell (0 or 1) |
| `batting_team` | Team batting |
| `bowling_team` | Team bowling |

---

## Phase_1: From Dots to Damage

**Question:** How has IPL batting changed over 18 seasons?

**Findings:**
- Sixes per match nearly doubled (9 → 18)
- Dot ball percentage dropped significantly
- Boundary rates surged across all phases
- Dismissals per match stayed flat at ~12
- Aggression Index (Boundary% + Six% − Dot%) increased steadily

📁 [View Phase_1 →](https://github.com/Sid-art6/IPL-Analysis-and-Prediction/tree/main/Phase_1)

---

## Phase_2: When Should IPL Teams Attack?

**Question:** Given a specific chase situation, should a team attack or defend?

**Model:** Random Forest Classifier (300 trees, 10 engineered features, 78.5% accuracy)

**Key Findings:**
- **rr_gap** (pressure metric) drives 44% of prediction importance
- Death overs + behind → boundaries help (+3.5%) → **Attack**
- Powerplay + behind → boundaries hurt (-10.9%) → **Defend**
- Precision: 81.1% — when the model says "attack," it's right 81/100 times
- The model makes 1.73× more safe mistakes than dangerous ones

📁 [View Phase_2 →](https://github.com/Sid-art6/IPL-Analysis-and-Prediction/tree/main/Phase_2)

🚀 [Try the Live Dashboard →](https://ipl-analysis-and-prediction-yusttzsxkgccxppkg49sx4.streamlit.app/)

---

## Tech Stack

- **Languages:** Python
- **Analysis:** pandas, NumPy, matplotlib, seaborn
- **Modeling:** scikit-learn (Random Forest), XGBoost
- **Dashboard:** Streamlit, Plotly
- **AI Tools:** Claude Opus 4 (code development)

---

## Project Structure

```
IPL Analysis/
├── README.md                    ← You are here
├── Phase_1/
│   ├── IPL_Analysis.ipynb       ← Phase_1 analysis notebook
│   ├── README.md                ← Phase_1 documentation
│   └── assets/                  ← 12 visualization plots
└── Phase_2/
    ├── Phase_2.ipynb            ← Phase_2 modeling notebook
    ├── README.md                ← Phase_2 documentation
    ├── app.py                   ← Streamlit dashboard
    ├── ipl_chase_model.pkl      ← Trained Random Forest model
    ├── requirements.txt         ← Python dependencies
    ├── IPL_Presentation.pptx    ← Final presentation
    └── assets/                  ← 9 analysis plots
```