



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

- Step 15  : Power point template created for time analsis page .
![Screenshot 2024-02-05 115338](https://github.com/Priash-Rahman/Los-Angeles-crime-analysis-2020-2023-/assets/155983828/9c5f108e-d761-42cf-a322-0472b616c934)

- Step 17 :  

- Step  18 :  Now that data visualization was completed its time to pull some insights or answer some of the business questions from management .  ![Screenshot 2024-01-23 225844](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/9962f569-c587-4538-837b-d888dd13f633)


  #### Step 19 : Answering business acumen .

## Question 1 : Which months are high revenue contributor & which months contributing to revenue decline ? Any influence to drive revenue high or low on precise periods ?


![Revenu lost    earn](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/f567245e-770a-4b92-b2c4-8f5db89fa976) 
![Screenshot 2024-01-23 230125](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/853fc8a0-f90d-4568-a3da-324361b6d987)

- We can clearly notice constant  revenue growth since february ; 
- where Jun-July-Aug pulling the highest revenue ;
- Similar pattern can also be noticed incase of revenue lost along with total revenue ;
- Avearage daily rate playing a chief role in both of the metrics , high avg daily rate pulling revenue high but at the same time it also playing key role for revenue decline.       

## Question 2 : Which months faces high cancelation(booking) ? Any driving factor  ?
        
![Screenshot 2024-01-24 113346](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/eda10c55-7929-418e-9ae1-9b00e6949444)

![Screenshot 2024-01-24 113407](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/76b7e068-93d6-4d30-a2a2-9d7a75497f8a)

- Cancelation trend going upwards since apr and making a constant impact till october 
- At the other end it clearly observed that avg daily rate has a upward trend till Aug .
- Avg daily rate has a key impact driving canceled booking over time !

## Question 3 : Whats the cancelation status across weekdays/weekends  ? 
 
![Screenshot 2024-01-24 133233](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/e47a4229-d84a-4bd7-8df0-aff4f3491e66)

![Screenshot 2024-01-24 140855](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/a0389cc1-04f0-45e9-b02b-82d3da25da66)

- High cancelation is occuring between thrusday to saturday accross all seasons !
 - Thu ,Fri & Sat contributing to 52% of cancelation accross weekdays .
 - Friday being the busiest day has highest booking canceled along with highest avg daily rate & high avg days in waiting.
 
 ## Question 4 : Seasons with high Cancelation rate ? Whats the scenario of avg daily rate accross seasons ?
 ![Screenshot 2024-01-25 105934](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/4b6b8439-6d5a-4937-9875-5805e3da2bdb)
![Screenshot 2024-01-25 110959](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/4de19ff0-72fa-4b15-8c50-82a00527e86d)
- Avg daily rate peaks in summer & spring as it is most demanding times for organization.
- At the same time we have high cancelation rate at summer & spring .
- Avg daily rate has a postive correlation with cancelation rate.
## Question 5 : Provide insights into lead time . Cancelation based on lead time & do avg daily rate has a correlation with lead time & also do certain customer has high lead time or low lead time  ?
![Screenshot 2024-01-25 115338](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/d95aaa6a-b492-470b-8c0b-f3f7e6bcbff2)

![Screenshot 2024-01-24 222656](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/6ffce9e2-2b8f-4bdf-8a9f-c4750e4bb9bd)

![Screenshot 2024-01-24 222630](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/bcca6438-592c-41ed-b3d3-948929cea9cc)
![Screenshot 2024-01-24 223218](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/8400870a-09c5-4c7c-a06b-cc4e5f79b7d2)
- Advance booking more than 30 days has high cancelation rate across seasons.
- Lead time has a steady relation with avg daily rate 
- Business travellers & solo travellers(friends&family) has high lead time compare to others customers and consequently have booking ratio of 69% & 74%
- Booking far in advance does increase the probability of cancellation ! 
## Question 6 : Provide insights of top revenue generating countries along with booking ratio , cancelation ratio , avg nights .
### ***For comprehensive analysis and view top 10 contries taken into consideration.
![Screenshot 2024-01-25 200039](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/a1a5ae33-def7-4c63-afd8-f677479e55cc)

![Screenshot 2024-01-25 195938](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/5da56f12-ea35-41f0-9e63-3caddee03a94)

![Screenshot 2024-01-25 195810](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/f4cf3ca3-a4c1-4b4b-9d86-4ba7b89bb288)

![Screenshot 2024-01-25 201838](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/7d01338e-c52b-4579-b4d0-2156095c2f93)
- Portogal , France, Great britain , Spain, Germany  are top revenue contributors .
- Top 5 countries holds 72% of transaction & 69% of total revneue & 68% of Successful booking combinedly .
- Despite high revenue , booking , transactions portugal has the highest canceletion rate !
## Question 7 : Days in waiting list & failed to book desired has any impact on canceletion ? 
     *Yes = Got the desired room  ; *No = didn't get the desired room ; *No count(Dax)= Count of failed to get the desired room.

![Screenshot 2024-01-25 213434](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/e33e76ec-0623-4cdf-8713-0308574bbe34)


![Screenshot 2024-01-26 212031](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/4c277f66-acf5-4d72-a3f2-e5a12fba5fd6)
![Screenshot 2024-01-27 115051](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/7e54322a-08a3-4818-8ad5-3fc732338069)
- Most of the cancelation came from "Yes" . So this doesnt have an impact on cancelation rate .
- On customer basis solo & solo(friends/family) have failed to book their desird room ,almost 98% of fail to get desired room fall in these customer catagory.
- maximum of transaction,canceled booking occurred in short waiting time or between 0-2 days , even though 64% of booking falls in long waiting time have'een canceled .
- Fail to get desired room &  long waiting list to reserve doesnt have any significant impact on canceletion . 
## Question 8 : Provide insights into distribution channel based on booking ratio, avg nights , No counts , lead time .

![Screenshot 2024-01-27 133101](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/cb5daa00-21e9-493a-b8e3-917fe7aaba28)
![Screenshot 2024-01-27 140022](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/6fd0c7b6-79ce-487d-a95b-7de49d4b9ebb)
- Booking ratio or reservations are more Successful when people are booking via direct , GDS(global distribution system) & corporate agencies .
- Though travel agencies / travel operator remain top gateway for revenue flow but it has high rate of depriving customer getting their desired room icluding high waiting in list & lead time!


# #Dashboard
![Screenshot 2024-01-27 152030](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/8f96d5cb-335b-4f30-8d20-dbfe5821428b)
![Screenshot 2024-01-27 152052](https://github.com/Priash-Rahman/Hotel_booking_-analysis-_Project/assets/155983828/6647bba6-b091-41db-93bc-4c5e883687f4)

 #          *Recommendations*
 ## Optimizing peak season revenue 
  Place a greater emphasis on encouraging early bookings, as it has been identified that advanced reservations correlate with a higher probability of cancellation.
Early bird benefits include superior property and room type selections, increased flexibility in availing discounts and offers, and enhanced cancellation and re-booking options.
   - A strategic adjustment in ADR during peak times can serve as a powerful incentive, positively impacting customer attraction and mitigating cancellation rates, as observed during the project analysis.

   ## Early booking emphasis 
 - Place a greater emphasis on encouraging early bookings, as it has been identified that advanced reservations correlate with a higher probability of cancellation.
  - Early bird benefits include superior property and room type selections, increased flexibility in availing discounts and offers, and enhanced cancellation and re-booking options.
  ## Tailoring Strategies for Portugal
   - In-depth analysis reveals Portugal as a singularly prominent revenue contributor with notable transaction volumes, albeit facing challenges related to high cancellation rates.
   - Tailor promotional offers and policies specifically for the Portuguese market, providing customized flexibility to address their distinct patterns of engagement.
   ## Focusing resort at summer 
  - Direct marketing efforts towards resort hotels during the summer season, leveraging promotions, exclusive deals, and special offers to capture the attention of potential customers seeking leisure and recreation options.
  ## Strategic collaboration with travel operators 
  - Concentrate efforts on collaborations with both online and offline travel operators (TOs), negotiating more favorable terms and exclusive offers to secure a larger share of the market.
  - Explore mutually beneficial partnerships that provide TOs with enticing cut deals, further amplifying the reach and appeal of the hotel's offerings.
  ## strategic over booking in peak season 
  - Implement a strategic overbooking approach during peak seasons to counteract cancellation rates.
  ## customer experience 
  - Including adjusting adr a more effective strategy is to add Value to our "guests stay "
  - special packages , unique experience or additional services .
  - By offering added value we can attract guests with least change into adr , which not only helps increasing bookings but also lead to guest satisfaction leading to positive reviews & repeat business .






 
