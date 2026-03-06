 
INTERNSHIP PROJECT 
Data Quality Issue Management & Reporting
First Citizens Bank  |  Enterprise Data & Analytics (ED&A) Team  |  Credit Department

Organization	First Citizens Bank (India) — formerly Credit Data Analytics, now Enterprise Data & Analytics (ED&A)
Department	Credit Department — Enterprise Data & Analytics (ED&A) Team
Duration	Internship Period (Multi-Quarter)
Role	Data Analytics Intern
Tools & Technologies	SQL • Power BI • Power Query • DAX • Data Modelling • Excel • CECL System • FCO Dashboard
Data Source	Enterprise Data Warehouse (EDW) via FRDS (Financial Reporting Data Store)
Data Volume	5+ years of raw historical data extracted from CECL & FCO dashboards (millions of records, CSV format)
Projects Delivered	2 Interactive Power BI Dashboards (Reporting + Remediation)

Project 1 — DQ Issue Management & Reporting

Background & Problem Statement
The Enterprise Data & Analytics (ED&A) team at First Citizens Bank is responsible for monitoring the quality of financial data flowing through the bank's Enterprise Data Warehouse (EDW). The bank ingests customer and financial data from numerous source systems into the EDW. Within the EDW sits the Financial Reporting Data Store (FRDS) — a specialised repository holding critical financial data where the team runs automated Data Quality (DQ) checks using SQL and database queries.

When these DQ checks identify anomalies or rule violations, the resulting exception data is stored in two downstream systems: the CECL (Current Expected Credit Loss) dashboard and the FCO dashboard. Prior to this project, the team was managing and reviewing this exception data through raw Excel files — a time-consuming, error-prone, and non-scalable process.

Objective
To design and develop an end-to-end automated Power BI dashboard that enables the ED&A team to:
•	Monitor active DQ exceptions across the CECL and FCO monitoring systems in real time
•	Track financial exposure (Unpaid Principal Balance & SEC Unfunded Balance) linked to exceptions
•	Identify which Critical Data Elements (CDEs) and DQ rules are triggering exceptions
•	Pinpoint which operations teams are responsible for the most exceptions and highest exposure
•	Drill down into individual exceptions for root cause investigation
•	Replace manual Excel-based reporting with an automated, self-refreshing analytical platform

Data Pipeline & Technical Architecture
The data journey for this project spanned the following layers:

Source Systems	Multiple upstream banking systems feeding customer and financial data into the bank's Enterprise Data Warehouse (EDW)
EDW / FRDS	Financial Reporting Data Store (FRDS) — a sub-layer within EDW housing financial records. SQL/DB queries were run here to evaluate DQ rules and generate exception data.
Exception Storage	CECL (Current Expected Credit Loss) and FCO dashboards store triggered exception records including associated financial exposure amounts.
Data Extraction	5+ years of historical exception data extracted in CSV format — millions of rows, containing significant volumes of erroneous, missing, and inconsistently formatted data.
Data Cleaning	Power Query (M language) was used to build automated transformation pipelines: null handling, deduplication, standardising formats, deriving calculated columns, and appending new data to a master file.
DAX Automation	Custom DAX measures and calculated columns were created to automate metric computation so that when new data is uploaded, all KPIs, charts, and visuals refresh without manual intervention.
Data Modelling	Star-schema data model established to link exception records, DQ rules, CDEs, operations teams, and financial exposure tables into a coherent analytical layer.
Visualisation	Power BI Desktop was used to design the interactive dashboard with slicers, gauges, combo charts, donut/pie charts, and a decomposition tree.

Dashboard Features & Functionality
Filter Panel (Left Sidebar)
Five interactive slicers allow users to filter all visuals simultaneously by:
•	Year (e.g. 2019 – 2024)
•	Month
•	Quarter (Q1–Q4)
•	CDE (Critical Data Element)
•	DQ Rule
A Reset button clears all filters in one click, restoring the full dataset view.

KPI Cards (Top Row)
10.79K (Sample)
Total Exceptions	$19.25bn (Sample)
Unpaid Principal Balance	$22.23bn (Sample)
SEC Unfunded Balance

These three cards give an at-a-glance snapshot of the scale of active exceptions and their total financial exposure across CECL and FCO systems.

Gauge Charts (Top Right)
Two semi-circular gauge charts display:
•	CDE With Exceptions — out of the total CDEs monitored (109), how many are currently triggering an exception (e.g. 62)
•	DQ Rule With Exception — out of all active DQ rules (507), how many are firing exceptions (e.g. 210)
Note: One CDE can have multiple DQ rules running underneath it. These gauges provide a coverage and health status view.

Combo Chart — Total Exposure by Exception Count
A dual-axis bar-and-line chart presents monthly exception counts (bar) alongside total financial exposure as a percentage of the portfolio (line). This visual identifies trends over time — periods of heightened exception activity and the corresponding financial risk spikes — enabling proactive monitoring.

Donut & Pie Charts — Operations Team Accountability
•	Donut Chart: Displays the top operations teams ranked by exception count — identifying which teams own the most unresolved DQ issues.
•	Pie Chart: Displays the top operations teams ranked by total financial exposure associated with their exceptions — distinguishing high-count but low-risk teams from lower-count but high-exposure teams.

