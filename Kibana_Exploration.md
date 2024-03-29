## Kibana Exploration
Exploring Kibana Using Generated Data

This document will answer the following questions:
- Sample Data
- Unique Visitors Vs. Average Bytes
- Kibana Discover page
- Conclusion

The Kibana Exploration requires data to be observed, and to add data samples is needed to be used for any sort of observation. The images shows the process of adding the sample in addition to observing the data and answering questions during this observation of Kibana.

The following images are steps taken to add sample data for observation:

- Select Load a data set and a Kibana dashboard under Add sample data.
![/Kibana_Exploration/AddingSampleData.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/AddingSampleData.PNG)

- Select Add Data under the Sample Web Logs data pane.
![/Kibana_Exploration/AddDataWebLog.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/AddDataWebLog.PNG)

- Select View Data to pull up the dashboard.
![/Kibana_Exploration/InstalledSampleWebData.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/InstalledSampleWebData.PNG)

### Sample Data Questions:
  - In the last 7 days, how many unique visitors were located in India?
  - Answer: 225
  ![/Kibana_Exploration/UniquevisitorsINIDA.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/UniquevisitorsINIDA.PNG)

  - In the last 24 hours, of the visitors from China, how many were using Mac OSX?
  - Answer: 43
  ![/Kibana_Exploration/24hourUniqueVisitorChina.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/24hourUniqueVisitorChina.PNG)

  - In the last 2 days, what percentage of visitors received 404 errors? How about 503 errors?
  - Answer:
    - 404 Error: 0%
    - 503 Error: 0%
  ![/Kibana_Exploration/Last2days_404_503_errors.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/Last2days_404_503_errors.PNG)

  - In the last 7 days, what country produced the majority of the traffic on the website?
  - Answer: China

  ![/Kibana_Exploration/Heatmap.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/Heatmap.PNG)
  ![/Kibana_Exploration/Request map.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/Request%20map.PNG)

  - Of the traffic that's coming from that country, what time of day had the highest amount of activity?
  - Answer:10 AM and 1 PM

  ![/Kibana_Exploration/Hour10ChinaHEATMap.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/Hour10ChinaHEATMap.PNG)

  - List all the types of downloaded files that have been identified for the last 7 days, along with a short description of each file type.
  - Answer:
    - gz: .gz is and archive file compressed, created using the gzip compression utility.
    - css: .css cascading style sheet, defines the graphical interface of HTML information on a webpage. They are downloaded with their .html counterparts and rendered by the browser.
    - zip: An archive compression format file. A .zip file may contain one or more files or directories that have been compressed.
    - deb: A file with the .deb file extension is a Debian (Linux) Software Package file. These files are installed when using the apt package manager.
    - rpm: .rpm file formats are a Red Hat Software Package file. RPM stands for Red Hat Package Manager.

    ![/Kibana_Exploration/Download_types.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/Download_types.PNG)

### Unique Visitors Vs. Average Bytes

![/Kibana_Exploration/Unique_Visitors_vs_Average_Bytes.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/Unique_Visitors_vs_Average_Bytes.PNG)

  - Most Bytes within the last 7 days, Is there anything that seems potentially strange about this activity?
  - Answer: The results seems strange as there is 2 visitors that is using most of the bytes, this is much higher then other usage.

  ![/Kibana_Exploration/highestbytecount.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/highestbytecount.PNG)

  - Filter the data by this event. What is the timestamp for this event?
  - Answer: The time: Mar 27, 2021 @ 18:00:00.0 - Mar 27, 2021 @ 21:00:00.0 The time stamp is 20:35

  Filtered the two counts
  ![/Kibana_Exploration/2uniquevisitorsHighusage.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/2uniquevisitorsHighusage.PNG)

  Filtered Time
  ![/Kibana_Exploration/Highusageby2visitors_FilteredTime.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/Highusageby2visitors_FilteredTime.PNG)
  ![/Kibana_Exploration/Isolated2vistorshighusage.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/Isolated2vistorshighusage.PNG)

  - What kind of file was downloaded?
  - Answer: zip file

  ![/Kibana_Exploration/UniqueVisitorDownloadType.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/UniqueVisitorDownloadType.PNG)

  - From what country did this activity originate?
  - Answer: Algeria and Brazil

  ![/Kibana_Exploration/UniqueVisitorsMap.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/UniqueVisitorsMap.PNG)

  - What HTTP response codes were encountered by this visitor?
  - Answer: HTTP Code: 200 -100%

  ![/Kibana_Exploration/UniqueVisitorHTTPCode.PNG](https://github.com/ShinHJP/Project-13/blob/main/Images/Kibana_Exploration/UniqueVisitorHTTPCode.PNG)

### Kibana Discover page
    ![/Kibana_Exploration/KibanaClientIP.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/KibanaClientIP.PNG)

  - What is the source IP address of this activity?
    Answer: 	86.158.95.250

  - What are the geo coordinates of this activity?
    Answer: {"lat": 33.12936111,   "lon": -94.97563889}

  - What OS was the source machine running?
    Answer: Windows XP

    ![/Kibana_Exploration/KibanaClientURL.PNG](https://github.com/ShinHJP/Project-13/blob/main/Kibana_Exploration/KibanaClientURL.PNG)

  - What is the full URL that was accessed?
    Answer: https://www.elastic.co/downloads/beats

  - From what website did the visitor's traffic originate?
    Answer: gregory-linteris
    http://www.elastic-elastic-elastic.com/success/gregory-linteris
##Conclusion
  - What do you think the user was doing?
    Answer: The user was downloading the beast logs

  - Was there anything that seems suspicious about this activity?
    Answer: This activity seems to be suspicious due to the large bytes that was being used. But this activity is also due to the fact that there could have been a large number of logs being downloaded

  - Is any of the traffic you inspected potentially outside of compliance guidelines?
    Answer: The compliance, logs are being downloaded unless we understand the full reason on this being downloaded this is in compliance where this logs being downloaded is being reviewed.   
