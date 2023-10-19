---
layout: post
title: Rugby Statistics Dashboard
---

Using Power BI to visualise the statistics from international Rugby matches between 1871 and 2023.

### Building a Dashboard
After completing a couple of courses covering PowerBI on DataCamp, I wanted to use my new skills to put together a dashboard based on one of my interests. In this case, with the Rugby World Cup just around the corner, I used this as my primary focus and found a dataset on [Kaggle](https://www.kaggle.com/datasets/lylebegbie/international-rugby-union-results-from-18712022) which contained the results from multiple international rugby matches between 1871 to 2023. My dashboard tracks the number of wins for each country, and an overall snapshot of this can be seen below.

*Full Dashboard*
![full_dash]({{ site.baseurl }}/images/rugby/full_dash.png)

While building these visuals, a number of new columns and measures were created using **DAX** methodology - the most key of these being the calculation of the winning team, and whether these wins occurred at home or away.

### Exploring the Data
This dashboard contains a number of options to dig deeper into the data that is available, which in this case is the **number of wins** for each of the international teams available. Other than looking into each invidual country, a number of additional filters have also been added. Namely these are:
1. Year period over which to calculate the wins
2. Whether the win was part of a World Cup
3. Whether the win was while at home or away
4. The losing country / opposition

For example, the below image shows only the number of wins from 2000 onwards, to see these relationships in more detail.

*Wins between 2000 and 2023*
![2000_dash]({{ site.baseurl }}/images/rugby/2000_dash.png)

To drill down into the detail even more, it is also possible to select a specific country and look at only their wins in more detail. In the example below, we are looking at Scotlands wins over the period of 2000 to 2023.

*Scottish wins between 2000 and 2023*
![2000SC_dash]({{ site.baseurl }}/images/rugby/2000SC_dash.png)

The final example of filtering into the data is by selecting the opposition. In this case, as is shown in the below image, the dashboard is showing all the occasions between 2000 and 2023 when South Africa has been beaten. 

*South African losses between 2000 and 2023*
![2000vSA_dash]({{ site.baseurl }}/images/rugby/2000vSA_dash.png)

This shows that South Africa have suffered most of  their losses against New Zealand and Australia, with New Zealand having a particularly high number of away wins against them.

*This post has only shown a small proportion of the capabilities of this dashboard. Feel free to get in touch using any of the links below if you have any questions on this project, I would be happy to discuss in more detail!*