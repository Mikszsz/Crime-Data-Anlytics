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

Data Preprocessing ⸙
Using the CLEAN framework (Conceptualize, Locate, Evaluate, Augment, Note)
╰┈➤ Conceptualize the Data
Each row in the dataset represents a unique crime incident or police report recorded from 2020 to 2024. The dataset contains information about the date and time of occurrence, location of the incident, victim demographics, crime classifications, weapon information, and reporting status used for crime analysis and public safety monitoring.

╰┈➤ Locate Solvable Problems
1. DATE RPTD — all rows have same timestamp (1,004,895 rows)
Removed the unnecessary timestamp and kept only the date value to make the format cleaner and easier for analysis.
2. DATE OCC — all rows have same timestamp (1,004,895 rows)
Removed the time portion because all rows contained the same default timestamp value.
3. TIME OCC — military time and improper format (1,004,895 rows)
Converted the military time format into a proper readable time format for consistency and easier interpretation.
4. Mocodes — inaccurate formatting and blanks (262,490 rows)
Standardized the formatting of mocodes and fixed entries with incomplete formatting to improve consistency.
5. Vict Age — negative ages (137 rows)
Negative age values were considered invalid data entries and were changed to 0.
6. Vict Sex — empty data, "-", H, and X values (242,499 rows)
Replaced unclear and inconsistent values with standardized categories such as “F”, “M”, and “Unknown”.
7. Vict Descent — empty data and "-" values (144,645 rows)
Blank and invalid entries were replaced with “Unknown” to maintain consistency in the dataset.
8. Premise CD — blanks (16 rows)
Missing premise codes were replaced with 0 because the actual value could not be identified.
9. Premis Desc — blanks and values with "*" (588 rows)
Cleaned the formatting and replaced unclear values with “Unknown”.
10. Weapon Used Cd — blanks (677,678 rows)
Missing weapon codes were replaced with “Unknown” because many incidents may not have involved a weapon.
11. Weapon Desc — blanks (677,678 rows)
Missing weapon descriptions were replaced with “Unknown” to match the cleaned weapon code column.
12. Status — same values as Status Desc (1,004,895 rows)
Removed the Status column because its information already existed in the Status Desc column, making it redundant.
13. Status Desc — “UNK” values (5 rows)
Replaced “UNK” with “Unknown” for readability and consistency.
14. Crm Cd 1 — blanks (11 rows)
Missing values were replaced with 0 because no matching crime code could be identified.
15. Crm Cd 2 — blanks (935,740 rows)
Blank entries were changed to 0 since many incidents only had one primary crime code.
16. Crm Cd 3 — blanks (1,002,580 rows)
Missing values were changed to 0 because additional crime codes were not always applicable.
17. Crm Cd 4 — blanks (1,004,830 rows)
Blank entries were replaced with 0 for consistency in the crime code columns.
18. LOCATION — unnecessary spaces and empty data
Removed unnecessary spaces and replaced missing values with “Unknown”.
19. Cross Street — unnecessary spaces and empty data
Removed extra spaces and replaced missing values with “Unknown” for cleaner location data.

╰┈➤ Evaluate Unsolvable Issues
1. Missing weapon information
A large number of rows had missing weapon-related data. These were retained as “Unknown” because not all crimes involve weapons, and assuming a value may lead to inaccurate analysis.
2. Multiple blank crime code columns
Crime code columns such as Crm Cd 2, Crm Cd 3, and Crm Cd 4 contained many blanks. These were kept as 0 because some incidents only require one official crime classification.

╰┈➤ Augment the Data
1. Created year column
Extracted the year from DATE OCC to make yearly crime trend analysis easier.
DATE OCC
year
2020-05-14
2020

2. Created month column
Extracted the month from DATE OCC for monthly crime pattern analysis.
DATE OCC
month
2020-05-14
May

3. Created day_of_week column
Added a column showing the day of the week to analyze which days have the highest crime occurrences.
DATE OCC
day_of_week
2020-05-14
Thursday

4. Created hour_occ column
Extracted the hour from TIME OCC to analyze crime activity by hour.
TIME OCC
hour_occ
18:30
18

5. Created full_location column
Combined LOCATION and Cross Street into one column to provide more complete location details.
LOCATION
Cross Street
full_location
Main St
5th Ave
Main St & 5th Ave


╰┈➤ Note and Document
Date and time fields were standardized for consistent formatting and easier time-based analysis.
Invalid, blank, and unclear categorical values were cleaned using standardized replacements such as “Unknown” and “0”.
Redundant columns were removed to reduce unnecessary duplication in the dataset.
Additional derived columns were created to improve trend analysis and visualization.
All preprocessing steps were applied consistently across the entire dataset to maintain data quality and reliability.


