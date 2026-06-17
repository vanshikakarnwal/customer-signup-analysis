# customer-signup-analysis
End-to-end data quality audit and EDA of SaaS customer sign-up data - Python, Pandas, Matplotlib, Seaborn
# Customer Sign-Up Behaviour & Data Quality Audit

**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn  
**Domain:** SaaS / Business Intelligence  
**Dataset:** 300 customer records, 10 variables (Jan - Oct 2024)

---

## Project Overview

This project analyses customer sign-up data for **Rapid Scale**, a fast-growing SaaS company with tiered subscription plans. The analysis was conducted to support a Monthly Business Review (MBR) by the Business Intelligence team.

The notebook covers a full end-to-end pipeline, from a raw, messy dataset with inconsistencies, missing values, and duplicates, to clean, structured insights ready for business decision-making.

---

## Business Questions Answered

- Which acquisition source brought in the most users?
- Which region shows signs of missing or incomplete data?
- Are older users more or less likely to opt in to marketing?
- Which plan is most commonly selected, and by which age group?
- Which plan's users are most likely to contact support?

---

## Repository Structure

```
├── Data_Analysis_for_Business_Insights.ipynb   # Full analysis notebook
├── customer_signups.csv                         # Primary dataset (300 records)
├── support_tickets.csv                          # Support ticket data
└── README.md
```


---

## Key Steps

**1. Data Quality Audit**
- Identified missing values across all columns (region: 10%, email: 11.3%)
- Detected invalid data — dates stored as text, age stored as "unknown" or "thirty"
- Found and removed duplicate records based on `customer_id` and `email`

**2. Data Cleaning**
- Standardised plan names: `PRO` → `Pro`, `PREMIUM` → `Premium`, `prem` → `Premium`
- Fixed gender casing: `FEMALE` → `Female`, `male` → `Male`
- Replaced invalid markers: `??` → `Unknown`, `Nil` → `No`
- Converted age to numeric and flagged out-of-range values (e.g. age = 206)
- Parsed mixed-format dates using `errors='coerce'`

**3. Exploratory Analysis**
- Sign-ups by source, region, and plan using `.groupby()` and `.value_counts()`
- Marketing opt-in behaviour segmented by gender
- Age distribution: min, max, mean, median

**4. Visualisations**
- Bar chart: Sign-ups by acquisition source
- Horizontal bar chart: Plan distribution
- Grouped bar chart: Marketing opt-in by gender
- Line chart: Monthly sign-up trend (Jan - Oct 2024)

**5. Support Ticket Analysis (Stretch Task)**
- Merged support ticket data onto customer records
- Identified **41 customers** who raised a support ticket within 2 weeks of sign-up
- Summarised support activity by plan and region

---

## Key Findings

- **YouTube and Instagram** are the top acquisition channels
- **Premium** is the most selected plan - strong willingness to pay
- **Marketing opt-in rates are low** across all genders - opt-in messaging needs review
- **Sign-ups were steady** Jan - Oct 2024 with no major seasonal spikes
- **Data quality is a risk** - 10%+ missing rates in region and email fields

---

## How to Run

1. Clone this repository
2. Open `Data_Analysis_for_Business_Insights.ipynb` in Jupyter Notebook or JupyterLab
3. Run all cells top to bottom

**Requirements:** `pandas` `numpy` `matplotlib` `seaborn`

---

*Dataset is fictional and used for educational purposes.*
