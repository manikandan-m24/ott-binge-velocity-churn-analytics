# OTT Content Binge Velocity & Post-Finale Churn Analytics 🎬📊

An end-to-end Python analytics project modeling subscriber viewing telemetry to quantify the relationship between **Binge Velocity** (episodes consumed per day) and **Post-Finale Churn** across streaming platforms.

![Executive Dashboard](Screenshot%202026-11-02%20234447.png)

## 📌 Executive Summary
In subscription video-on-demand (SVOD), retaining subscribers after they finish a major series is a significant retention challenge. This project models 1,000 subscriber lifecycles across 7,810 playback sessions to analyze whether fast-paced viewers present higher churn risk once a season concludes.

### Key Findings
* **Churn Escalation:** While the overall platform churn baseline is **31.40%**, viewers completing shows at high velocity (Q3/Q4) experience post-finale churn rates reaching **49.69%**.
* **Rapid Consumption Cliff:** Top-tier bingers (Q4) consume **~2.97 episodes/day**, finishing full seasons in roughly **3 days**, creating an immediate 14-day re-engagement window.
* **Targeted Intervention:** Exported **83 active at-risk subscribers** who completed series rapidly to trigger personalized content recommendations before churn occurs.

## 🛠️ Tech Stack & Methodology
* **Language & Environment:** Python, Google Colab / Jupyter Notebook
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn
* **Data Modeling:** Star Schema design (`Fact_Stream`, `Dim_User`, `Dim_Content`)
* **Feature Engineering:**
  * `Days-to-Finish` (DTC): Total calendar days from first episode to season finale
  * `Binge Velocity`: Total episodes watched divided by Days-to-Finish
* **Segmentation:** Quantile-based speed clustering (`Q1 (Slowest)` to `Q4 (Extreme Binge)`) via `pd.qcut`

## 📊 Speed Quantile vs. Churn Breakdown
| Viewer Speed Cohort | Total Viewers | Avg Velocity (Ep/Day) | Median Days to Finish | Churn Rate (%) |
| :--- | :---: | :---: | :---: | :---: |
| **Q1 (Slowest)** | 167 | 0.19 | 41.7 | 42.51% |
| **Q2 (Moderate)** | 153 | 0.41 | 18.1 | 42.48% |
| **Q3 (Fast)** | 161 | 0.82 | 9.1 | **49.69%** |
| **Q4 (Extreme Binge)** | 159 | 2.97 | 3.0 | **47.80%** |

---

## 📁 Repository Structure
