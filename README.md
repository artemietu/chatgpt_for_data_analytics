# ChatGPT for Data Analytics

## Project Overview

A no‑code, reproducible walkthrough showing how to use ChatGPT to explore a real dataset, clean it, visualise it, and build a simple prediction model — **entirely through prompts**, no local code was executed. This project uses ChatGPT 5 (GPT-5 Thinking).

---

## Repository Structure

```
chatgpt_for_data_analytics/
│
├── data/
│   └── archive.zip                 # raw dataset (contains gsearch_jobs.csv)
├── images/
│   ├── step_3/                     # EDA visuals
│   ├── step_5/                     # distribution + platform salary visuals
│   └── step_6/                     # titles/locations salary visuals
├── project.md                      # step‑by‑step transcript + outputs
└── README.md
```

---

## Dataset Overview

The data arrived in a compressed file, **`data/archive.zip`**, which contains **`gsearch_jobs.csv`** — job postings for data‑related roles scraped from Google Jobs. Each row is a listing with fields such as:
- `job_title`
- `company_name`
- `location`
- source platform (e.g., LinkedIn, Indeed)
- free‑text `description` and metadata (`posted_at`, `schedule_type`, etc.)
- multiple salary signals (`salary_yearly`, `salary_hourly`, `salary_standardized`, ranges)

---

## What This Project Demonstrates

1) **Data and Setup** — unpack `archive.zip`, inspect schema, and document columns.  
2) **Descriptive Statistics** — per‑column summaries (numeric + non‑numeric).  
3) **Exploratory Data Analysis (EDA)** — titles, companies, locations, sources.  
4) **Data Cleaning** — trim leading spaces in `location` (e.g., “␣Oklahoma City, OK” → “Oklahoma City, OK”), with an evidence table.  
5) **Visualising Salary Data** — Distribution of `salary_yearly`, top 10 job platforms by average yearly salary, and top 10 most common platforms with yearly salary — average yearly salary  
6) **Predicting Yearly Salary:**
- Context Visuals: top 10 most common job Titles — average yearly salary and top 10 most Common Locations (cleaned) — average yearly salary
- Model Suggestion And Selection: **Random Forest** on one‑hot encoded `title`, `job_platform`, `location_clean` → target `salary_yearly`
- Why Random Forest
- Accuracy (RMSE Band)
- Single Prediction

---

## Notes

- This is a **no‑code** case study. Everything was produced by instructing ChatGPT.
- The model is intentionally simple (Random Forest) to keep the focus on the workflow, not hyper‑tuning.
- Salary predictions are indicative; real‑world use should include richer features (seniority parsing, state/region normalisation, company effects, posting freshness).

---

## Author

Artemie Țurcanu — Data Analyst