# Large-Scale E-commerce Data Cleaning & Customer Behaviour Analysis

## Overview

This project analyses **42.4 million e-commerce customer events** from October 2019 to explore customer behaviour, product activity, pricing patterns, and data quality.

The main focus was handling a large real-world dataset using **Python and pandas**, followed by behavioural analysis and visualisation using **Matplotlib and Seaborn**.

---

## Dataset

**Source:** REES46 Multi-Category E-commerce Behaviour Dataset

- **42,448,764 rows**
- **3,022,290 users**
- **9,244,421 sessions**
- **166,794 products**
- **9 original columns**
- Events: `view`, `cart`, `purchase`

Only **October 2019** was used for this analysis.

---

## Tools

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- Parquet
- Git / GitHub

---

## Project Workflow

### 1. Data Understanding

Explored dataset structure, data types, event types, users, products, sessions, dates, and price distribution.

### 2. Data Quality Audit

Key issues identified:

- **31.84%** missing category codes
- **14.41%** missing brand values
- **30,220** duplicate-looking records
- **68,673** zero-price events
- **137 products** linked to multiple brands

### 3. Data Cleaning

Cleaning decisions were evidence-based rather than automatically deleting unusual records.

- Missing categories → `uncategorized`
- Missing brands were recovered where reliable
- Remaining missing brands → `unknown`
- Duplicate-looking behavioural events were retained
- Zero-price events were retained for behavioural analysis
- Datatypes were optimised where appropriate

### 4. Feature Engineering

The dataset was expanded from **9 to 19 columns** while preserving all **42,448,764 rows**.

New features included:

- Date
- Day
- Hour
- Day of week
- Weekend indicator
- Time of day
- Department
- Category
- Subcategory
- Price band

---

# Visual Analysis

## Customer Event Distribution

Customer activity was heavily dominated by product views, with **40.8M views** compared with **742,849 purchases**.

![Customer Event Distribution](images/01_event_distribution.png)

---

## Top Departments by Purchases

This analysis identifies the product departments generating the highest number of purchase events.

![Top Departments by Purchases](images/02_department_purchases.png)

---

## Department View-to-Purchase Ratio

This compares purchase activity against product views across departments.

The metric is an **event-based behavioural indicator**, not a true customer conversion rate.

![Department Conversion](images/03_department_conversion.png)

---

## Top Product Categories

Purchase activity was analysed at category level to identify the most frequently purchased product groups.

![Top Categories by Purchases](images/04_category_purchases.png)

---

## Customer Activity by Hour

Hourly behaviour analysis shows how views, carts, and purchases change throughout the day.

![Customer Activity by Hour](images/05_hourly_activity.png)

---

## Weekday vs Weekend Activity

Average daily activity was compared between weekdays and weekends rather than using raw totals.

![Weekday vs Weekend Activity](images/06_weekday_weekend.png)

---

## Price Band Behaviour

Products were divided into price bands based on the distribution of positive prices to compare purchasing behaviour across different price levels.

![Price Band Conversion](images/07_price_band_conversion.png)

---

# Key Findings

- Product browsing dominates customer activity, with **40.8M views** compared with **742K purchases**.
- The dataset contains more than **3 million users** and **9.2 million sessions**.
- Prices are right-skewed, with an average price of approximately **290** compared with a median of approximately **163**.
- Missing category and brand information were the largest data-quality issues.
- Cleaning required judgement rather than automatically removing duplicates or unusual values.
- Feature engineering improved the dataset from **9 to 19 analytical fields** without removing customer events.

---

## Limitations

- Analysis covers only **October 2019**.
- Missing category and brand information limits some product-level analysis.
- View-to-purchase ratios are event-based indicators rather than true customer-level conversion rates.

---

## Project Structure

```text
Multi-Category E-commerce Data Quality & Customer Behaviour Analysis/
│
├── python/
│   ├── 01_data_understanding.ipynb
│   ├── 02_data_quality_audit.ipynb
│   ├── 03_data_cleaning.ipynb
│   ├── 04_data_transformation.ipynb
│   ├── 05_exploratory_analysis.ipynb
│   └── 06_visual_analysis.ipynb
│
├── images/
│   ├── 01_event_distribution.png
│   ├── 02_department_purchases.png
│   ├── 03_department_conversion.png
│   ├── 04_category_purchases.png
│   ├── 05_hourly_activity.png
│   ├── 06_weekday_weekend.png
│   └── 07_price_band_conversion.png
│
└── README.md
```

> The original raw dataset is not included because of its large file size.

---

## What This Project Demonstrates

- Processing **40M+ rows with pandas**
- Data quality auditing
- Evidence-based data cleaning
- Feature engineering
- Large-scale behavioural analysis
- Matplotlib and Seaborn visualisation
- Documenting assumptions and limitations

---

## Conclusion

This project processed more than **42 million e-commerce behavioural events**, transforming raw data into an analysis-ready dataset while preserving potentially valid customer activity.

The project demonstrates an end-to-end workflow covering **data understanding, quality assessment, cleaning, transformation, analysis, and visual communication**.