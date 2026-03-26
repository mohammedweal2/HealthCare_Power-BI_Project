# 🏥 Healthcare Analytics Dashboard — Power BI

A comprehensive Power BI project analyzing hospital patient data across multiple healthcare KPIs, built with a focus on **domain understanding** rather than just tool usage.

---

## 📌 Project Overview

This project is part of my ongoing journey to deepen my understanding of **key KPIs across different business domains** — including Sales, E-commerce, and Healthcare. Rather than simply applying tools, the goal was to build genuine domain knowledge and translate it into meaningful business insights.

**Domain:** Healthcare  
**Tool:** Microsoft Power BI + Power Query  
**Dataset Size:** 9,000+ patient records

---

## 🧠 Domain Concepts Explained

Before diving into the data, I made sure to fully understand the domain-specific terminology:

| Concept | Description |
|---|---|
| **Patient Race** | The ethnic/racial identity of patients admitted to the hospital |
| **Department Referral** | The specific department each patient is referred to based on their condition. Departments include: Cardiology, Neurology, Nephrology, and Orthopedics |
| **Patient Admin Flag** | A boolean field with meaningful business logic: `True` = patient condition is critical and requires transfer to another department; `False` = patient has recovered and been discharged |

---

## 🛠️ Data Preparation Steps (Power Query)

### 1. Data Cleaning
- Identified and handled missing/null values
- Evaluated which null records were safe to drop vs. retain

### 2. Fixing the Admission Date Column ⚠️
The `Patient Admission Date` column was stored as **text**, and a direct conversion to `DateTime` caused errors.

**Solution:**
1. Split the date into three separate columns: **Year**, **Month**, **Day**
2. Merged them back using `/` as a delimiter → reconstructed a valid `Date` column
3. Separated the `Time` component into its own column

> This workaround successfully resolved the type conversion issue without data loss.

### 3. Creating a Date Table
Built a dedicated **Date Table** in Power BI using the date range from the dataset to enable proper time intelligence functions.

---

## 📊 Key KPIs & Insights

| KPI | Value |
|---|---|
| 👥 Total Patients Analyzed | **9,000+** |
| ⏱️ Average Patient Wait Time | **35 minutes** |
| 🚨 Patients Exceeding Target Wait Time | **40%** |
| ✅ Patients Served Within Target Time | **59%** |
| 📅 Busiest Day of the Week | **Saturday** |
| 🕐 Peak Hours | **Late evening** |

### Key Finding
> **40% of patients exceeded the target wait time** — a critical operational gap that requires immediate process improvement, particularly on Saturdays during late evening hours.

---

## 💡 Lessons Learned

- Understanding the **business domain** is just as important as knowing the tool
- Data type issues (especially date/text conversions) require creative workarounds in Power Query
- KPIs only become meaningful when you understand **what they represent** in the real world
- Building a proper **Date Table** is essential for reliable time-based analysis in Power BI

---

## 🗂️ Project Structure

```
healthcare-powerbi/
│
├── Healthcare_Dashboard.pbix     # Main Power BI file
├── data/
│   └── patients_raw.csv          # Source dataset
└── README.md
```

---

## 🚀 How to Run

1. Clone or download this repository
2. Open `Healthcare_Dashboard.pbix` in **Power BI Desktop**
3. If needed, update the data source path under **Transform Data → Data Source Settings**
4. Refresh the dataset

---

## 📬 Connect

Feel free to reach out or leave feedback — always open to improving both technical skills and domain knowledge across different industries.
```
