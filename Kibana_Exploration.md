## Kibana Exploration
Exploring Kibana Using Generated Data

This document will answer the following questions:
- Sample Data
- Unique Visitors Vs. Average Bytes
  - Is there anything that seems potentially strange about this activity?
  - Filter the data by this event. What is the timestamp for this event?
  - What kind of file was downloaded?
  - From what country did this activity originate?
  - What HTTP response codes were encountered by this visitor?
- Kibana Discover page
  - What is the source IP address of this activity?
  - What are the geo coordinates of this activity?
  - What OS was the source machine running?
  - What is the full URL that was accessed?
  - From what website did the visitor's traffic originate?
- Conclusion
  - What do you think the user was doing?
  - Was there anything that seems suspicious about this activity?
  - Is any of the traffic you inspected potentially outside of compliance guidelines?

The Kibana Exploration requires data to be observed, and to add data samples is needed to be used for any sort of observation. The images shows the process of adding the sample in addition to observing the data and answering questions during this observation of Kibana.

The following images are steps taken to add sample data for observation:

- Select Load a data set and a Kibana dashboard under Add sample data.
![/Images/Kibana_Exploration_Images/AddingSampleData.PNG](https://github.com/ShinHJP/Project-13/blob/main/Images/Kibana_Exploration_Images/AddingSampleData.PNG)

- Select Add Data under the Sample Web Logs data pane.
![/Images/Kibana_Exploration_Images/AddDataWebLog.PNG](https://github.com/ShinHJP/Project-13/blob/main/Images/Kibana_Exploration_Images/AddDataWebLog.PNG)

- Select View Data to pull up the dashboard.
![/Images/Kibana_Exploration_Images/InstalledSampleWebData.PNG](https://github.com/ShinHJP/Project-13/blob/main/Images/Kibana_Exploration_Images/InstalledSampleWebData.PNG)

- Sample Data Questions:
  - In the last 7 days, how many unique visitors were located in India?
  - Answer: 225
  ![/Images/Kibana_Exploration_Images/UniquevisitorsINIDA.PNG](https://github.com/ShinHJP/Project-13/blob/main/Images/Kibana_Exploration_Images/UniquevisitorsINIDA.PNG)

  - In the last 24 hours, of the visitors from China, how many were using Mac OSX?
  - Answer: 43
  ![/Images/Kibana_Exploration_Images/24hourUniqueVisitorChina.PNG](https://github.com/ShinHJP/Project-13/blob/main/Images/Kibana_Exploration_Images/24hourUniqueVisitorChina.PNG)

  - In the last 2 days, what percentage of visitors received 404 errors? How about 503 errors?
  - Answer:
    - 404 Error: 0%
    - 503 Error: 0%
  ![/Images/Kibana_Exploration_Images/24hourUniqueVisitorChina.PNG](https://github.com/ShinHJP/Project-13/blob/main/Images/Kibana_Exploration_Images/24hourUniqueVisitorChina.PNG)

  - In the last 7 days, what country produced the majority of the traffic on the website?
  - Of the traffic that's coming from that country, what time of day had the highest amount of activity?
  - List all the types of downloaded files that have been identified for the last 7 days, along with a short description of each file type.