Decomposition Tree (Bottom Section)
An interactive decomposition tree that allows deep-dive analysis. Users can navigate from:
•	Operations Team → CDE → DQ Rule → DQ Rule ID → Exposure Value
This enables the team to trace any financial exposure or exception back to its root data quality rule, the responsible team, and the specific loan/record — essential for root cause investigations and audit trails.

Business Impact & Benefits
•	Visualisation: Replaced raw Excel outputs with an interactive, business-friendly dashboard — dramatically improving clarity for team meetings, client presentations, and management reporting.
•	Automation: The entire pipeline (data upload → transformation → dashboard refresh) is automated via Power Query and DAX. New data batches can be appended to the master file and all visuals update instantly without any manual work.
•	Exception Tracking: The team can now continuously monitor recurring exceptions, identify patterns, and escalate unresolved issues to the responsible operations teams.
•	Exposure Prioritisation: The dashboard separates exception frequency from exposure value, enabling the team to intelligently prioritise which issues to remediate first based on financial risk.
•	Operational Accountability: Clear attribution of exceptions and exposure to specific operations teams creates accountability and simplifies escalation workflows.
•	Audit Preparedness: The structured, traceable dashboard with full historical data supports both internal and external audit requirements — replacing ad hoc data pulls with a governed reporting layer.

 
Project 2 — DQ Issue Management & Reporting (Remediated)

Background & Problem Statement
As a natural companion to the Issue Management & Reporting dashboard, the ED&A team also needed a structured way to track and demonstrate the remediation work being done — i.e., the exceptions that had already been investigated and resolved. Without this, there was no consolidated view of team productivity, remediation progress, or the financial exposure that had been secured through resolution efforts.

Objective
To build a focused Power BI dashboard that tracks all historically remediated DQ exceptions, providing the team with:
•	A running record of every remediated exception and its associated financial exposure
•	Clear visibility of which DQ rules and CDEs the team has successfully covered
•	Attribution of remediation work to specific operations teams
•	An automated, evergreen platform that grows with new remediation activity over time
•	A motivational and audit-ready reporting tool for team and function meetings

Dashboard Features & Functionality
Filter Panel
Five slicers (Year, Month, Quarter, DQ Rule, CDE) allow targeted filtering of remediation history, with a Reset button to return to the full dataset view.

Combo Chart — Remediated Count by Exposure
A dual-axis bar-and-line chart plots remediated exception counts (bar) against total financial exposure resolved (line) over time. This shows the pace and scale of remediation activity — including any high-volume periods where large batches of exceptions were cleared.

Donut Chart — Remediated Exception Count by Ops Team
A donut chart breaking down total remediated exceptions by the responsible operations team, highlighting which teams have contributed most to the remediation effort.

KPI Cards
$62,380M (Sample)
Total SEC Unfunded (Remediated)	$124,168M (Sample)
Total Net Loan (Remediated)	20,632 (Sample)
Remediation Count

These three cards represent the cumulative impact of the team's remediation work — quantifying both the volume of exceptions resolved and the total financial exposure secured.

Gauge Charts — DQ Coverage
•	DQ Rule Covered: Out of 507 active DQ rules, how many has the team worked on through remediation (e.g. 277)
•	CDE Covered: Out of 109 CDEs, how many have been touched by remediation activity (e.g. 70)
These gauges demonstrate the breadth of the team's coverage across the data quality landscape.

Top Exposure by Ops Team Responsible
A horizontal bar chart ranking operations teams by the total financial exposure associated with the exceptions they remediated, making it easy to identify the highest-impact remediation contributors.

Business Impact & Benefits
•	Progress Tracking: Gives the ED&A team a real-time view of total exceptions remediated and the cumulative financial exposure they have secured — demonstrating tangible business value.
•	Historical Record: Acts as a permanent, searchable log of all remediation activity, allowing the team to reference previous resolutions for similar issues.
•	Automation: Like Dashboard 1, this platform is fully automated. Future remediation data can be appended and the dashboard self-updates — no manual rework needed.
•	Team Motivation: The dashboard serves as a performance showcase in team meetings and function meetings, making the team's achievements visible and celebrating milestones.
•	Audit Readiness: Provides a clean, evidence-based record of remediation activity — indispensable for internal compliance reviews and external regulatory audits.

Technical Skills Demonstrated

Category	Tool / Technology	Application
Data Engineering	SQL / Database Queries	Ran DQ checks on FRDS (Financial Reporting Data Store) within the EDW to identify and flag exception records
Data Extraction	CSV / Excel	Extracted 5+ years of historical exception data from CECL and FCO dashboards (millions of records)
Data Cleaning	Power Query (M)	Built automated transformation pipelines: null handling, deduplication, type casting, column derivation, and master file appending
Analytics & Metrics	DAX (Data Analysis Expressions)	Authored custom measures and calculated columns for KPIs, exception ratios, exposure aggregations, and period comparisons
Data Modelling	Power BI Data Model	Designed a star schema linking exception records, DQ rules, CDEs, ops teams, and financial tables
Visualisation	Power BI Desktop	Built full interactive dashboards including slicers, KPI cards, gauges, combo charts, donut/pie charts, and decomposition trees
Domain Knowledge	CECL / FCO / Credit Risk	Applied understanding of credit risk frameworks, financial exposure metrics (Unpaid Principal, SEC Unfunded), and data governance


Note: All figures shown in portfolio dashboards are illustrative dummy data. Actual production data has been replaced in compliance with organizational data confidentiality policies.
