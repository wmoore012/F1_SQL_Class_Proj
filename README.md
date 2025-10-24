# 🏎️ F1 Racer Efficiency: A Data-Driven Analytics Platform

## 👥 Team Members

**Troy Benner** | **Kiefer Jenny** | **Will Moore**

*MS in Data Science and Business Analytics*
*UNC Charlotte (UNCC)*

---

## 🎯 Project Overview

**What makes a Formula 1 driver truly efficient?** Our team built a comprehensive analytics platform to answer this question using 70+ years of F1 racing data. This project showcases advanced SQL database design, complex multi-table queries, and interactive data visualizations—all centered around measuring driver performance, pit crew efficiency, and racing strategy.

**Dataset:** [Formula 1 World Championship (1950-2024)](https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020) by Rohan Rao
**Purpose:** Portfolio project demonstrating SQL proficiency, database design, and data analysis skills for potential employers

---

## 📖 The Story: From Database Design to Interactive Insights

### 🏁 Phase 1: Use Case & Database Design

Our team identified a real-world need: **racing analysts, F1 enthusiasts, and betting platforms** need detailed driver performance metrics to understand efficiency trends. We designed a relational database with 10 interconnected tables to answer questions like:

- Which countries produce the most championship-winning drivers?
- How do lap times correlate with final race positions?
- Which drivers have the most efficient pit crews?

**Database Architecture:**
- 10 tables with proper foreign key relationships
- Complex join patterns across `drivers`, `results`, `races`, `lap_times`, `pit_stops`, `qualifying`, and more
- Handled 70+ years of evolving F1 data standards (e.g., fastest lap data only available post-2004)

### 🔍 Phase 2: SQL Analysis & Data Exploration

We performed comprehensive data analysis using advanced SQL techniques:

**Key Analyses:**
1. **🌍 Nationality Wins** — Multi-table joins to aggregate race victories by country
2. **⏱️ Lap Time Performance** — CTEs and complex joins correlating lap speeds with race outcomes
3. **🔧 Pit Stop Efficiency** — Aggregation and filtering to rank the fastest pit crews

**SQL Skills Demonstrated:**
- INNER/LEFT JOINs across 7+ tables
- Common Table Expressions (CTEs) for complex queries
- GROUP BY with COUNT, AVG, SUM aggregations
- NULL handling for incomplete historical data
- Data modification (INSERT, UPDATE, DELETE) with safe mode handling
- Time-based calculations and data type conversions

### 🐍 Phase 3: Python Translation & Visualization

This repository translates our original MySQL queries into **Pandas** operations with **Plotly** visualizations, making our findings:
- ✅ Interactive and explorable
- ✅ Portfolio-ready for employers
- ✅ Reproducible with sample or full datasets

---

## 📊 Dataset Information

### Current Setup: Mini Sample Dataset

The repository includes a **mini sample dataset** (`data/f1/`) with 4 drivers and 2 races for demonstration purposes. The notebook runs immediately without additional downloads.

### Upgrading to Full Historical Data

To analyze complete F1 history (1950-2020+):

1. **Download** the [Kaggle Formula 1 World Championship dataset](https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020) by Rohan Rao
2. **Extract** these CSV files:
   - `drivers.csv`
   - `results.csv`
   - `races.csv`
   - `driver_standings.csv`
   - `lap_times.csv`
   - `pit_stops.csv`
   - `qualifying.csv`
3. **Replace** the files in `data/f1/` with the full dataset (keeping the same filenames)
4. **Run** the notebook — no code changes needed!

**Alternative:** Set an environment variable to point to your data location:
```bash
export F1_DATA_DIR="/path/to/your/kaggle/f1/data"
```

---

## 🚀 Quick Start

### Option 1: Run the Jupyter Notebook (Recommended)

```bash
# Navigate to project directory
cd "F1 Racing SQL Project"

# (Optional) Set custom data path
export F1_DATA_DIR="/path/to/full/kaggle/data"

# Launch Jupyter
jupyter notebook f1_sql_annotated_and_visuals.ipynb
```

### Option 2: View SQL Queries

Open `F1 Racing.sql` in your preferred SQL client (DataGrip, DBeaver, MySQL Workbench, etc.) to see the original SQL queries.

