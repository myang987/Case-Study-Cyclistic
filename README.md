# CASE STUDY: Cyclistic Bike Trip Analysis
##### Author: Mike Yang

##### Date: December 30, 2022

##### [Tableau Dashboard](https://public.tableau.com/app/profile/mike3830/viz/CyclisticTripTracker/LandingPage)

##### [Data](https://divvy-tripdata.s3.amazonaws.com/index.html)

# Executive Summary
Cyclistic operates a bike-share program for consumers across Chicago. Launched in 2016, Cyclistic has grown to service a fleet a 5,824 bicycles that are geotracked and locked into a network of 692 stations. The bikes can be unlocked from one station and returned to any other station in the system anytime. 
Cyclistic offers a flexible pricing program for riders: single-ride passes, full-day passes, and annual memeberships. Customers who purchase single-rie or full-day passes are categorized as casual riders, and customers with annual memeberships are Cyclistic members. 

Cyclistic's current marketing strategy has relied on building general awareness and appealing to broad consumer segments, focusing on the flexible pricing plans to attract consumers. The company's financial analysts have concluded that annual members generate more profit than casual riders. Lily Moreno, director of marketing, is planning to create a marketing campaign that aims to convert existing casual riders into Cyclistic memebrs. Moreno believes that maximizing the number of annual members will be the key to future growth and sustainability. 

Guiding questions for the marketing campaign:
- *How do annual members and casual riders use Cyclistic bikes differently?*
- *Why would casual riders buy Cyclistic annual memberships?*
- *How can Cyclistic use digital media to influence casual rider sto become members?*

## Task
**_Generate insights into rider trends and help the marketing team better understand differences between casual riders and Cyclistic members._**

The objective of this case study is to describe the process, detail the findings of the analysis, and provide high-level recommendations for Cyclisic's marketing campaign. Focusing on converting casual riders into long term Cyclistic members; what are the major differences between casual riders and Cyclistic members?

# Process
## Tools
**Data Source:** AWS Cloud Storage<br />
**Original Format:** CSV<br />
**Data Storage:** Locally and on the cloud in Google Drive<br />
**Data Manipulation:** Python Jupyter Notebook<br />
**Data Visualization:** Python and Tableau<br />
**Reports & Documentation:** Google Doc<br />

## Data
The data was stored on the cloud in an AWS server in CSV format organized by various date ranges. Data uploaded after April 2020 were consistently organized by the month. Data prior to April 2020 were organized by varied time periods, from quarterly to yearly data.

<img src="/pictures/data_screenshot.png" alt="Data Storage Post 202004" height="253" width="500"/> <img src="/pictures/data_screenshot2.png" alt="Data Storage Pre 202004" height="283" width="500"/>
<sub>The storage organization change after April 2020</sub><br /><br />

The data recorded the user information, time, and geolocation data of Cyclistic customer's trips. The trips recorded the datetime and geo-coordinates of what station the trips began and ended at. 

## Complications
The data is a collection of timeseries data ranging from Jan 2013 to Dec 2022. The schema for the data varied but were consistent for periods of time. The most notable difference is the schema change pre and post 2020. 

| | | | | | | | | | | | | | |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Post-2020 Schema | ride_id | rideable_type | started_at | ended_at | start_station_name | start_station_id | end_station_name | end_station_id | start_lat | start_lng | end_lat | end_lng | member_casual |
| Pre-2020 Schema | trip_id | start_time | end_time | bikeid | tripduration | from_station_id | from_station_name | to_station_id | to_station_name | usertype | gender | birthyear |

After manually checking the schema of each CSV, the data was stored into seperate folders by schema. A program was then created to create seperate dataframes containing the data of each folder to be clean and merged in Python.

# Analysis
The goal of our analysis is the generate ideas on how to convert casual riders into annual members for a marketing campaign that targets the benefits of being an annual member. To do so, we need to first understand the differences casual riders and annual members, how these two demographics use the services differently.

### Tableau Dashboard
The findings of the EDA provided a general view of how Cyclistic's services are being used by customers. A visual dashboard helps further the analysis while providing a visual aid in understanding geographic coordinate data. <br />

<details>
    <summary>Click me</summary>
<ins>Dashboard Overview</ins><br />
  <img src="/pictures/dashboard_bot_V3.png" alt="Dashboard Map"/>
<br />
</details>

