# Kickstarting with Excel

## Overview of Project
The Kickstart data provided by the bootcamp was analyzed using Microsoft Excel for creating charts and presenting findings. 

## Purpose
This analysis was completed to find relevant information for fundraising regarding Louise's possible fundraising campaign. Specifially, the information regarding launch dates and fundraising goals for all campaigns in the dataset are summarized and visualised.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
<p>Data required to visualize the outcomes based on the launch date included the parent category (theater), outcomes (succesful, failed, or cancelled) and month of launch. Both parent category and outcome were readily available in the data while a conversion of the unix timestamp was necessary to retrieve the day, month, and year of the launch.
The formula,
<b>=(((A1/60)/60)/24)+DATE(1970,1,1)</b> was used to convert the unix timestamp to a usable format. These three parameters were made into a pivot table filtered by month showing campaign outcome totals for all theater campaigns. 
  
<img width="453" alt="Screen Shot 2022-06-15 at 8 05 53 PM" src="https://user-images.githubusercontent.com/106560606/173971174-f57ae23a-9f63-4c41-9346-3a4cad05035a.png">
 
The line graph titled "Theater Outcomes Based On Launch Date" was created from this pivot table. No issues were encountered with data during analysis.  </p>

### Analysis of Outcomes Based on Goals
The data needed for performing an analysis based on goals included goal amounts, and the number of succesful, failed, and canceled projects. The goal amounts were sorted into a range of dollar amounts for further detail.

<img width="145" alt="Screen Shot 2022-06-15 at 8 44 16 PM" src="https://user-images.githubusercontent.com/106560606/174194316-be02bf8a-165b-4ccc-9bfb-6fec123f2c00.png">

To retrieve this from the original spreadsheet, the COUNTIFS() function was used to filter by goal amount and outcome. 

<img width="598" alt="Screen Shot 2022-06-15 at 8 43 39 PM" src="https://user-images.githubusercontent.com/106560606/174194312-dcf3573b-9592-4fb4-8639-3eee7542aaf5.png">

This same formula was used, adjusting as necessary, to obtain this data for all campaigns. Once goal amounts and outcomes were sorted a count of all campaigns for each outcome (sucessful, failed, canceled) was completed using the SUM() function. Each goal was then assigned a percentage for the total of each outcome by simply dividing the individual amount of campaigns by outcome and goal by the total amount. The results had to be formated as a percentage for proper analysis. These results were then used in creating a pivot chart for visualizing the data. 


### Challenges and Difficulties Encountered
A potential issue could have happened during the outcomes based on launch analysis if it wasn't known that the serial number for the calendar dates was a unix time stamp. Without being able to convert the serial number, the analysis would have been impossible. 

A challenge arose during initial pulling of data from the Kickstarter sheet using the COUNTIFS() function. The returned information was not correlating correctly with the original data. After reaching out to classmates in Slack to confirm that others were not getting the same results, it was discovered that the incorrect column was choosen during writing of the initial formula that was then copied into other cells resulting in incorrect calculations. Once the correction was made to include the correct column, the formula produced the proper results. 


## Results

- <b>What are two conclusions you can draw about the Outcomes based on Launch Date? </b><br>
From charting the outcomes against the launch date it is clear that May has the highest number of sucessful campaigns launched during this month. It is also clear that October followed by November sees the highest amount of failed campaigns launched, however none were canceled in October. Ideally, one would launch a campaign in May or possibly June for the highest chance of success while avoiding October and November launch dates. 

- <b>What can you conclude about the Outcomes based on Goals?</b> <br>
The chart for outcomes based on goals provided a clear visulization for each goal amount range and outcome. The highest percentage of successful campaigns was seen at the "less than $1000" goal range. The highest percentage of failed campaigns was seen at the "$45,000 to 49,999" range. This informations tells us the first goal range would have the highest chance of success while the latter would have the lowest chance. 

- <b>What are some limitations of this dataset? </b> <br>
This data is only able to tell us goals, types of projects, dates, and outcomes based on campaign activity. We are not able to know anything about experience the campaign launchers have or any other resources they utilized during the fundraising that could have impacted the outcome. 

- <b>What are some other possible tables and/or graphs that we could create? </b> <br>
A chart comparing the average donation amounts per backer for each parent category could be helpful to understand where theater stands in terms of individual backer investment. Are they higher individually compared to the movie or tv show backers? 
A table showing the count of backers for each goal range would also be helpful in determining which goal amount would be ideal and how many backers would possibly be needed. 
