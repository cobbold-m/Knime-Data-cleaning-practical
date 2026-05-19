# Knime-Data-cleaning-practical
Data cleaning, filtering, and manipulation practicals using KNIME Analytics Platform — University of Reading, Data Science module
# 🧹 KNIME Data Cleaning & Manipulation

> **Practical 1** | University of Reading — Department of Computer Science  
> Module: Data Science | Dr. Carmen Lam

---

## 📌 Overview

This repository contains my work for **Practical 1: Data Cleaning and Manipulation**, completed as part of the Data Science module at the University of Reading. The practical explores core data preprocessing techniques using **KNIME Analytics Platform**, working with the UCI Adult Income dataset.

---

## 🛠️ Tools & Technologies

![KNIME](https://img.shields.io/badge/KNIME-FFD500?style=for-the-badge&logo=knime&logoColor=black)
![CSV](https://img.shields.io/badge/Data-CSV-green?style=for-the-badge)
![University of Reading](https://img.shields.io/badge/University%20of%20Reading-003DA5?style=for-the-badge)

---

## 📂 Repository Structure

```
knime-data-cleaning-practical/
│
├── 📁 workflows/
│   └── P1_Data_Cleaning.knwf        # KNIME workflow file
│
├── 📁 data/
│   ├── adult_file_1_raw_data.csv     # Original raw dataset
│   ├── adult_file_2_clean_data.csv   # Cleaned dataset
│   ├── adult_file_3_male.csv         # Male subset
│   ├── adult_file_4_female.csv       # Female subset
│   ├── adult_file_5_occupational.csv # Occupational data subset
│   └── adult_file_6_personal.csv     # Personal data subset
│
└── README.md
```

---

## ✅ Tasks Completed

### Task 1 — Data Cleaning
- Loaded raw data using the **File Reader (Complex Format)** node
- Handled missing values:
  - **String columns** → removed rows with missing values
  - **Number columns** → replaced missing values with the **mean**
- Reset row IDs using the **RowID** node
- Exported cleaned data to `adult_file_2_clean_data.csv`

---

### Task 2 — Row and Column Filtering
Used **Row Filter** and **Column Filter** nodes to extract:

| Filter | Description |
|--------|-------------|
| 🔢 Age < 30 | All records where person's age is under 30 |
| 👩 Female | All female data samples |
| 🔟 First 100 | Only the first 100 rows |
| ❌ No "some-college" | Removed records with that education label |
| 🧍 Personal Info | Selected only personal attribute columns |

---

### Task 3 — Horizontal & Vertical Data Splitting
Used **Row Splitter** and **Column Splitter** nodes to produce 4 subsets:

| File | Contents |
|------|----------|
| `adult_file_3_male.csv` | Male records only |
| `adult_file_4_female.csv` | Female records only |
| `adult_file_5_occupational.csv` | Occupational attributes only |
| `adult_file_6_personal.csv` | Personal attributes only |

> 💡 **Filter vs Splitter:** Filter nodes output **one** table (keeping or discarding rows/columns). Splitter nodes output **two** tables simultaneously — the matched data and the remainder — making them more efficient when you need both halves.

---

### Task 4 — Concatenation and Joining
- **Concatenated** `adult_file_3_male.csv` + `adult_file_4_female.csv` → stacking rows vertically to rebuild the full dataset
- **Joined** `adult_file_5_occupational.csv` + `adult_file_6_personal.csv` → merging columns horizontally using a common key

> 💡 **Concatenation vs Joining:**  
> Use **concatenation** when datasets share the same columns and you want to stack rows (e.g. combining data from different time periods or sources).  
> Use **joining** when datasets share the same rows but have different columns, and you want to merge attributes (e.g. combining a demographics table with a salary table).

---

## 📖 Dataset

The dataset used is based on the [UCI Adult Income Dataset](https://archive.ics.uci.edu/ml/datasets/adult), which contains census data used to predict whether a person earns over $50K/year.

---

## 🚀 How to Run

1. Download and install [KNIME Analytics Platform](https://www.knime.com/downloads)
2. Clone this repository
3. Open KNIME and import the workflow from the `workflows/` folder
4. Update file paths in the CSV Reader/Writer nodes to match your local directory
5. Execute the workflow ▶️

---

*University of Reading · Department of Computer Science · 2025–2026*