## Types of data:
The analysis is conducted on data acquired between January 2020 and November 2022 for a total of 14,270,395 points of data.<br />
The types of data available for analysis: <br />
**- Date (Month graph)** <br />
&emsp;Can be visualized in a Month vs Trip Volume graph.<br />
**- Time (Time of day graph)** <br />
&emsp;Can be visualized in a Time of Day vs Trip Volume graph<br />
**- Type of ride (Trip type graph)** <br />
&emsp;Can be visualized in a Ride Type vs Trip Volume graph<br />
**- Location (Geo-Map)** <br />
&emsp;Can be visualized through a geographic map.<br />


## Findings
Using the dashboard, we are able to visualize the data based on certain selected metrics:
- Trip Volume
- Average Trip Distance
- Average Trip Time
- Average Start Staion Capacity
- Average End Station Capacity
### Trip Volume
First we take a look at the trip volume trends over our time period (01/2020 - 11/2022). Cyclistic has seen steady growth in their trip volume for both members and casual-riders post-pandemic. Monthly trip volume has grown just over 30% over the course of the data; peak month trip volume rose from 621,423 in 2020 to 822,541 in 2022. <br />

On average, members use Cyclistic more compared to casual-riders, with the exception July 2021. Member trip volume has also grown at a slightly higher rate than casual-rider trip volume. <br />

From the time chart, trip volume surge during the warmer months and wanes during colder months. This is to be expected as the utility of a bicycle drastically diminishes in the event of cold or bad weather. <br />

The most popular ride type for annual members is the classic bike, 3.6M classic bike trips compared to 2.8M electric bike trips. Casual riders show no significant preference between classic bikes and electric bikes (2.1M vs 2.3M).

![Trip Volume over Time](/pictures/trip_time_ride-volume.png)
<br />

Closer Examination of monthly and hourly trends will reveal user patterns and preferences. <br />

The beakdown of trip volume throughout each month shows the popularity of bycicle services throughout the seasons. Both members and casual-riders show gradual growth in activity throughout Spring, reaching peak in summer, steap decline in Fall, and bottom in Winter. <br />

There are small, yet noticable, differences between members and casual riders: 
- Casual rider activity shows a steeper surge during the summer and an ealier peak than member activity.
- Member activity gradually increases in activity, peaking in August, while casual rider activity peaks in July. 
- Casual-rider activity exhibits a relatively consistent decline as compared to members. 
- Member activity experiences minimal declines after August until October, where then the trip volume drastically declines. <br />

These trends can be explained by the difference in trip motive between members and casual-riders.

**Hypothesis: Many casual-riders use Cyclistic for leisure while members use Cyclistic for commute.** 
<br /><br />
![Monthly Trip Volume](/pictures/trip_start-monthV2.png)
<br />

The graph below depicts trip activity levels of Cyclistic services throughout each hour of the day. The usage of Cyclistic services for annual members and casual riders are noticably different. Annual member activity have a higher spike during hours 6-9 and hours 15-19 (3pm-7pm), especially so during the morning session. Casual rider activity exhibits a gradual increase in volume throughout the day, peaking at hour 17 (5pm) before declining.

This trend further supports the previous hypothesis while providing more specific insights. The time period for spikes in trip volume coincides with commute times for a majority of the population. To summarize:
- Both annual members and casual riders use Cyclistic rental bicycles for work commute.
- Annual members commute with bicycles in the morning more often than casual riders. <br />

Further analysis is required to determine purpose of trip. Factors such as location and trip distance can help better determine the makeup of casual rider trips. 

**There is potential opportunity available for Cyclistic to convert casual riders to annual members through a marketing campaign focused on work commutes.**
<br /><br />
![Monthly Trip Volume](/pictures/trip_start_time-volume.png)
<br />

![Monthly Trip Volume](/pictures/top_stations-volume.png)
<br />

**<ins>Proportion of trips conducted by casual riders and annual members</ins>**<br />
![Distribution of membership](/pictures/member_percentage.png)

**<ins>Proportion of trips used by different types of bikes</ins>**<br />
![Distribution of bike type](/pictures/ride_type_percentage.png)

**<ins>Breakdown of ride type grouped by membership type</ins>**<br />
<img src="/pictures/member_ride_type_breakdown.png" alt="Ride Type by Membership" width="391" height="233"/>

### Date
**<ins>Customer traffic by month from 2020-01 to 2022-11</ins>**<br />
<img src="/pictures/ride_per_month.png" alt="Trips per Month" width="465" height="378"/>

### Time
**<ins>Customer traffic by hour of day</ins>**<br />
<img src="/pictures/ride_hour_of_day.png" alt="Trips per Hour of Dayh" width="468" height="329"/>

### Ride Type

### Location

## Limitations



# Recommendation