<img width="1688" height="458" alt="image" src="https://github.com/user-attachments/assets/7b84423f-4ada-468e-87ea-616f0bb4d6b2" />




Dashboard Visualizations

The dashboard is organized into three main report pages. Each page focuses on a distinct analytical perspective: overall crime overview, crime pattern analysis, and victim profiling. Interactive slicers are available on all pages for cross-filtering.







Page 1 — Crime Overview Dashboard
This page provides a high-level executive summary of crime activity, featuring KPI cards with sparklines, geographic and crime-type breakdowns, weapon usage analysis, and a monthly breakdown by day.

Slicers available on this page:
•Date Reported (Range)
•Date Occurrence (Range)
•Area Name
•Crime Code Desc
•Report District No

<img width="587" height="308" alt="cvsd" src="https://github.com/user-attachments/assets/aaa29b85-6dcb-4574-bb7a-d9572fe894bd" />


<img width="1024" height="697" alt="689286455_939872768885852_4142700994101863831_n" src="https://github.com/user-attachments/assets/24540a05-e5c5-4f18-9633-d71288accf45" />
 
 Figure 1a: Page 1 Wireframe — Crime Overview Dashboard (layout design)

 <img width="757" height="424" alt="1000028249" src="https://github.com/user-attachments/assets/88c04efb-28a7-4881-9a92-a4f55656d796" />

 Figure 1b: Page 1 Live Dashboard — Crime Overview (dark theme, red accents)






 
Page 2 — Crime Trends and Status
This page provides deeper temporal analysis and case resolution insights, including monthly trend lines, time-of-day heatmaps, premise type breakdowns, and crime status composition across years.

Slicers available on this page:
•Date Reported (Range)
•Date Occurrence (Range)
•Area Name
•Crime Code Desc
•Report District No

<img width="593" height="185" alt="sad" src="https://github.com/user-attachments/assets/06a8de00-ee92-4e4f-b7a2-3b36b9ba4afe" />

<img width="1024" height="768" alt="687962639_26948753788114338_2314805742268222346_n" src="https://github.com/user-attachments/assets/76dfc951-467c-4922-bc6a-f65f1131732c" />

Figure 2a: Page 2 Wireframe — Crime Trends and Status (layout design)

<img width="766" height="427" alt="1000028247" src="https://github.com/user-attachments/assets/ef7a8f80-5404-47f6-84ac-7e78d21d059c" />

Figure 2b: Page 2 Live Dashboard — Crime Trends and Status (dark theme, red accents)









Page 3 — Victim Demographics
This page presents a full victim profile analysis, covering age distribution, gender breakdown, ethnicity/descent, and aggregate statistical summaries. It enables targeted understanding of who is most affected by crime in the dataset.

Slicers available on this page:
•Date Reported (Range)
•Date Occurrence (Range)
•Area Name
•Crime Code Desc
•Victim Sex
•Report District No

<img width="593" height="236" alt="asdcx" src="https://github.com/user-attachments/assets/eff1d155-9eea-4a2f-a3e6-6864e4d902b2" />

<img width="1134" height="684" alt="679367393_1005889141962429_1423780584507947744_n" src="https://github.com/user-attachments/assets/38cf0f52-5baf-46d7-b454-39cb5b950cfa" />

Figure 3a: Page 3 Wireframe — Victim Demographics (layout design)

<img width="769" height="427" alt="1000028246" src="https://github.com/user-attachments/assets/b5e64dec-a0ec-4355-a991-ef3a35b58686" />

Figure 3b: Page 3 Live Dashboard — Victim Demographics (dark theme, red accents)




Insights and Recommendations

•High-frequency crime types identified through the Crime Rate by Area and Crime Code breakdown can help law enforcement prioritize patrol resources.

•Time-of-day and day-of-month heatmaps reveal peak crime windows, enabling targeted deployment of personnel during high-risk hours.

•Monthly crime trends allow year-over-year comparison to identify seasonal spikes or reductions in criminal activity.

•Victim demographic analysis across gender, descent, and age can support targeted outreach programs and community engagement strategies.

Conclusion

The Crime Data Analytics 2020–2024 Power BI dashboard provides a comprehensive, multi-dimensional view of crime incidents in the Los Angeles area. The dataset, sourced from LAPD open data, was loaded, cleaned, and transformed to support robust time intelligence, geographic analysis, and victim profiling.
