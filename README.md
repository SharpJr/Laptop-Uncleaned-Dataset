#  Laptop Sales Dataset — Excel Data Cleaning & Structuring

This project focuses on transforming a raw and messy Excel dataset of laptop listings into a clean, structured format suitable for analysis and reporting — using only Microsoft Excel. The dataset includes product names, prices, specs, release dates, ratings, operating systems, and more.

---

##  Dataset Overview

- **File**: `99laptop_dirty_dataset.xlsx`
- **Sheet**: `99laptop_dirty_dataset`
- **Total Rows**: ~100
- **Sample Columns**:
  - `name`: Product title
  - `name_c`: Cleaned product title (often redundant)
  - `img`: Image path (missing `https:`)
  - `price`: Selling price (text format)
  - `no_rates`: Number of customer ratings
  - `rating_100`: Product rating (0–100)
  - `released`: Launch date (stored as string)
  - `system_name`: OS name with unnecessary prefix (`- Windows 11`)
  - `windows`: OS fallback value
  - `processor`: Text description of the processor
  - `storage`: RAM + SSD combined (e.g., "8 GB LPDDR5 RAM, 512 GB SSD")
  - `spec_score`, `usb`, `slim`, `camera`, etc.

---

##  Cleaning Goals

1. Standardize OS names and merge with backup column
2. Extract RAM size, RAM type, and SSD size from compound `storage`
3. Normalize numeric columns (price, ratings)
4. Convert string-based dates into real Excel dates
5. Fix relative image URLs
6. Identify and flag missing values
7. Extract brand from product title

---

##  Excel Cleaning Steps & Formulas

### 1.  Clean and Merge OS Columns

#### ✅ Remove dash (`-`) from `system_name`:
```excel
=TRIM(SUBSTITUTE(L2, "-", ""))
