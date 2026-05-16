# HR Insights Pro – Intelligent Workforce Analytics Dashboard

![Project Banner](https://via.placeholder.com/1200x500/0A3D2E/00FF9F?text=HR+Insights+Pro)

**Turning HR Data into Strategic Workforce Intelligence**

---

## 📋 Project Overview

**HR Insights Pro** is a business intelligence and workforce analytics solution developed in Power BI to help organizations monitor employee performance, workforce trends, retention risks, and strategic HR metrics in real time.

The dashboard transforms raw HR data into actionable business insights that support data-driven decision-making across recruitment, employee retention, workforce planning, and organizational performance management.

---

## 🎯 Business Objectives

The dashboard was designed to help organizations:

- Analyze workforce distribution across departments
- Monitor employee attrition and retention trends
- Identify high-risk workforce segments
- Improve HR decision-making through real-time analytics
- Support strategic workforce planning
- Enhance organizational performance visibility

---

## ✨ Key Features

- Executive Overview with core KPIs (1,470 employees)
- Promotion Pipeline Tracking (72 employees due)
- Retrenchment Risk Analysis (117 employees flagged)
- Departmental & Role-level performance breakdown
- Performance Rating and Job Satisfaction insights
- Interactive filtering and drill-down capabilities

---

## 🔍 Key Business Insights

- **Research & Development** has the highest retrenchment risk (**74 employees**)
- **72 employees** are due for promotion, with the **Manager** role having the largest backlog (**22 employees**)
- **84.63%** of employees are rated as High Performers
- Strong job satisfaction with **569 employees** in the High category
- Majority of workforce concentrated in **Job Level 1 & 2**

---

## 📸 Dashboard Screenshots

![Executive Overview](Screenshots/Executive_Overview.png)
![Promotion & Retrenchment](Screenshots/Promotion_Retrenchment.png)
![Department & Role Analysis](Screenshots/Department_Analysis.png)

---

## 🔢 Key DAX Measures Used

```dax
// Base Measure
Total Emp = COUNTROWS('HR Analytics Data')

// Core Counts
Due for promotion = CALCULATE([Total Emp], 'HR Analytics Data'[Promotion Status] = "due for promotion")
Retrenched = IF(ISBLANK(CALCULATE([Total Emp], 'HR Analytics Data'[Retrenchment Status] = "Will be Retrenched")), 0, CALCULATE([Total Emp], 'HR Analytics Data'[Retrenchment Status] = "Will be Retrenched"))

// Percentage Measures
% Due for promotion = DIVIDE([Due for promotion], [Total Emp], 0)
% On Service = DIVIDE([On Service], [Total Emp], 0)
% Will Be Retrenched = DIVIDE([Retrenched], [Total Emp], 0)
% Male = DIVIDE([Male], [Total Emp], 0)
% Female = DIVIDE([Female], [Total Emp], 0)
% High Rated = DIVIDE([High Rated], [Total Emp], 0)

// Supporting Measures
High Rated = CALCULATE([Total Emp], 'HR Analytics Data'[Performance Rating] = "High Rating")
Male = CALCULATE([Total Emp], 'HR Analytics Data'[Gender] = "male")
Female = CALCULATE([Total Emp], 'HR Analytics Data'[Gender] = "female")
On Service = CALCULATE([Total Emp], 'HR Analytics Data'[Retrenchment Status] = "On Service")
##

📁 Repository Structure

```bash
HR-INSIGHTS-PRO-Intelligent-Workforce-Analytics-Dashboard/
├── HR Insights Pro.pbix
├── Data/
│   ├── HR Analytics Data.csv
│   ├── HR Employee Data.csv
│   └── Clustered HR Data/
├── Documentation/
│   └── HR Insight Pro Presentation.pdf
├── Screenshots/
└── README.md

🛠️ Technologies Used

Microsoft Power BI Desktop
DAX (Advanced Measures & Calculations)
Power Query (Data Cleaning & Transformation)
Microsoft Excel / CSV
Canva (Presentation & Visual Design)
GitHub (Documentation & Version Control)

📊 Project Workflow

textRaw HR Data (CSV/Excel)
        ↓
Power Query (Cleaning & Modeling)
        ↓
DAX Calculations & KPIs
        ↓
Interactive Power BI Dashboard
        ↓
Actionable Business Insights

🚀 How to Use

1. Open HR Insights Pro.pbix using Power BI Desktop
2. Explore the interactive dashboard pages

👤 Author
Boniface Anuforo
Data Analyst | Business Intelligence | Workforce Analytics

GitHub: https://github.com/bcanuforo/HR-INSIGHTS-PRO-Intelligent-Workforce-Analytics-Dashboard
LinkedIn: www.linkedin.com/in/boniface-anuforo-34b935219


⭐ If this project inspires you, please give it a star!
