# CASE STUDY: Cyclistic Bike Trip Analysis
##### Author: Mike Yang

##### Date: December 30, 2022

##### [Tableau Dashboard](https://public.tableau.com/app/profile/mike3830/viz/CyclisticTripTracker/CyclisticTripTracker)

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
The analysis is conducted on data acquired between January 2020 and November 2022 for a total of 14,270,395 points of data.
## Types of data:


## Findings
**Proportion of trips conducted by casual riders and annual members**<br />
![Distribution of membership](/pictures/member_percentage.png)


**Proportion of trips used by different types of bikes**<br />
![Distribution of bike type](/images/ride_type_percentage.png)


**Breakdown of ride type grouped by membership type**<br />
![]()


**Customer traffic by month from 2020-01 to 2022-11**<br />
![]()


**Customer traffic by hour of day**<br />
![]()



## Limitations



# Recommendation

