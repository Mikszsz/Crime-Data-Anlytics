Crime Data Anlytics Documention

Dataset Overview

The dataset covers crime incidents reported in the Los Angeles area from 2020 to 2024. It contains records sourced from the Los Angeles Police Department (LAPD) open data portal and was loaded into Power BI for visualization and analysis.

Tables / Entities
The data model includes the following tables:

•Crime_fact — primary fact table containing all crime incident records

•dim_weapon — dimension table mapping weapon codes to descriptions

Columns Included in the Dataset
The following columns are used across the data model and visualizations:
<img width="576" height="226" alt="Screenshot 2026-05-15 125616" src="https://github.com/user-attachments/assets/54b72391-3d2f-4700-a515-0813d6606a9b" />

Data Cleaning Process


<img width="1688" height="458" alt="image" src="https://github.com/user-attachments/assets/7b84423f-4ada-468e-87ea-616f0bb4d6b2" />

Dashboard Visualizations

The dashboard is organized into three main report pages. Each page focuses on a distinct analytical perspective: overall crime overview, crime pattern analysis, and victim profiling. Interactive slicers are available on all pages for cross-filtering.

Page 1 — Crime Overview
This page provides a high-level summary of crime activity across areas and time periods.

<img width="1024" height="697" alt="689286455_939872768885852_4142700994101863831_n" src="https://github.com/user-attachments/assets/24540a05-e5c5-4f18-9633-d71288accf45" />
                                Figure 1a: Page 1 Wireframe — Crime Overview Dashboard (layout design)

<img width="757" height="424" alt="1000028249" src="https://github.com/user-attachments/assets/88c04efb-28a7-4881-9a92-a4f55656d796" />
                               Figure 1b: Page 1 Live Dashboard — Crime Overview (dark theme, red accents)
 


<img width="587" height="308" alt="cvsd" src="https://github.com/user-attachments/assets/aaa29b85-6dcb-4574-bb7a-d9572fe894bd" />

Page 2 — Crime Patterns
This page dives deeper into temporal patterns, premises, and case resolution status.

<img width="593" height="185" alt="sad" src="https://github.com/user-attachments/assets/06a8de00-ee92-4e4f-b7a2-3b36b9ba4afe" />

Page 3 — Victim Profile
This page analyzes victim demographics including age, gender, and descent/ethnicity.

<img width="593" height="236" alt="asdcx" src="https://github.com/user-attachments/assets/eff1d155-9eea-4a2f-a3e6-6864e4d902b2" />

Slicers / Filters (All Pages)
The following interactive slicers are available across the dashboard pages to enable dynamic cross-filtering:
•Date Reported
•Date Occurence
•Area Name
•Crime Code Desc
•Report District No
•Vict Sex

Insights and Recommendations

•High-frequency crime types identified through the Crime Rate by Area and Crime Code breakdown can help law enforcement prioritize patrol resources.

•Time-of-day and day-of-month heatmaps reveal peak crime windows, enabling targeted deployment of personnel during high-risk hours.

•Monthly crime trends allow year-over-year comparison to identify seasonal spikes or reductions in criminal activity.

•Victim demographic analysis across gender, descent, and age can support targeted outreach programs and community engagement strategies.

Conclusion

The Crime Data Analytics 2020–2024 Power BI dashboard provides a comprehensive, multi-dimensional view of crime incidents in the Los Angeles area. The dataset, sourced from LAPD open data, was loaded, cleaned, and transformed to support robust time intelligence, geographic analysis, and victim profiling.
