<div align="center">

# PROJECT FORESIGHT

### AI-Powered Retail Sales Intelligence Dashboard

*Transforming raw transactional data into strategic retail decisions through machine learning and interactive analytics.*

<br>

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit--Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

<br>

**[Explore the Dashboard](#running-locally)** · **[View Features](#dashboard-features)** · **[Report an Issue](../../issues)** · **[Request a Feature](../../issues)**

</div>

---

## Project Overview

**Project FORESIGHT** is an end-to-end retail analytics system that converts raw e-commerce transaction data into actionable business intelligence. It combines a rigorous data science pipeline — cleaning, feature engineering, segmentation, and forecasting — with a polished, interactive Streamlit dashboard designed for executive decision-making.

Built on the **Online Retail II Dataset**, FORESIGHT simulates a real-world retail intelligence product: the kind of internal tool a data team would ship to help merchandising, marketing, and inventory teams answer one core question — *what should we do next, and why?*

The project is intentionally structured to reflect production-grade data science practice: reproducible notebooks, modular processing scripts, a clean dashboard-ready dataset layer, and a presentation surface that non-technical stakeholders can actually use.

---

## Problem Statement

Retail businesses generate enormous volumes of transactional data — but most of it goes unused beyond basic revenue reporting. Common gaps include:

- No unified view of revenue performance across time, geography, and product categories
- Customer bases treated as homogeneous, when in reality they contain distinct behavioral segments
- Demand planning driven by intuition rather than statistically grounded forecasts
- Inventory decisions made reactively instead of proactively
- Insights trapped in static spreadsheets instead of interactive, explorable tools

**Project FORESIGHT** addresses these gaps by building a complete pipeline — from raw data to a decision-ready dashboard — that surfaces patterns a spreadsheet simply cannot.

---

## Objectives

- Clean and structure a real-world, imperfect retail transaction dataset
- Engineer features that capture customer behavior, product performance, and temporal trends
- Segment customers using unsupervised learning to enable targeted business strategy
- Forecast short-term demand to support planning and procurement decisions
- Translate model outputs into practical inventory recommendations
- Prepare a clean, dashboard-ready dataset layer decoupled from raw data processing
- Deliver findings through a professional, interactive, and exportable dashboard

---

## Dashboard Features

| Feature | Description |
|---|---|
| **Executive KPI Cards** | At-a-glance summary of revenue, orders, customers, and average order value |
| **Interactive Sidebar Filters** | Filter by date range, country, product category, and customer segment |
| **Revenue Trend** | Time-series visualization of revenue with drill-down granularity (daily/weekly/monthly) |
| **Revenue by Country (World Map)** | Choropleth map visualizing geographic revenue distribution |
| **Business Insights** | Auto-generated narrative insights highlighting notable trends and anomalies |
| **Analytics Dashboard** | Deep-dive statistical views: cohort behavior, seasonality, and distribution analysis |
| **Product Performance** | Best/worst performing SKUs, category-level revenue contribution, and return rates |
| **Customer Analysis** | Segment-level breakdown from RFM and clustering models |
| **PDF Export** | One-click export of the current dashboard view for reporting and sharing |
| **Professional Dark Theme** | Custom-themed UI built for extended analyst use and executive presentation |

---

## Machine Learning Workflow

The project follows a linear, auditable pipeline — each stage consumes the previous stage's output and produces a versioned artifact for the next.

```
Raw Transactional Data
        │
        ▼
┌───────────────────────┐
│   1. Data Cleaning     │  → handle missing IDs, cancellations, duplicates, outliers
└───────────┬───────────┘
        ▼
┌───────────────────────┐
│ 2. Exploratory Data    │  → distribution analysis, seasonality, correlation study
│    Analysis (EDA)      │
└───────────┬───────────┘
        ▼
┌───────────────────────┐
│ 3. Feature Engineering │  → RFM metrics, time-based features, product-level features
└───────────┬───────────┘
        ▼
┌───────────────────────┐
│ 4. Customer            │  → K-Means clustering on RFM feature space
│    Segmentation        │
└───────────┬───────────┘
        ▼
┌───────────────────────┐
│ 5. Demand Forecasting  │  → time-series forecasting per category/SKU
└───────────┬───────────┘
        ▼
┌───────────────────────┐
│ 6. Inventory           │  → reorder signals derived from forecast + velocity
│    Recommendation      │
└───────────┬───────────┘
        ▼
┌───────────────────────┐
│ 7. Dashboard Dataset   │  → aggregation & flattening for fast Streamlit rendering
│    Preparation         │
└───────────┬───────────┘
        ▼
┌───────────────────────┐
│ 8. Interactive         │  → Streamlit application layer
│    Streamlit Dashboard │
└───────────────────────┘
```

**Segmentation approach:** Customers are profiled using Recency, Frequency, and Monetary (RFM) metrics, then clustered via K-Means to identify actionable groups such as high-value loyalists, at-risk customers, and one-time buyers.

**Forecasting approach:** Demand is modeled at the category/SKU level using historical revenue and quantity trends, producing short-horizon forecasts that feed directly into the inventory recommendation logic.

---

## Folder Structure

```
project-foresight/
│
├── data/
│   ├── raw/                     # Original Online Retail II dataset
│   ├── interim/                 # Cleaned, intermediate data
│   └── processed/               # Final dashboard-ready datasets
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_exploratory_data_analysis.ipynb
│   ├── 03_feature_engineering.ipynb
│   ├── 04_customer_segmentation.ipynb
│   ├── 05_demand_forecasting.ipynb
│   └── 06_inventory_recommendation.ipynb
│
├── src/
│   ├── data_cleaning.py
│   ├── feature_engineering.py
│   ├── segmentation.py
│   ├── forecasting.py
│   ├── inventory.py
│   └── dashboard_prep.py
│
├── dashboard/
│   ├── app.py                   # Streamlit entry point
│   ├── components/              # KPI cards, charts, filters
│   ├── assets/                  # Theme, logo, custom CSS
│   └── utils/                   # Helper functions for the app layer
│
├── reports/
│   ├── figures/                 # Exported charts and screenshots
│   └── insights_summary.md      # Narrative business insights
│
├── models/                      # Serialized clustering & forecasting models
│
├── tests/                       # Unit tests for pipeline components
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

## Tech Stack Table

| Layer | Technology | Purpose |
|---|---|---|
| Core Language | Python 3.10+ | Primary development language |
| Data Processing | Pandas, NumPy | Cleaning, transformation, aggregation |
| Machine Learning | Scikit-learn | Clustering, feature scaling, forecasting utilities |
| Visualization | Plotly | Interactive charts, world map, trend lines |
| Application Layer | Streamlit | Dashboard framework and UI rendering |
| Data Source | Online Retail II Dataset | Real-world transactional retail data |

---

## Installation

**Prerequisites**

- Python 3.10 or higher
- pip or conda package manager
- Git

**Clone the repository**

```bash
git clone https://github.com/<your-username>/project-foresight.git
cd project-foresight
```

**Create a virtual environment**

```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

**Install dependencies**

```bash
pip install -r requirements.txt
```

---

## Running Locally

**1. Prepare the dataset**

Place the Online Retail II dataset inside `data/raw/`, then run the processing pipeline:

```bash
python src/data_cleaning.py
python src/feature_engineering.py
python src/segmentation.py
python src/forecasting.py
python src/inventory.py
python src/dashboard_prep.py
```

**2. Launch the dashboard**

```bash
streamlit run dashboard/app.py
```

**3. Open in browser**

Navigate to `http://localhost:8501` to explore the live dashboard.

---

## Dashboard Screenshots

<div align="center">

*Executive Overview*

`![Executive KPI Overview](reports/figures/executive_overview.png)`

<br>

*Revenue Trend & World Map*

`![Revenue Trend and World Map](reports/figures/revenue_geography.png)`

<br>

*Customer Segmentation View*

`![Customer Segmentation](reports/figures/customer_segments.png)`

<br>

*Product Performance & Inventory Recommendations*

`![Product Performance](reports/figures/product_performance.png)`

</div>

> Replace the placeholder image paths above with actual exported screenshots in `reports/figures/` once the dashboard is running.

---

## Results

- Consolidated over half a million raw transaction records into a clean, analysis-ready dataset
- Identified distinct customer segments with measurably different purchasing behavior and lifetime value
- Produced category-level demand forecasts to support proactive inventory planning
- Reduced manual reporting effort by replacing static spreadsheets with a live, filterable dashboard
- Delivered an executive-ready reporting surface with one-click PDF export

---

## Business Insights

- A small proportion of customers consistently drives a disproportionate share of total revenue, reinforcing the value of loyalty-focused retention strategy
- Revenue is heavily concentrated in a limited number of geographic markets, highlighting clear expansion opportunities elsewhere
- Certain product categories show strong seasonal spikes, indicating opportunities for pre-emptive stocking ahead of peak periods
- A meaningful segment of customers shows declining recency and frequency, flagging churn risk that can be addressed through targeted re-engagement campaigns
- Fast-moving, high-margin products are frequently under-stocked relative to demand, pointing to inventory allocation inefficiencies

---

## Future Improvements

- Integrate real-time data ingestion via streaming or scheduled ETL pipelines
- Add advanced forecasting models (e.g., Prophet, LSTM) for longer-horizon predictions
- Introduce a recommendation engine for cross-sell and upsell opportunities
- Add role-based authentication for multi-user dashboard access
- Deploy the dashboard to the cloud with CI/CD for continuous delivery
- Incorporate anomaly detection for early fraud or data-quality alerts
- Expand segmentation with behavioral and psychographic features beyond RFM

---

## Learning Outcomes

Building Project FORESIGHT involved practical, end-to-end application of:

- Real-world data cleaning on a messy, inconsistent transactional dataset
- Feature engineering techniques for customer and product-level modeling
- Unsupervised learning for customer segmentation and its business interpretation
- Time-series forecasting fundamentals applied to retail demand
- Translating model outputs into operational business recommendations
- Designing and building a production-style interactive dashboard with Streamlit
- Structuring a data science project for readability, reproducibility, and collaboration

---

## Author

**Your Name**

Data Analyst / Data Scientist passionate about turning data into decisions.

[GitHub](https://github.com/<your-username>) · [LinkedIn](https://linkedin.com/in/<your-username>) · [Portfolio](https://your-portfolio-link.com)

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

<div align="center">

<br>

If you found this project useful, consider giving it a star on GitHub.

</div>
