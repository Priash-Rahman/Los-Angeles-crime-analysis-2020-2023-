



# Los Angeles crime analysis (2020-2023)

### Dashboard Link : https://www.novypro.com/project/navigating-the-urban-landscape---decoding-los-angeles-crime-trends-2020--2023--power-bi

## Problem Statement

 This Power BI project is designed to offer actionable insights and support stakeholders and law enforcement agencies in making informed decisions based on a thorough analysis of Los Angeles crime data spanning from 2020 to 2023.
 Goal is to empower  the user, to navigate and pull insights tailored to user needs. Through a set of visually immersive dashboards across three main pages, user embark on an exploration of temporal crime patterns, uncover the top 10 crimes, and dive into a realm of interactive reporting for personalized, in-depth analysis.

 User-Centric Features :

**Explore Your Way: Navigate through monthly and yearly crime trends, dissect crime by time groups, weekdays, and months, all at your pace.

**Top 10 Crimes Unveiled: Peel back layers of data to reveal the top 10 crimes, allowing user to dynamically adjust parameters for a customized view.

**Interactive Reporting Playground: Engage with a detail-rich reporting page, where crime, weapon, and premises data become tools in users hands. User can slice & dice & mold the data by customizable filters.

 User interaction with the dashboards will uncover unique insights, allowing user to pinpoint high-crime timeframes and areas with ease. The ultimate aim is to arm user with the tools and knowledge to make strategic decisions and allocate resources effectively.﻿

### Steps followed 

- Step 1 : Load data into Power query , dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : Data normalization : Turned the flat schema dataset to star schema for comprehensive analysis .
- Step 5 : Calculated crime time from time occ column & also determined "Hour group" from crime time column afterwards  .
- Step 6 : Created a "Time group" column where 24 hour divided into 6 hour basis for crime analysis .

         -Time group : SWITCH(
       TRUE(),
       MOD(HOUR('fcrime data'[Crime Time]),24) >= 0 && MOD(HOUR('fcrime data'[Crime Time]),24)<=6, "12:00 AM - 5:59 AM" ,              
       MOD(HOUR('fcrime data'[Crime Time]),24) >= 6 && MOD(HOUR('fcrime data'[Crime Time]),24)<=12, "6:00 AM - 11:59 AM" ,              
       MOD(HOUR('fcrime data'[Crime Time]),24) >= 12 && MOD(HOUR('fcrime data'[Crime Time]),24)<=18, "12:00 PM - 5:59 PM" ,              
       MOD(HOUR('fcrime data'[Crime Time]),24) >= 18 && MOD(HOUR('fcrime data'[Crime Time]),24)<=24, "6:00 PM - 11:59 PM" ) 
        
- Step 7 : Catagorized crime nature into offensive & less offensive crimes   . 
- Step 8 : Catagorized age group into 6 sections . 
- Step 9 : Lead time range created from lead time ( 0-30 days / >30 days ) for gaining insights from lead time.
- Step 10: Date table created in power query & "Crime date occ " of fact table and date of date table was connected for time analysis . 
- Step 11 : Removed unnecessary columns & dealt with null, blank  for better analysis.
- Step 12 : Data prepared for analysis & loaded to power bi .
           
- Step 13 :DAX measures created for comprehensive & robust analysis and to create necessary kpi's .
           
           -Total Crimes(distinct count of crimes) .
           -Crimes reported  ( coutrows of fact table).
           -Crime prev month .
           -Crime %  .
           -% of filtered crime . 
           -Condition F month(Icon based on condition ).
           -Condition F year(Icon based on condition)
           -Lebel month .
           -Lebel year.
          

- Step 14 : As main goal was to focus on time 2 dashboard page created "Time analysis"& "Time details" & the last page focuses more on reporting.
          
          -Crimes by month  , year , crime by time group & crimes by month and weekday presented in time analysis along with dangerous crime hour & map chart . 
          -Time details focuses more on high/low time frame of crimes , where top 10 crimes was presented .
          -detail report focuses on crimes based on crime , premises , weapon along with victim by age group ,  in which user can slice & dice the data based on year , time hour .

- Step 15  : Power point template created for time analsis page .![Screenshot 2024-03-19 222148](https://github.com/Priash-Rahman/Los-Angeles-crime-analysis-2020-2023-/assets/155983828/b0bb77b2-9884-4db7-820a-f623fd2c59c8)



# #Dashboard
![Screenshot 2024-03-19 224609](https://github.com/Priash-Rahman/Los-Angeles-crime-analysis-2020-2023-/assets/155983828/cd59dacb-e7fd-48c2-b84b-a21d4c76e053)


![Screenshot 2024-03-19 224630](https://github.com/Priash-Rahman/Los-Angeles-crime-analysis-2020-2023-/assets/155983828/822eaa2b-ebfc-457b-8c9b-2af43b891f7c)


![Screenshot 2024-03-19 224656](https://github.com/Priash-Rahman/Los-Angeles-crime-analysis-2020-2023-/assets/155983828/1d422159-b190-4fb4-9e90-83da0f5f78c0)
