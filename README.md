Agustin Lew

#  A1. Data Curation

## Introduction
The goal of this project is to construct a dataset of monthly traffic on English Wikipedia from January 1, 2008 through August 30, 2019 while focusing on documentation and reproducibility. 

## Data
The json datasets were obtained using two Wikimedia API endpoints, the Legacy Pagecounts API and the Pageviews API. Detailed documentation of these APIs can be found at https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts and https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews. The content accessed via these APIs is licensed under the CC-BY-SA 3.0 and GFDL licenses. The terms of use of the Wikimedia Foundation REST API can be found at  https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions.
The legacy json datasets contain information such as the type of access, the year and month, and the number of visits to the English Wikipedia website. The json datasets obtained from the Pageviews API contain additional information, such as whether the user was a person or a crawler.
The resulting csv file, named en-wikipedia_traffic_200801-201809.csv, contains the following features: year, month, pagecount_all_views, pagecount_desktop_views, pagecount_mobile_views, pageview_all_views, pageview_desktop_views, and pageview_mobile_views. Features containing ‘pagecount’ were obtained from the Legacy Pagecount API and features containing ‘pageviews’ were obtained from the Pageviews API. Desktop views refer to users who access the website with a computer, and mobile views refer to users who access the website with their smartphones. And ‘all_views’ is calculating by adding desktop views and mobile views.

## Software and modules
Python 3.7.3

Matplotlib 3.0.2

Numpy 1.16.2

Pandas 0.24.2

Requests 2.21.0

## Issues
The data obtained from the Legacy Pagecounts API does not differentiate between human users and web crawlers. In consequence, the number of page views is inflated when compared to the data obtained from the Pageviews API. This issue can be seen when the data from the two APIs overlap, showing a gap between the number of total views in the same time period.