---

## 📁 Project Structure

```
F1 Racing SQL Project/
├── f1_sql_annotated_and_visuals.ipynb  # Main analysis notebook
├── F1 Racing.sql                        # Original SQL queries
├── data/f1/                             # Sample F1 dataset (7 CSV files)
│   ├── drivers.csv
│   ├── results.csv
│   ├── races.csv
│   ├── driver_standings.csv
│   ├── lap_times.csv
│   ├── pit_stops.csv
│   └── qualifying.csv
├── FinalProject_Deliverable_4(Group5).docx  # Original project documentation
├── F1 Racer Efficiency.pptx             # Project presentation
├── LICENSE                              # MIT License
└── README.md                            # This file
```

---

## 🎯 SQL Skills Demonstrated

| Skill | Example in Project |
|-------|-------------------|
| **INNER JOIN** | `drivers → results` for nationality wins |
| **LEFT JOIN** | `results → lap_times` to handle DNFs |
| **GROUP BY + Aggregation** | COUNT wins per nationality, AVG lap times |
| **Common Table Expressions (CTEs)** | Calculate per-driver averages before joining |
| **Filtering (WHERE/HAVING)** | Drivers with ≥5 pit stops, specific races |
| **Sorting (ORDER BY)** | Rank by fastest times, most wins |
| **NULL Handling** | DNF positions, missing fastest lap data |
| **Data Type Conversions** | Time strings → milliseconds |

---

## 📈 Sample Visualizations

The notebook generates interactive Plotly charts including:

- **Bar Chart:** Total wins by driver nationality
- **Scatter Plot:** Average lap time vs finish position correlation
- **Horizontal Bar Charts:** Top 20 fastest pit stop crews, total stops per driver

---

## 🔧 Technical Stack

- **SQL:** MySQL (original queries)
- **Python:** pandas, plotly, pydantic
- **Data Source:** Kaggle Formula 1 World Championship dataset
- **Notebook:** Jupyter with Python 3.11+

---

## 📝 License

This project is open-sourced under the MIT License. See `LICENSE` for details.

---

## 🏆 Key Findings

### Finding 1: European Dominance in F1 🇬🇧🇩🇪

**Britain and Germany lead the world in F1 championship wins**, with Brazil and France following. Surprisingly, **the United States has ZERO championship wins** in our dataset, despite being a powerhouse in other motorsports (NASCAR) and international athletics (Olympics). This reveals F1's deep European roots and the steep barriers to entry for new racing nations.

### Finding 2: Speed Matters, But Strategy Wins 🏁

Our analysis of the **2012 Malaysian Grand Prix** revealed:
- Fastest average lap time ≠ guaranteed victory
- Drivers who DNF (Did Not Finish) can still place in top 5 after points adjustments
- **Negative correlation exists**: faster lap times generally lead to better finishes, but outliers show strategic pit stops and tire management matter

### Finding 3: Pit Crew Efficiency Separates Legends from the Rest ⚡

**Top performers:**
- **Mark Webber**: 22.43s average pit stop (fastest)
- **Michael Schumacher** & **Nick Heidfeld**: Sub-23s averages

**Consistency under pressure:**
- **Lewis Hamilton** & **Sebastian Vettel**: 400+ pit stops each, yet maintained <24s averages
- High-volume drivers (Alonso, Räikkönen, Button) show refined pit crew coordination over time

**The insight:** Elite drivers benefit from elite pit crews. Milliseconds saved in the pit lane translate to championship points on the track.

---

## 🤝 About This Project

This project was developed as part of a **graduate-level database course at UNC Charlotte**. It demonstrates real-world SQL and data analysis skills applicable to:

- 📊 **Data Analyst roles** — Complex SQL queries, data cleaning, visualization
- 🏎️ **Sports Analytics** — Performance metrics, efficiency analysis, predictive insights
- 💼 **Business Intelligence** — Translating data into actionable insights
- 🐍 **Data Science** — SQL-to-Python workflows, statistical analysis, storytelling with data

### Team Members

**Troy Benner** | **Kiefer Jenny** | **Will Moore**
*MS in Data Science and Business Analytics, UNC Charlotte*

**Contact:** Available for data analyst/scientist opportunities. See our portfolios for more projects!
