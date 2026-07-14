# 🏥 HCAHPS Patient Survey — US Hospital Experience Analysis (2014–2022)

![Dashboard Preview](images/dashboard_preview.png)

## 📌 Project Overview

This project analyses **US hospital patient experience data** collected through the HCAHPS
(Hospital Consumer Assessment of Healthcare Providers and Systems) survey across **9 years
(2014–2022)**. It covers **50 US states** across **10 patient experience measures**, answering
key questions about whether hospitals have genuinely improved the quality of care they deliver.

> **Data Source:** Maven Analytics Data Playground — HCAHPS Patient Survey dataset
> (originally sourced from the US Centers for Medicare & Medicaid Services)

---

## 🎯 Business Questions Answered

1. Have hospitals made improvements in quality of care over the past 9 years?
2. Are there specific areas where hospitals have made more progress than others?
3. Are there still major areas of opportunity remaining?
4. What recommendations can be made to help hospitals further improve patient experience?

---

## 🗂️ Project Structure

```
hcahps-patient-survey/
│
├── data/
│   ├── national_results.csv      # National Top/Middle/Bottom box scores per measure per year
│   ├── state_results.csv         # State-level scores (4,580 rows across 50 states)
│   ├── measures.csv              # 10 patient experience measures and their types
│   ├── reports.csv               # 9 reporting periods with survey date ranges
│   ├── states.csv                # US state names and regional groupings
│   └── data_dictionary.csv       # Field definitions for all tables
│
├── powerbi/
│   └── HCAHPS_Patient_Survey_Dashboard.pbix   # Interactive Power BI dashboard
│
├── images/
│   └── dashboard_preview.png     # Dashboard screenshot
│
└── README.md
```

---

## 📊 The 10 Patient Experience Measures

| Measure ID | Measure | Type |
|---|---|---|
| H_COMP_1 | Communication with Nurses | Composite |
| H_COMP_2 | Communication with Doctors | Composite |
| H_COMP_3 | Responsiveness of Hospital Staff | Composite |
| H_COMP_5 | Communication about Medicines | Composite |
| H_COMP_6 | Discharge Information | Composite |
| H_COMP_7 | Care Transition | Composite |
| H_CLEAN_HSP | Cleanliness of Hospital Environment | Individual |
| H_QUIET_HSP | Quietness of Hospital Environment | Individual |
| H_HSP_RATING | Overall Hospital Rating | Global |
| H_RECMND | Willingness to Recommend the Hospital | Global |

---

## 🔍 Key Findings

### 1. Overall Patient Satisfaction Slightly Declined
Despite 9 years of data collection, the national average Top Box % dropped from
**71.0% (2014) to 69.4% (2022)** a decline of **1.6 percentage points**. This suggests
that while some areas improved, others deteriorated enough to pull the overall average down.

### 2. Care Transition Is the Biggest Concern
Care Transition — how well hospitals prepare patients for going home — showed the
**sharpest decline of -4.0pp** over 9 years, scoring just **51%** in 2022. This means
nearly half of all patients felt unprepared when leaving hospital.

### 3. Discharge Information Leads the Way
Discharge Information scored the **highest of all measures at 86%** in 2022 —
showing that hospitals have invested heavily in giving patients written information
before leaving, even if verbal preparation (Care Transition) lags behind.

### 4. Quietness Remains Stubbornly Low
The quietness of hospital environments at night scored just **62%** in 2022 and
showed minimal improvement over 9 years suggesting this is a structural
challenge that simple training programmes haven't been able to fix.

### 5. Geographic Inequality Is Significant
New England states (Massachusetts, Connecticut, Vermont) consistently outperform
the rest of the country. Southern states (Mississippi, Alabama, Louisiana) consistently
score lowest a gap of **4–6 percentage points** that has persisted across all 9 years.

---

## 💡 Recommendations

Despite steady improvements over 9 years, hospitals still have clear areas to address.
Quietness remains the lowest-rated experience enforcing quiet hours and reducing
night-time noise should be an immediate priority. Patients also need clearer, jargon-free
explanations of their medicines and a written plan before leaving hospital, as Care
Transition scores show many still feel unprepared going home. Hospitals in lower-scoring
regions particularly in the South should look to New England, which consistently leads
the country in patient experience, and adopt their communication and discharge practices.
Where progress has been made especially in doctor and nurse communication that
momentum must be protected and built upon.

---

## 🛠️ Tools & Skills Used

| Tool | How It Was Used |
|---|---|
| **Microsoft Excel (Power Query)** | Data import, table merging, Master analysis table |
| **Microsoft Excel (PivotTables)** | 4 summary analyses answering Maven's business questions |
| **Power BI Desktop** | Interactive dashboard with slicers, KPI cards, and 4 chart visuals |

### Power BI Features Used
- Power Query merges across 5 related tables
- DAX measures for dynamic KPI calculations
- Interactive slicers (Survey Year, Care Area, US Region)
- Conditional colour formatting (red → green gradient)
- US Shape Map with state-level colour saturation
- Cross-filtering across all visuals

### DAX Measures Written
```
Avg Top Box % = AVERAGE(National_Master[Top Box Pct])

Top Box 2022 = CALCULATE(AVERAGE(National_Master[Top Box Pct]),
               National_Master[Release Period] = "07_2023")

Top Box 2014 = CALCULATE(AVERAGE(National_Master[Top Box Pct]),
               National_Master[Release Period] = "07_2015")

Change vs 2014 = [Top Box 2022] - [Top Box 2014]
```

---

## 👤 Author

**Joseph Ejoh**
Data Analyst | Nigeria (Open to Remote)
- 🌐 Portfolio: [josephejoh.github.io](https://josephejoh.github.io)
- 💼 GitHub: [github.com/JosephEjoh](https://github.com/JosephEjoh)
- 📧 josephcejoh@gmail.com

---

*This project is part of my data analytics portfolio demonstrating end-to-end analysis
skills across Excel, Power Query, PivotTables, and Power BI.*
