# 💻 Laptop Sales Dataset — Excel Cleaning & Standardization

This project focuses on cleaning and standardizing a laptop sales dataset in Microsoft Excel. The data includes product names, specifications, pricing, ratings, operating systems, and more. The goal is to transform raw, messy product listing data into clean, structured, and analysis-ready information.

---

## 📄 Dataset Description

- **Source**: Web-scraped listings of laptops (e.g., from 91mobiles)
- **Format**: Excel spreadsheet with multiple columns containing mixed types, inconsistent formats, and some missing values
- **Rows**: Each row represents a unique laptop model

### 🔑 Key Columns
- `name`: Product title
- `price`: Selling price (numeric)
- `storage`: RAM + SSD specs in text form
- `processor`: CPU details
- `system_name` / `windows`: OS-related columns
- `rating_100`, `released`, `spec_score`, `display`, `img`

---

## 🎯 Objectives

- Clean inconsistent formatting and naming
- Extract structured data from compound fields (e.g., RAM/SSD from `storage`)
- Normalize OS, image URLs, and release dates
- Identify and flag missing data
- Prepare for use in dashboards or analysis tools (Excel, Power BI, etc.)

---

## 🔧 Cleaning Steps (Formulas Used)

### 1. 🖥 OS Standardization

Remove leading dashes from `system_name`:
```excel
=TRIM(SUBSTITUTE(L2,"-",""))

## Augustine
