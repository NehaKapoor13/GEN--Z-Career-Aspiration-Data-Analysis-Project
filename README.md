# GEN--Z-Career-Aspiration-Data-Analysis-Project
# 🎯 Gen-Z Career Aspirations — Data Analysis Project

> **Internship Project** | Tools: SQL · Excel · Power BI · Python (EDA) | Dataset: ~3,900+ Gen-Z respondents

---

## 📌 Project Overview

This end-to-end data analysis project explores the **career aspirations, work environment preferences, salary expectations, and values of Generation Z** (born 1997–2012) using survey data collected via Google Forms.

The project covers the full data pipeline:
- Survey-based data collection
- Exploratory Data Analysis (EDA) in Excel
- SQL-based querying and insights extraction
- Dashboard creation (Power BI)
- Presentation of findings

---

## 📂 Repository Structure

```
📁 gen-z-career-aspirations/
│
├── 📄 README.md
├── 📊 Career_Aspirations_EDA.xlsx        # Raw dataset + EDA workbook
├── 📝 analysis_in_sql_report.docx        # SQL queries + result tables + insights
├── 📄 sql-analysis_workstandard.pdf      # SQL query documentation
├── 📊 Career_aspirations.pptx            # Final presentation deck
└── 📁 assets/                            # Dashboard screenshots (add yours here)
```

---

## ❓ Business Questions Answered

| # | Question | Method |
|---|----------|--------|
| 1 | What industries are Gen-Z most interested in? | SQL `GROUP BY` + `COUNT` + `ORDER BY DESC` |
| 2 | What factors most influence their career choices? | SQL frequency analysis on `influence_factors` |
| 3 | What is the preferred work environment? | SQL aggregation on `working_environment` |
| 4 | How do salary expectations impact career choices? | SQL `GROUP BY` on `salary for mid careers` |
| 5 | What role does social impact play in career decisions? | SQL `CASE WHEN` bucketing on social impact score |

---

## 🔍 Key Findings

### 1. Career Aspirations
- **Design & Creative Strategy** dominates with **2,042 responses** — far ahead of all other categories
- **Business Operations** (753) and **Teaching** (492) follow
- AI/Data Analytics and Freelancing are gaining traction — signals a shift toward independent, tech-driven careers
- BPO and Manufacturing show low interest — awareness or resource gap

### 2. Influencing Factors
| Rank | Factor | Count |
|------|--------|-------|
| 1 | My Parents | 1,345 |
| 2 | World changers / inspiring leaders | 864 |
| 3 | Successful career influencers | 665 |
| 4 | People from circle (non-family) | 571 |
| 5 | Social Media (LinkedIn) | 335 |
| Last | Movies | 14 |

> **Insight:** Family remains the strongest career influence. Social media is growing, especially LinkedIn. Films have minimal impact.

### 3. Work Environment Preferences
| Preference | Count |
|------------|-------|
| Hybrid (15+ days/month in office) | 1,090 |
| Fully Remote (with travel flexibility) | 1,074 |
| Every Day Office | 812 |
| Hybrid (< 3 days/month in office) | 576 |
| Fully Remote (no office option) | 200 |

> **Insight:** Hybrid work dominates. Traditional full-time office is losing appeal. Gen-Z wants flexibility, not isolation.

### 4. Salary Expectations (Mid-Career)
| Range | Count |
|-------|-------|
| > 151k | 884 (highest demand) |
| 71k–90k | 717 |
| 91k–110k | 712 |
| 30k–50k | 168 (lowest demand) |

> **Insight:** Most Gen-Z expect high mid-career salaries. Very few accept entry-level ranges — indicating awareness of skill-based pay inflation.

### 5. Social Impact at Work
| Category | Count |
|----------|-------|
| More Impact (scores 7–10) | 1,300 |
| Partially Impact (scores 4–6) | 1,564 |
| Less Impact (scores 1–3) | 1,033 |

> **Insight:** Most Gen-Z care about working for socially responsible companies. "Partially Impact" is the biggest group — they weigh purpose but don't make it non-negotiable.

---

## 🛠️ Tech Stack

| Tool | Usage |
|------|-------|
| **MySQL / SQL** | Data querying, aggregation, CASE WHEN logic |
| **Microsoft Excel** | EDA, pivot tables, data cleaning |
| **Power BI** | Interactive dashboards |
| **Google Forms** | Data collection (survey) |
| **PowerPoint** | Final presentation |

---

## 💻 Sample SQL Queries

### Top Career Aspirations
```sql
SELECT `Aspirational job`, COUNT(`Aspirational job`) AS count
FROM `genz`.`careerdata`
GROUP BY `Aspirational job`
ORDER BY COUNT(`Aspirational job`) DESC;
```

### Social Impact Bucketing
```sql
SELECT
  CASE
    WHEN `No social impact` IN (1, 2, 3) THEN 'Less Impact'
    WHEN `No social impact` IN (4, 5, 6) THEN 'Partially Impact'
    WHEN `No social impact` IN (7, 8, 9, 10) THEN 'More Impact'
  END AS Impact_Category,
  COUNT(*) AS Total_Count
FROM `genz`.`careerdata`
GROUP BY Impact_Category;
```

### Salary Distribution
```sql
SELECT `salary for mid careers`, COUNT(`salary for mid careers`) AS total
FROM `genz`.`careerdata`
GROUP BY `salary for mid careers`
ORDER BY COUNT(`salary for mid careers`) DESC;
```

---

## 📊 Dataset Overview

- **Source:** Google Forms survey
- **Primary country:** India (~95% respondents)
- **Other countries:** USA, Pakistan, Malaysia
- **Total records:** ~3,900+ rows
- **Key columns:** `Aspirational job`, `influence factors`, `working environment`, `salary for mid careers`, `No social impact`, `Gender`, `Country`, `Zip Code`

---

## 📈 Dashboard Highlights

The Power BI dashboard covers:
- Manager aspiration preferences
- Mission alignment analysis
- Salary range distributions
- Work environment breakdown
- Influencing factor comparisons


---

## 🚀 How to Run / Explore

1. Clone this repository
   ```bash
   git clone https://github.com/yourusername/gen-z-career-aspirations.git
   ```
2. Open `Career_Aspirations_EDA.xlsx` in Excel for raw data exploration
3. Run the SQL queries in `analysis_in_sql_report.docx` on MySQL using the `genz.careerdata` table
4. Open `Career_aspirations.pptx` for the full presentation

---

## 🌱 What I Learned

- Writing aggregation, filtering, and CASE WHEN queries in **MySQL**
- Exploratory Data Analysis workflows in **Excel**
- Translating raw survey data into **business insights**
- Building storytelling dashboards in **Power BI**
- Structuring a complete end-to-end data project from collection to presentation

---

## 🙋‍♂️ About Me

**Neha** — Data Analyst | Passionate about turning data into decisions.

📍 Doha, Qatar | 🔗 [LinkedIn](https://linkedin.com/in/yourprofile) | 📧 nehakapoor213001@gmail.com

---

> *This project was completed as part of my data analytics internship. All data is survey-based and anonymized.*
