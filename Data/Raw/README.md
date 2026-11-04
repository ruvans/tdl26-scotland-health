# Data Package



**Date**: 11/09/2026

**Title**: Telling Scotland's Health Story

**Authors**: K. Nicholson

**Institution**: Public Health Scotland, NHS

**Suggested Citation**: Public Health Scotland Strategy

https://publichealthscotland.scot/about-us/what-we-do-and-how-we-work/together-we-can-our-10-year-strategy-to-2035/strategic-vision/



\----



### Overview



This data package provides information from three datasets and reference file:

1. [A\&E](data/A&E)
2. [Unintentional Injuries](data/Unintentional_Injuries)
3. [Community Prescribing](data/Prescribing)
4. [Prescription cost analysis of 2025](reference_data)



The goal of each is to provide three different perspectives on the drivers of action outlined in the Public Health Scotland Strategy namely: Prevention-focused system, social and economic factors, places and community, healthy living, and equitable health and care. There are other open datasets that can be used as part of this work (https://www.opendata.nhs.scot/ ). The three datasets cover over 1000 locations that dispense prescriptions, 8 different injury types covering both admissions and deaths, and A\&E activity over the last 8 years with demographic information and the last 19 years for activity.



### Structure



The data has been organised in the following way:



- **`data/A&E/`** — A\&E dataset contained in 2 files:
  - [`Level_1_Activity.csv`](data/A&E/Level_1_Activity.csv) — Number of A\&E attendances across 103 sites by month, disaggregated by 3 variables about each site and 10 metrics for July 2007 to June 2026
  - [`Level_2_Demographics.csv`](data/A&E/Level_2_Demographics.csv) — Number of A\&E attendances across 14 health board areas by month, disaggregated by 3 demographics for January 2018 to June 2026
- **`data/Unintentional_Injuries/`** — Unintentional Injuries dataset contained in 2 files:
  - [`Admissions.csv`](data/Unintentional_Injuries/Admissions.csv) — Number of admissions for unintentional injuries across 32 council areas by financial year, disaggregated by 2 demographics and 2 injury variables for 2015/16 to 2024/25
  - [`Deaths.csv`](data/Unintentional_Injuries/Deaths.csv) — Number of deaths from unintentional injuries across 32 council areas by calendar year, disaggregated by 2 demographics and 2 injury variables for 2015 to 2024
- **`data/Prescribing/`** — Community Prescribing dataset contained in 3 files:
  - [`File_A_2019-21.csv`](data/Prescribing/File_A_2019-21.csv) — Number of items dispensed across 1343 dispensing locations by month, disaggregated by BNF chapter and location details for 2019 to 2021
  - [`File_B_2022-24.csv`](data/Prescribing/File_B_2022-24.csv) — Number of items dispensed across 1343 dispensing locations by month, disaggregated by BNF chapter and location details for 2022 to 2024
  - [`File_C_2025-26.csv`](data/Prescribing/File_C_2025-26.csv) — Number of items dispensed across 1343 dispensing locations by month, disaggregated by BNF chapter and location details for 2025 to May 2026
- **`reference_data/`** — Prescription cost analysis reference file:
  - [`Ref File prescription_cost_analysis_2025.xlsx`](reference_data/Ref%20File%20prescription_cost_analysis_2025.xlsx)





#### Dataset 1 - A\&E



Both Level 1 and Level 2 tables share some common metadata, and then each of them have additional attributes. The difference between Level 1 and Level 2 is that they record information from two perspectives; Level 1 from the hospitals' perspective and Level 2 from the patients' perspective. While Level 1 tells us the business of a hospitals and their wait time, Level 2 focuses on the patients demographics.



**Common metadata**

* Month - Month of the A\&E attendance
* HBName - Name of the Health Board
* DepartmentType - Type of A\&E department Type 1 is an Emergency Department working throughout the day and dealing with all cases, Type 3 is Minor Injuries Unit which can have more limited work hours and deals with more limited cases.





**Level 1 attributes**

* HospitalName - the name of the site where the patient was seen
* Address - address information for the hospital site across 3 columns (AddressLine1, AddressLine2, Postcode)
* AttendanceCategory - Three different groups, Unplanned which are patients that turn up at A\&E, New planned which are those arranged to arrive at A\&E and All which is the sum of Unplanned and New planned
* NumberOfAttendancesAll - Total number of attendances which is the sum of NumberWithin4hours and NumbersOver4hours
* NumberWithin4HoursAll - Total number of attendances where patients are seen and discharged within 4 hours of arrival
* NumberOver4HoursAll - Total number of attendances where patients are seen and discharged over 4 hours of arrival
* PercentageWithin4HoursAll - Percentage of those seen within 4 hours of the total
* NumberOfAttendancesEpisode - Total number of attendances this is the same as NumberOfAttendancesAll for Type 1 sites
* NumberWithin4HoursEpisode - As NumberWithin4HoursAll
* NumberOver4HoursEpisode - As NumberWithin4HoursAll
* PercentageWithin4HoursEpisode - As PercentageWithin4HoursAll
* NumberOver8HoursEpisode - Total number of attendances where patients are seen and discharged over 8 hours of arrival
* PercentageOver8HoursEpisode - Percentage of those seen over 8 hours of the total
* NumberOver12HoursEpisode - Total number of attendances where patients are seen and discharged over 12 hours of arrival
* PercentageOver12HoursEpisode - Percentage of those seen over 12 hours of the total





**Level 2 attributes**

* Age - Refers to the patient's age. Ages have been arranged in six different groups.
* Sex - The patient's sex.
* Deprivation - deprivation quintile of the postcode where the patient lives. Where 1 is the most deprived and 5 is the least deprived.



**Notes**

Episode data - some sites do not have detailed information on A\&E attendances, these are all MIU sites, the following are for sites with episode data and provide more information about attendances.

Additional A\&E data if you want it: https://www.opendata.nhs.scot/dataset/monthly-accident-and-emergency-activity-and-waiting-times

Reports on A\&E data are here: https://publichealthscotland.scot/healthcare-system/urgent-and-unscheduled-care/accident-and-emergency/overview/





#### Dataset 2 - Unintentional Injuries



Both Admissions and Deaths tables share the same attributes listed below:



* Dataset - Indicates which dataset the record  is coming from (admissions or deaths)
* Year Type - Indicates the years are based on financial or calendar years
* Year - The financial year (1st April to 31st March) the data refers to, as YYYY/YY.
* AgeGroup - Refers to the patient's age. Ages have been arranged in seven different groups.
* Sex - The patient's sex.
* InjuryLocation - The place the injury occurred: Home; Other; Unknown; Not applicable. Where place of injury occurred is not recorded and the admission is not due to a road traffic accident the place of occurrence is classified as 'Not applicable'.
* InjuryType - The injury type of the patient: All (aggregates all injury types); Land transport accidents; Poisoning; Falls; Struck by, against; Crushing; Scalds; Accidental exposure; Other.
* Number - The total number of admissions or deaths depending on file
* HBR - the health board area that the individual lives/lived in
* CAName - the council area that the individual lives/lived in
* HSCPName - the health and social care partnership that the individual lives/lived in





**Notes**

Original open data file is here: https://www.opendata.nhs.scot/dataset/unintentional-injuries

Report on Unintentional injuries can be found here: https://publichealthscotland.scot/publications/unintentional-injuries/unintentional-injuries-hospital-admissions-year-ending-31-march-2021-and-deaths-year-ending-31-december-2020/





#### Dataset 3 - Community Prescribing



All tables A, B and C share the same attributes listed below:



* PaidDateMonth - the month when the payment claim was submitted by the dispenser
* DispLocationCode - the unique code of the dispenser location
* BNFChapter - the British National Formulary chapter in which the item appears
* Chapter Description - short description of the BNF chapter
* NumberOfPaidItems - Count of the prescription items paid on a prescription
* PaidQuantity - Quantity of drug/appliance paid. May be different from what was prescribed or dispensed. This will be in measures such as number of pills, amount of liquid etc
* GrossIngredientCost - Paid Gross Ingredient Cost (GIC) of the prescription in pounds
* DispLocation - Information about the dispensing location in columns (DispLocationAddress1, DispLocationAddress2, DispLocationAddress3, DispLocationAddress4, DispLocationPostcode)
* HSCPName - The Health \& Social Care Partnership where the dispensing location is situated
* HBName - Health board where the dispensing location is situated





**Notes**

Further data on prescribing can be found here: https://www.opendata.nhs.scot/dataset/prescriptions-in-the-community

Report on prescribing can be found here:

* https://publichealthscotland.scot/publications/prescribing-practice-and-dispensing-pharmacy-open-data/prescribing-practice-and-dispensing-pharmacy-open-data-april-to-june-2026/
* https://publichealthscotland.scot/publications/community-pharmacy-contractor-activity/community-pharmacy-contractor-activity-data-for-april-to-june-2026/
* https://publichealthscotland.scot/publications/monthly-prescribing-activity-data/monthly-prescribing-activity-data-data-for-june-2026/







### Terminology



Here is a list of the common expressions and acronyms explained to help you understand the data.





#### A\&E Data



* A\&E (Accident and Emergency) - A hospital service that provides urgent treatment for people with illnesses or injuries that need immediate attention.
* Attendance - A visit by a patient to an A\&E department. One person may have multiple attendances over time.
* Type 1 Department - A major emergency department that is open 24 hours a day and can deal with a wide range of serious illnesses and injuries. This was previously labelled "ED" (Emergency Department).
* Type 3 Department - Usually a Minor Injuries Unit (MIU) or similar service providing treatment for less serious conditions. Opening hours and services may vary.
* Planned Attendance - An attendance arranged in advance, often following contact with NHS services such as Flow Navigation Centres.
* Unplanned Attendance - A patient attends A\&E without a pre-arranged appointment because urgent care is needed.
* Deprivation Quintile - A way of grouping neighbourhoods by levels of deprivation. Quintile 1 represents the most deprived areas and Quintile 5 the least deprived areas.







#### Unintentional Injuries



* Unintentional Injury - An injury that was not deliberately caused, such as a fall, accidental poisoning, burn or road traffic accident.
* Emergency Admission - A hospital admission that was not planned in advance and happened because urgent treatment was needed.
* Injury Type - The broad category describing what caused the injury, such as falls, poisoning or transport accidents.
* Injury Location - The place where the injury occurred, for example at home or elsewhere.
* Council Area - One of Scotland's 32 local authority areas, such as Glasgow City or Highland.
* Health Board - Regional NHS organisations responsible for planning and delivering healthcare services within a geographical area of Scotland.
* Health and Social Care Partnership (HSCP) - Organisations that bring together NHS and local authority services to coordinate health and social care for local populations.
* Calendar Year vs Financial Year - A calendar year runs from January to December. A financial year runs from April to March of the following year.
* Injury Types:

  * Falls - Injuries caused by a person falling from, on, or between surfaces. Examples include slipping on ice, tripping on stairs, or falling from a ladder.
  * Road Traffic Injury (RTI) - Injuries resulting from incidents involving vehicles on roads or land transport networks. Examples include car crashes, motorcycle collisions, bicycle accidents, and pedestrian injuries involving vehicles.
  * Poisoning - Injuries caused by exposure to harmful substances. This may include medicines, alcohol, household chemicals, gases, or other toxic substances taken accidentally.
  * Struck By, Against - Injuries caused by being hit by an object or person, or by accidentally colliding with an object. Examples include being hit by sports equipment, walking into a fixed object, or being struck by a falling item.
  * Crushing - Injuries where part of the body is squeezed, trapped, pinched or compressed between objects. Examples include fingers trapped in doors or injuries caused by heavy objects.
  * Scalds - Burn injuries caused by hot liquids, steam, or other hot substances. Common examples include spilling boiling water or hot drinks.
  * Other - Unintentional injuries that do not fit into any of the categories above.







#### Prescriptions



* Prescription Item - A medicine or appliance dispensed to a patient through an NHS prescription. One prescription form may contain several items.
* Dispensed - A medicine has been supplied to a patient by a pharmacy or other approved dispenser.
* Prescribing - The act of a healthcare professional authorising a medicine or treatment for a patient.
* BNF Chapter (British National Formulary Chapter) - A way of grouping medicines by the type of condition they are used to treat. For example, medicines for the heart, respiratory conditions, mental health, or infections are grouped into different chapters.
* Gross Ingredient Cost (GIC) - The cost of the medicine itself before dispensing fees or other adjustments are applied. Think of it as the basic cost of supplying the medicine.
* Paid Quantity - The quantity of medicine reimbursed by NHS Scotland, such as the number of tablets, capsules, millilitres or doses supplied.
* Dispensing Location - The pharmacy, dispensing practice or other location that supplied the medicine to the patient.
* Community Prescribing - Prescriptions supplied through community settings such as GP practices and pharmacies, rather than medicines provided directly within hospitals.







#### Further Information

* https://publichealthscotland.scot/
* https://www.opendata.nhs.scot/

