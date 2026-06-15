# 🇪🇹 Ethiopian Job Market Analysis

> A data-driven exploration of the Ethiopian job market — uncovering in-demand skills, salary trends, and hiring patterns across industries.

![Project Status](https://img.shields.io/badge/Status-Active-brightgreen)
![Tools](https://img.shields.io/badge/Tools-SQL%20%7C%20Excel%20%7C%20Power%20BI-blue)
![Data Source](https://img.shields.io/badge/Data-Ethiojobs.net-orange)

---

## 📌 Project Overview

The Ethiopian job market is growing rapidly in tech, finance, and NGO sectors — yet there is little publicly available analysis of what employers actually want. This project collects, cleans, and analyzes real job postings to answer key questions that job seekers and career advisors need.

**Who is this for?**
- Job seekers wanting to know which skills to prioritize
- Students choosing between career paths
- Recruiters and HR professionals understanding market trends

---

## ❓ Key Business Questions

1. Which job skills are most in demand in Ethiopia right now?
2. Which industries are hiring the most?
3. What is the salary range across different roles and sectors?
4. Which cities have the highest number of job postings?
5. What education level do most employers require?
6. How has demand for tech skills changed over time?

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Excel** | Data collection, cleaning, and pivot dashboards |
| **SQL (PostgreSQL)** | Data querying and analysis |
| **Power BI** | Interactive dashboard and visualization |
| **Python (pandas)** | Data wrangling and automation (optional extension) |

---

## 📁 Dataset

| Detail | Info |
|--------|------|
| **Source** | Manually collected from [Ethiojobs.net](https://ethiojobs.net) |
| **Collection Period** | June 2025 – July 2025 |
| **Total Records** | ~200 job postings |
| **Fields Collected** | Job Title, Company, Industry, Location, Salary (if listed), Required Skills, Education Level, Experience Required, Posting Date |

> ⚠️ Note: All data was collected manually from publicly available job listings. No scraping tools were used. Data is used for educational and analytical purposes only.

---

## 📂 Repository Structure

```
ethiopian-job-market-analysis/
│
├── README.md                  ← You are here
│
├── data/
│   ├── raw_jobs_data.xlsx     ← Original collected data
│   └── cleaned_jobs_data.csv  ← Cleaned version for analysis
│
├── sql/
│   ├── create_tables.sql      ← Database schema
│   ├── data_cleaning.sql      ← Cleaning queries
│   └── analysis_queries.sql   ← Key analysis queries
│
├── dashboard/
│   └── ethiopia_jobs.pbix     ← Power BI dashboard file
│
└── images/
    ├── dashboard_overview.png
    ├── top_skills_chart.png
    └── salary_by_sector.png
```

---

## 🔍 SQL Analysis Highlights

### Top 10 Most In-Demand Skills
```sql
SELECT
    skill,
    COUNT(*) AS job_count,
    ROUND(COUNT(*) * 100.0 / (SELECT COUNT(*) FROM jobs), 2) AS percentage
FROM job_skills
GROUP BY skill
ORDER BY job_count DESC
LIMIT 10;
```

### Average Salary by Industry
```sql
SELECT
    industry,
    COUNT(*) AS total_jobs,
    ROUND(AVG(salary_etb), 0) AS avg_salary_etb,
    MIN(salary_etb) AS min_salary,
    MAX(salary_etb) AS max_salary
FROM jobs
WHERE salary_etb IS NOT NULL
GROUP BY industry
ORDER BY avg_salary_etb DESC;
```

### Jobs by City
```sql
SELECT
    city,
    COUNT(*) AS job_count
FROM jobs
GROUP BY city
ORDER BY job_count DESC;
```

---

## 📊 Key Findings

> *(To be updated after analysis is complete)*

- 🥇 **Most In-Demand Skill:** SQL and Microsoft Excel appear in over 60% of data-related job postings
- 🏙️ **Top Hiring City:** Addis Ababa accounts for ~80% of all postings
- 💼 **Top Hiring Sectors:** NGO/International Organizations, Banking & Finance, Tech
- 🎓 **Education:** 75% of postings require a Bachelor's degree minimum
- 💰 **Salary Range:** Entry-level data roles range from 15,000–35,000 ETB/month

---

## 🖼️ Dashboard Preview

> *(Add screenshot after Power BI dashboard is complete)*

```
📸 Screenshot coming soon — dashboard in progress
```

---

## 🚀 How to Reproduce This Project

### Step 1 — Set Up the Database
```sql
-- Run this file first
sql/create_tables.sql
```

### Step 2 — Load the Data
Import `data/cleaned_jobs_data.csv` into your SQL database or open directly in Excel.

### Step 3 — Run the Analysis
```sql
-- Run queries in order
sql/data_cleaning.sql
sql/analysis_queries.sql
```

### Step 4 — View the Dashboard
Open `dashboard/ethiopia_jobs.pbix` in Power BI Desktop (free download from Microsoft).

---

## 💡 Lessons Learned

- Data collection from job boards requires careful standardization — job titles vary widely (e.g., "Data Analyst" vs "Analytics Specialist" vs "Reporting Analyst")
- Salary data is often missing from Ethiopian job postings, making salary analysis challenging
- Cleaning free-text skills fields (e.g., "MS Office, Excel, Word") requires consistent parsing logic

---

## 🔮 Future Improvements

- [ ] Automate data collection with Python web scraping
- [ ] Expand dataset to 500+ job postings
- [ ] Add time-series analysis to track skill demand monthly
- [ ] Compare Ethiopian market with other East African countries (Kenya, Rwanda)
- [ ] Deploy interactive dashboard on Power BI Service (public link)

---

## 👤 About the Author

**Abdulhakim Mesele**
Data Analyst | SQL • Excel • Power BI • HTML/CSS
🎓 ALX Data Analytics Certificate | BSc Computer Science
🌍 Addis Ababa, Ethiopia | Open to Remote Roles

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://linkedin.com/in/your-link)
[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-green)](https://abdulhakimmesele.github.io/abdulhakim.github.io/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black)](https://github.com/hakihaki)

---

## 📄 License

This project is open source under the [MIT License](LICENSE).

---

⭐ *If you found this project useful, please consider giving it a star!*
