<div align="center">

# PROJECT FORESIGHT

### Retail Sales Analytics Dashboard

*An exploratory data science project that turns raw e-commerce transaction data into an interactive Streamlit dashboard.*

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

**[Live Demo](https://project-foresight-uk4v.onrender.com/)** · **[GitHub Repository](https://github.com/Yashr4635/Project_FORESIGHT)**

</div>

---

## Live Demo

**[project-foresight-uk4v.onrender.com](https://project-foresight-uk4v.onrender.com/)**

> ⚠️ Hosted on Render's free tier — the app sleeps after inactivity, so the first load after idle time can take 30–60 seconds to spin up. If you're sharing this link with a recruiter, mention that upfront so a slow first load doesn't read as broken.

---

## What this is

Project FORESIGHT analyzes retail transaction data through a series of Jupyter notebooks — cleaning, EDA, feature engineering, customer segmentation, demand forecasting, and inventory recommendation — and presents the output through a Streamlit dashboard deployed on Render.

**Read this before you present it in an interview:** the analysis logic currently lives in the notebooks, not in reusable Python modules. `src/` exists as a folder but has no scripts in it yet. If you're asked "is this pipeline modular / production-style," the honest answer right now is no — it's notebook-driven analysis feeding a dashboard app. That's a completely normal and defensible stage for a project like this. It is not a "production ML pipeline," and this README won't call it one.

---

## Repository Structure

This is the actual structure — nothing here is invented:

```
Project_FORESIGHT/
├── app/
│   └── app.py                   # Streamlit dashboard entry point
├── data/                        # Raw and processed datasets
├── models/                      # (currently empty — no serialized models saved yet)
├── notebooks/
│   ├── 01_Data_Cleaning.ipynb
│   ├── 02_EDA.ipynb
│   ├── 03_Feature_Engineering.ipynb
│   ├── 04_Customer_Segmentation.ipynb
│   ├── 05_Demand_Forecasting.ipynb
│   ├── 06_Inventory_Recommendation.ipynb
│   └── 07_Dashboard_Preparation.ipynb
├── reports/                      # (currently empty)
├── screenshots/
│   ├── dashboard.png
│   ├── analytics.png
│   ├── map.png
│   └── insights.png
├── src/                          # (currently empty — pipeline not yet modularized)
├── requirements.txt
└── README.md
```

> ⚠️ **TODO for you:** `models/`, `reports/`, and `src/` are empty. Either populate them (export trained models with `joblib`/`pickle`, save summary figures, move reusable logic out of the notebooks into `.py` modules) or don't reference them in future README edits. An empty folder in a portfolio repo reads as unfinished work — better to have fewer folders that are all real than a folder tree that looks bigger than the project.

---

## Pipeline (as it actually exists — notebook by notebook)

```
01_Data_Cleaning        → handle missing IDs, cancellations, duplicates
02_EDA                  → distribution, trend, and correlation analysis
03_Feature_Engineering  → RFM and time-based features
04_Customer_Segmentation→ K-Means clustering on RFM features
05_Demand_Forecasting   → category/SKU-level demand forecasting
06_Inventory_Recommendation → reorder signals from forecast output
07_Dashboard_Preparation→ aggregation for the Streamlit app
        │
        ▼
   app/app.py (Streamlit) → deployed on Render
```

---

## Dashboard

Screenshots below are the actual files from `screenshots/` — I'm not using placeholder image paths since you have real ones.

<div align="center">

**Executive Overview**
![Dashboard](screenshots/dashboard.png)

**Analytics View**
![Analytics](screenshots/analytics.png)

**Geographic Revenue**
![Map](screenshots/map.png)

**Business Insights**
![Insights](screenshots/insights.png)

</div>

---

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3.10+ |
| Data processing | Pandas, NumPy |
| Machine learning | Scikit-learn (K-Means) |
| Visualization | Plotly |
| Dashboard | Streamlit |
| Analysis environment | Jupyter Notebook |
| Deployment | Render |

> ⚠️ **TODO for you:** paste the actual contents of `requirements.txt` here (or just keep the table in sync with it). I'm not listing OpenPyXL, Git, or Railway as tech stack items — Render is the confirmed deployment target, not Railway, based on the live link you gave me. If you also deployed to Railway at some point, tell me and I'll add it back; otherwise leave it out.

---

## Running Locally

```bash
git clone https://github.com/Yashr4635/Project_FORESIGHT.git
cd Project_FORESIGHT

python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

pip install -r requirements.txt

streamlit run app/app.py
```

Open `http://localhost:8501` in your browser.

> ⚠️ Note: you mentioned recently fixing a numpy/pandas ABI mismatch causing a segfault crash loop. If that's fully resolved, ignore this. If it's intermittent, say so here rather than shipping install instructions that might crash for someone else's environment — a recruiter hitting a segfault on `pip install` is a worse first impression than an honest known-issues note.

---

## What's real vs. what needs work

Being direct about project status, because vague completeness claims fall apart under questioning:

**Done:**
- Data cleaning notebook
- EDA notebook
- Feature engineering (RFM)
- Streamlit dashboard app connected to processed data
- Customer segmentation via K-Means (notebook-based)
- Demand forecasting notebook
- Inventory recommendation notebook
- Live deployment on Render

**Not done yet — don't claim otherwise:**
- No modularized `src/` pipeline (notebooks aren't refactored into reusable scripts)
- No saved/serialized models in `models/`
- No exported reports in `reports/`

---

## Author

**D.S. Yashaswi**
[GitHub](https://github.com/Yashr4635)

---

## License

MIT
