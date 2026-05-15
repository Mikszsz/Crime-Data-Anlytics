Crime Data Analytics Documentaion

1. Dataset Overview
The dataset covers crime incidents reported in the Los Angeles area from 2020 to 2024. It contains records sourced from the Los Angeles Police Department (LAPD) open data portal and was loaded into Power BI for visualization and analysis.

Tables / Entities
The data model includes the following tables:
•Crime_fact — primary fact table containing all crime incident records
•Crime Data — supporting reference table for crime classification
•dim_weapon — dimension table mapping weapon codes to descriptions
•LocalDateTable (x2) — auto-generated date dimension tables by Power BI for time intelligence

Columns Included in the Dataset
The following columns are used across the data model and visualizations:

DR_NO	Vict Age
Date Reported	Vict Sex
Date Occurence	Vict Descent
Area Name	Time Occurence
Report District No	Date Occurence Year
Crime Code Desc	Date Occurence Month
Status Desc	Date Occurence Day
Premise Desc	Date Occurence Quarter
Weapon_Desc	


<img width="1688" height="458" alt="image" src="https://github.com/user-attachments/assets/ea1cac01-5321-4bd4-89fb-ee44ab3de4bb" />
