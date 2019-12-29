---
authors:
- admin
categories:
- Post
date: "2019-12-15T00:00:00Z"
draft: false
featured: ture
image:
  caption: ''
  focal_point: ""
  placement: 2
  preview_only: false
lastmod: "2019-12-15T00:00:00Z"
projects: []
subtitle: 'The magic of data science with Python'
summary: 
tags:
- Web Crawling
- Folium
- Data imputation
- Foursquare solutions
- K mean Clustering
title: 'Exploring Sydney Suburbs for Opening A New Restaurant'
---

I have been studying the [IBM Data Science course](https://www.coursera.org/professional-certificates/ibm-data-science) from Coursera for the past several months. After learning all essential skills and tools in Python for this course, here comes the final assignment. The goal of this assignment is to define a business problem related to the city of my choice and then solve it by using the [Foursquare](https://foursquare.com/) location data.

Although this is an assignment, it closely resembles a real-world problem in which a data analyst would be required to solve in his/her daily job, which involves **problem definition**, **data collection**, **data cleaning**, **data analysing**, **data visualisation**, and **report forming**. Throughout the assignment, I used web-crawling, missing value imputation, Foursquare API, Folium map and k-mean clustering.
I hope you will either gather information or find useful data from this post. Please feel welcome to leave any suggestions and comments. Detailed codes/notebooks/data can be also found [here](https://github.com/Perishleaf/applied-data-science-capstone).

### 1. BUSINESS PROBLEM
You are working in a boutique consulting firm specialised in Restaurant Marketing. A client is looking to open a new **Italian restaurant** in Sydney, however, he is not sure about the best location and marketing strategy for his new venue. You have been assigned to help him to develop a comprehensive marketing program. Sydney is a vibrant city that shines all year with spectacular events. It is best known for its tourist attractions and idyllic beaches. Strolling around the city suburbs, it hardly find a clean niche to open up a new restaurants among established competitors without a data-driven methodology. How would you advise your client in deciding his restaurant location using data science?

### 2. DATA COLLECTION/CLEANING
Synthesised from *Start Your Own Restaurant and More: Pizzeria, Coffeehouse, Deli, Bakery, Catering Business* published by [Entrepreneur Press](https://www.entrepreneur.com/article/73384), the following components are deemed as key factors in selecting restaurant location: demographics, traffic density, crime rates, competitor, and property affordability. We may not be able to solve all these factors in such a short period of time, however, some of these considerations could be addressed by using available public datasets or web-scraping.

#### 2.1 Web-crawling Sydney suburb list from Wikipedia
Since the whole analysis is location-based, we should consider having detailed coordinates for all suburbs in Sydney. It is not hard to find the geojson file for all suburbs in NSW from the [government website](https://data.gov.au/dataset/ds-dga-91e70237-d9d1-4719-a82f-e71b811154c6/details). But, the challenge is to select those suburbs within Sydney metro area? Here, I used web-crawling method to scrap a list from Wikipedia using `requests` and `Beautifulsoup4`.
