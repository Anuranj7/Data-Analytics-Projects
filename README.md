Google Data Analytics Capstone project.
Citibike Trip Data Case Study

For the final capstone project, I have selected the citibike trip data bike share analysis case to work on. I have selected data from the past 12 months for this project (from May 2021 to April 2022). For this case study, I will perform the real-life tasks of a data analyst for the marketing team at citibike, a bike-share company.

To answer the key business questions, I followed the six steps of the data analysis process: Ask, Prepare, Process, Analyze, Share and Act.

Detailed documentation of code is available in GitHub.

Initial analysis of datasets done using Microsoft Excel.

Data cleaning, validation and exploration using Google Big Query.

Data Visualization made using Tableau Public and Microsft Power Bi.

Background of the Study

Citibike:

In 2016, launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are geo tracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime.

Lily Monero:
The director of marketing and responsible for development of campaigns and initiatives to promote the bike-share program.

1. Ask
Identify the business task:
Strategy to maximize the number of annual memberships by converting casual riders into annual riders.

Consider key stakeholders:
Lily Monero & the Executive team

Stakeholder perspective:

Monero believes company’s future success depends on maximizing the number of annual memberships. She believes rather than creating a marketing campaign targeting all new customers, there is a very good chance to convert casual riders into members

Questions to Analyze:

How do annual members and casual riders use Citibike bikes differently?
Why would casual riders buy Citibike annual memberships?
How can Citibike use digital media to influence casual riders to become members?

2. Prepare
Data Source:

Past 12 month of bike share dataset from 01/05/2021 to 30/04/2022 were extracted as 12 zipped .csv files. The data is made available and licensed by
Motivate International Inc.

Data Organization & Description:

File naming convention: tripdata_YYYYMM
File Type: .csv
File Content: Each excel files contains 13 columns containing information related to ride id, ridership type, ride time and location and location etc.

Data Security:

Riders’ personal identifiable information is hidden through tokenization.
Original files are backed up in a separate folder.

Data Limitations:
As riders’ personal identifiable information is hidden, thus will not be able to connect pass purchases to credit cards numbers to determine if casual riders live in the Citibike service area or if they have purchased multiple single passes.

3. Process

Tools I have selected for data verification and cleaning:

Original files are backed up in a separate folder.
Microsoft Excel
Google Big Query
Tableau Public

Reasons:

By scanning through data in Excel worksheet, the general outline and basic information can be found which enabled me to familiarize with the dataset. I was able to perform simple check on formatting, missing information, sorting and filtering from the spreadsheet as well. Thus, Google Big query is used to perform such task. Big query will be also used to extract and generate new table for information which will be used for data visualization via Tableau Public. Initial assessment on the dataset Using Microsoft Excel.

Although the data have some missing, incorrect and unknown information prior to cleaning for a quick analysis i have used the total rows of each sheet to find the total number of rides per month and plot using a line chart to show the trend over time. The data showed that the number of trips peaked in September 2021 and dropped to the all time low in January 2022, which might have correlated with seasonal changes. During winter from from November to January there is steady decline the number of rides per month.


Initial analysis of total number of rides taken on each month
Initial data verification and cleaning was dome using Microsoft Excel

● Verified individual columns for the assigned data
● Checking for invalid/incorrect/unusable data, remove them if neccessary.
● Created a new column named ride length which calculates the length for each ride.
● Created another column named day of week to calculate the day of the week.
● Some columns contained empty cells and incosnsistent data which i cleaned using the filter function in excel.

1. By using the filter function, inconsistent data in the ride_id column is found. standard ride_id contains 16 characters. Removed rows that does not contains 16 characters to make the ride_id column consistent.

Data Cleaning and Data Manipulation using Google big query

I started with combining 12 data sets into one. For the first query, I used the UNION command, to combine 12 month datasets from may 2021 to april 2022 form a yearly dataset.

By going through the combined dataset, NULL strings shows up from column start_station_name to end_lng. These rows of data are considered to be incomplete therefore should be removed.


Null strings cleaned using the IS NOT NULL command
Next, I proceed to aggregate the data. Used CASE clause is used to convert day_of_week into different strings from Monday to Sunday, and by using EXTRACT function extracted DAY,MONTH, SEASON and YEAR from started_at column.Then used the TIMESTAMP_DIFF function to find the ride time in minutes.


4. Analysis and Visualization

Now the data is clean its time to answer the questions.

To analyze my data I used google bigquery platform to run to sort, filter and aggregate data. After the analysis I imported the results in to csv file format to create visualizations in Tableau. My bigquery sql analysis can be found here (Github), and my Tableau visualizations can be viewed here
(Tableau).

A snapshot a the queries can be seen here.


A summary of analysis I did is as follows

1. I started by finding the total number rides from each starting stations.

2. Calculated the total number of rides by ride type to find which type of members undertook most rides during the time.

3. I then proceeded to calculate the amount rides per month, per day, and per season and by per hour and grouped by member type.

4. To get a full view of the picture calculated the average ride length.

5. Then Idecided to check for the most prefered starting station, and end station for each rider type.

Main Insights

1. I started by analyzing the total number of rides taken by each member types.


2. I then analyzed the total number of trips taken by each member types by month.


3.From these findings, we can begin to assumethat annual members use citibikes for commuting purposes as their ridership levels peak during the evening from 4pm to 6pm. Furthermore, annual member ridership levels show less of a trend of dropping in the winter months in comparison to casual members. Thus, we can also assumethat casual members use citibikes more for leisure purposes.

To further test this hypothesis, I then analyzed the ridership levels per day of the week and by the average ride time (in minutes)


Both of these insights strongly support our hypothesis and we can conclude that annual members are typically commuters using citibikes for short trips during the weekdays to get to work and casual riders typically use Cyclistic’s bikes on the weekend for leisure.

Now let’s dive deeper and look at a map with the starting locations of the bike trips plotted. The bike trips are grouped by member type.


Summary of Insights
Casual Riders: Tend to use the Cyclistic bikes for leisure; preferring to ride during the midday hours on the weekend, concentrated in the late spring and early summer months. Their average ride time is around longer than annual members. Tend to start and end their trips near the water, city parks, and other tourist and recreational attractions.

Annual Members: Tend to use the Cyclistic bikes for commuting; preferring to ride all-year-round on the weekdays, with a drop off in the winter months, and during peak work commuting times (4pm/6pm).Tend to start and end their trips in the city, near office and apartment buildings.

Act/Recommendations

Having defined the differences between casual riders and annual members, the marketing department can start to develop its strategy of converting casual members to annual members.

Issue: A large percentage of the casual rider are most likely tourists visiting the city who cannot be converted into annual members. However, I have developed some
recommendations for converting city residents who are casual members
into long-term members:

Citibike could offer a new subscription plan targeted at different seasons and offer unlimited rides during spring and winter at a offer price. Citibike
would offer unlimited use of bikes on weekdays. The advertising campaign should be run in the summer months in order to attract the most attention. Furthermore, informational and promotional booths can be set up on weekends near the most popular starting and ending stations for casual riders.
