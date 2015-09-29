---
layout: post
title: NYC Subway Traffic Analysis
---

![NYC Subway](/images/subway.jpg "NYC Subway")  

###Team:  
Don Perkus, John Winter, Michael Zhang, and myself (Sean Osier)

###Situation:  
- _**WomenTechWomenYes International**_ (_**WTWY**_), a hypothetical client, is a non-profit that aims to increase the participation of women in technology.  
- _**WTWY**_ uses "street teams" at entrances to subway stations as a significant portion of their fundraising efforts.  
- _**WTWY**_ engaged us to **optimize the effectiveness of their street teams**.  

###Recommendations:  
 1. **Optimal timing:** Weekday evenings  
 2. **Optimal locations:** Factoring in pure subway traffic volume, proximity to nearby tech startups (and specifically  startups founded by or focused on women), and relative neighborhood affluence, our top stations:  
   1. 34th and Herald Square  
   2. 42nd and Time Square  
   3. 34th and Penn Station  
   4. 42nd and Grand Central  
   5. 59th and Columbus  

###Report:  
<iframe src="https://drive.google.com/a/seanosier.com/file/d/0B90v2XyX9nIARzZiQWUtQ2E1R1k/preview" width="640" height="480"></iframe>

###Data:  
 - [NYC MTA Turnstile Data](http://web.mta.info/developers/turnstile.html)  
 - [Tech Startups Heatmap](http://www.1776.vc/reports/innovation-that-matters/)  
 - [Women Tech Startups Data](https://www.cbinsights.com)  
 - [Average Income by Manhattan ZIP code](http://zipatlas.com/us/ny/new-york/zip-code-comparison/average-income-per-person.htm)  

###Technologies:  
 - Python  
 - Pandas  
 - UNIX  
 - Github  
 - MATLAB  
 - Google Fusion Tables  
 - Excel  
 - Powerpoint  

###Methodolgy:  
 1. Scrape, clean, and roll up MTA turnstile data to the station level  
 2. Aggregate data over all stations, and determine optimal days of the week for street team deployment  
 3. Looking at just target days of the week, determine optimal time of day  
 4. Looking at just optimal time and days of week, determine top stations by volume and plot on map  
 5. Layer in the density of tech startups and plot  
 6. Layer in neighborhood affluence (average income) and plot  
 7. Determine a final "score" for each station by combining the three factors (pure station traffic volume, density of tech startups, and neighborhood affuence) using a weight for each based its relative importance  
 8. Rank the stations by overall "score"  

###Code:  
For more details checkout my [Github repository](https://github.com/sosier/NYC_Subway_Traffic_Analysis).
