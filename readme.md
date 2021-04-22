# Ford Gobike Trip Data Analysis
## by Eman Khalaf


## Dataset

> The dataset contains comprehensive information about Gobike trips in the United States of America during February, 2019. I have downloaded the csv file of the dataset from a link provided by Udacity,
then I changed the working directory to the location where the file exists.
From the priliminary exploration, the dataset contained 183,412 records for bike trips with 16 features/variables including; 
duration_sec, start_time, end_time, start_station_id, start_station_name, start_station_latitude, start_station_longitude, end_station_id, end_station_name, end_station_latitude, 
end_station_longitude, bike_id, user_type, member_birth_year, member_gender, bike_share_for_all_trip). 9 out of the 16 features are numerical, whereas 7 are of object type. 
There are missing values in start_station_id, start_station_name, end_station_id, end_station_name, member_birth_year, and member_gender variables. However, there are no duplicates in any of the variables.
Hence, I did some data wrangling prior to exploratory analysis. These adjustments included the followings:
1- changing the datatype of start_time and end_time to datetime.
2- changing datatype of user type, gender and bike_share_for_all_trip to category
3- Dropping unneccessary variables from the dataframe (start_station_id, start_station_latitude, start_station_longitude, end_station_id, end_station_latitude ,and end_station_longitude).
   However, I kept the bike_id variable to use it as a counter for records in the downstream analysis, in particular it does not have any missing data.
4- I calculated the age of each member and added it into a new column; "member_age" to use it in the data analysis
5- I removed members aged >60 from the dataset since the majority of the members are between 20 - 60 years old. So records >60 are considered as outliers.
6- I Categorized members' age into 5
 age groups, then created a new variable to include the age group corresponding to each record.
7- I extracted the month name, weekday name, and hour from the start_time variable and created 3 new variables/columns to use them in data analysis.
8- I identified the top 10 frequent start station and created a new dataframe to include all the relevant information to them
 Eventually, After cleaning, the dataset now contains 170186 records with information for 15 different features/variables to include in the downstream analyses.

## Summary of Findings
- From data exploation, I found 8 interesting features to focus on through out the analyses. These variables are; trip duration, common weekdays for renting bikes,
  common day hour for renting bikes, age group of members, member gender, user_type of the service, and bike_share_for_all_trip variable, and the start_station_name variable.
- From data analysis, we found the followings:
1- The duration of the majority of bike trips were below 2000 seconds with a maximum value at approximately 400-600 seconds equivalent to 7-10 minutes.
   That means the majority of the service users are renting bikes for very quick trips.
2- Regarding the rental rate across weekdays, Thursday followed by Tuesday showed the highest rates of bike trips, whereas weekends had the lowest rates.
3- Bike rent starts to increase remarkably from 7 am to reach its maximum at 8 am, then declines gradually with a steady state within time interval 10am-3pm, 
   then starts to increase to reach the maximum rate again at 5pm then declines gradually. It seems that the rent rate reaches its maximum at times where members go to their work at early morning (7-9 am) 
   and leave at evening (4-6 pm).
4- Members in age_group 31-40 are the most frequent users of the service across weekdays followed by those within the age_group (21-30) years old. 
   That means young adults mostly employed are the main users of Gobike service.However, members in age group 21-30 have a little bit higher rate over the weekends, and 
   for other group, the rate is relatively consistent across the weekdays.
5- Members within age of late 20's and early 30's are the most frequent users of Gobike service, probably because they are freshly employed and bike share is the most economic means of transportation to commute to their workplace.   
6- Males are the most frequent users of Gobike service accounting for 74.3% of the total users, followed by far behind the females' category.
7- subscribers/members in the service constitute the majority of Gobike users.
8- The vast majority of users accounting for 90.2% of the total do not share bikes for all trips, that porobably due to the majority of trips are too short to share bikes.
9- The majority of subscribers use Gobike service for relatively shorter trips compared to customers.
10- The Market station at 10th street has the highest rate of bike trips as a start station. Furthermore, half of the top start stations are Market stations.
11- Only subscribers may or may not share the bike for all the trip, but all customers do not. In addition, most subscribers share the bike for all the trip for shorter durations compared to those who do not from the same group (subscribers).
12- There is a strong consistent correlation pattern across all of the heatmaps where the peak maximum of bike rental was at 8 am, and 5 pm on Thursday followed by Tuesday regardless to the age group. 
   Additionally, weekends showed the lowest usage of the service for all age groups.  

> Summarize all of your findings from your exploration here, whether you plan on bringing them into your explanatory presentation or not.
Based on the performed data analyses and visualizations, we conclude that Gobike rental system is mainly used for short bike trips, and the majority of users are male subscribers within age range between late 20's and early 30's. 
Noteworthy, official work hours are the most common time intervals where the service is used especially on Thusrdays and Tuesdays. However, weekends have the lowest rates.
Furthermore, market stations are the most frequent used start stations.

## Key Insights for Presentation
- Gobike sharing system is mainly used for short trips. 
- Males and females follow a consistent pattern of hourly use with peak maximum at official work hours. However, the majority of the service users are males.
- Members within age groups 20-30, and 30-40 are the most frequent users of the service across weekdays.
- Market stations are the most frequent start stations for bike rentals that are mostly shorter trips compared to other stations.
- Subscribers constitute the majority of users and they may/may not share the bike during the entire trip, however, all customers do not.
- Subscribers have consistent pattern of using Gobike service across age groups 20-30, 30-40, 40-50, along with weekdays.

> Select one or two main threads from your exploration to polish up for your presentation. Note any changes in design from your exploration step here.
The adapted heatmaps represent the correlation between age_group, weekdays, day_hours regarding the rate of bike share, and that is for only subscribers who constitute the majority of users.

List of resources used during the creation of the project:
 https://stackoverflow.com/questions/52753613/grouping-categorising-ages-column-in-python-pandas