🏥 Hospital Records Analysis Dashboard

An interactive Tableau dashboard that analyzes patient encounters, procedures, costs, and insurance coverage for a hospital, helping stakeholders understand patient demographics, care utilization, and spending patterns.

📌 Project Overview

Hospital management needs a clear view of who the patients are, what care they receive, what it costs, and how much is covered by insurance. This project combines five related datasets into a single data model and presents the key metrics in one interactive dashboard.

Key questions answered

How many patients does the hospital serve, and what is their demographic profile (age, gender, race)?
Which encounter types (ambulatory, inpatient, emergency, etc.) drive the most volume and cost?
What is the average cost per visit and average length of stay?
What share of encounters and procedures are covered by insurance?
How do admission and readmission rates look across patient groups?
📊 Dataset

The workbook is built on five related tables:

Table	Description	Records
patients.csv	Patient demographics (birthdate, gender, race, ethnicity, location)	974
encounters.csv	Hospital visits with class, cost, payer, and coverage	27,891
procedures.csv	Procedures performed during encounters	47,701
payers.csv	Insurance payers	10
organizations.csv	Hospital/organization details	1

Time span: January 2011 – February 2022

🔍 Key Insights
$101M+ in total claim costs across 27.9K encounters, averaging about $3,640 per encounter.
Ambulatory visits are the most common (12.5K encounters), but inpatient visits are the most expensive, averaging about $7,760 vs. about $2,890 for ambulatory.
Only about 51% of encounters had insurance coverage, highlighting a significant coverage gap.
The patient base is evenly split by gender (494 male, 480 female), and about 16% of patients are recorded as deceased.

Figures reflect the full dataset with no filters applied. Values may change with dashboard filters.

🛠️ Features & Technical Highlights
Multi-table data model: joined patients, encounters, procedures, payers, and organizations.
Calculated fields
Patient Age and 10-year Age Category buckets (0–9 … 90+)
Stay Duration (days between encounter start and stop)
Admission Status and Admitted or Readmitted flags
Procedure Coverage Status (covered vs. not covered by insurance)
Is_Alive flag (alive vs. deceased)
Cleaned patient names using REGEXP_REPLACE
LOD expressions: FIXED calculations to identify each patient's latest visit and count distinct patients per date.
Interactive filters and drill-down views for detailed record exploration.


📈 Dashboard Views
Sheet	Purpose
Total Patients	Headline patient count KPI
Admission Rates	Admitted vs. not admitted share
Avg Cost/Visit	Average cost per encounter
Stay Duration	Length-of-stay analysis
Encounter Costs Analysis	Cost breakdown by encounter type
Encounterclass Types	Volume by encounter class
Age Category / Gender / Demographic by Race	Patient demographic breakdowns
Insurance Count / Insured Procedures Count	Insurance coverage analysis
Details	Record-level drill-down


🧰 Tools Used
Tableau Desktop (data modeling, calculated fields, LOD expressions, dashboard design)
