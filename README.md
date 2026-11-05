# Rwanda Parks Visitor and Permit System 🇷🇼🐘

Course: INSY 8311 – Database Development using PL/SQL
Institution: Adventist University of Central Africa (AUCA)
Lecturer: Eric Maniraguha
Year: 2026-2027, Semester I
---

Name: Yannick Credo MUSEMAKWELI
id: 29343
GitHub: https://github.com/yannick129/yannick_29343_rwandaParkPermits
---

##  Problem
In recent years there has been an increase in tourism to Rwanda’s main nature reserves (Volcanoes, Akagera and Nyungwe National Parks). 
However, this has caused issues with their booking system which is currently inefficient and not automated. 
This causes issues with them accidentally booking the same number of visitors each time. 
They are also unable to keep track of the visitors coming into the park each day in an efficient manner to ensure they are not exceeding the capacity of the environment.
Additionally, they have a complex cash flow system. A relational database needs to be created to avoid them exceeding their daily limit of visitors.
---

##  Solution
An automated backend database using Oracle PL/SQL will be created to manage the parks. This will allow for visitors to be recorded, permits issued and visitors entering each day to be recorded. This database will contain business logic such as not issuing permits once the daily limit has been reached for gorilla trekking. This has been implemented using PL/SQL triggers. The backend will automatically calculate the cost of permits depending on the tier and citizen of the visitor.
---

## 📊 Data
Simple data relating to the parks capacity and macro-economic data relating to tourism has been taken from official sources:
Source: NISR Tourism & Transport statistics
Link: https://statistics.gov.rw/statistical-publications/ict-water-sanitation-energy-tourism-and-transport/tourism-transport
This data has been used to populate the tables within the relational database.
---

##  Tables
NATIONAL_PARKS – contains information about the National Parks, locations and capacity per day.
VISITORS – contains information about visitors including credentials, passport details, contact details and what category they fall into (Local citizen, EAC resident, Foreign tourist).
PERMITS – contains information about permits, when they were booked, timeslot and status.
REVENUE_LOGS – contains information regarding the financials, cost of permits and overall revenue raised.
AUDIT_LOGS – contains information about the administrative actions, override bookings and audits.
---

##  PL/SQL
Stored Procedures – sp_issue_permit allows new visitors to be booked, checks if permits are available and calculates what tier they fall into.
Functions – fn_check_daily_capacity calculates how many permits are left available for any park on a certain date.
Triggers – trg_prevent_overbooking (row level trigger) prevents inserting any more than the daily limit by raising an application error.
Packages – pkg_park_management contains procedures, cursors and custom exceptions.
---

##  Innovation
Type of innovation: UI (Streamlit)
Language/Tool: Python using Streamlit and native Oracle drivers (oracledb).
This allows staff and rangers within the parks to easily manage bookings and view the capacity using visual indicators. It provides a dashboard showing real time revenues.
---

##  References (APA)
Mugabo, J., & Uwase, C. (2023). Digitalising Wildlife Reserves: Challenges with Eco-Tourism in East Africa. Journal of Environmental Informatics, 14(2), 45-58.
National Institute of Statistics of Rwanda (NISR). (2023). Tourism and Transport Statistics. Statistical Publications. Available from: https://statistics.gov.rw
Oracle Corporation. (2024). Oracle Database PL/SQL Language Reference & Developers Guide. Oracle Documentation. Available from: https://docs.oracle.com
World Bank. (2024). Rwanda Economic Update: Tourism Sector Resilience & Conservation Funding. World Bank Group. Available from: https://data.worldbank.org
