# kickstarter-analysis

![alt text](https://en.wikipedia.org/wiki/Play_(theatre)#/media/File:Macbeth_(32280144787).jpg)

## Overview of Project

### Purpose
The purpose of the project was to look at data from crowdfunding campaigns to analyze trends and make conclusions based on outcomes (whether the campaign met it’s goals or not).   Specifically, the analysis was done to see the success or failure trends of plays in the theater category.  We ultimately wanted to look at how different campaign successes were based on launch dates and funding goals. 


## Analysis and Challenges
Analysis for this project was completed using the Kickstarter.xls spreadsheet downloaded from the UT Data Analysis Bootcamp website.

### Analysis of Outcomes Based on Launch Date
Using our Kickstarter spreadsheet (???????), Initially, we took the data and applied a conditional formatting to identify whether the outcome of the campaign was successful, failed, live or canceled.  We then used a ROUND() function to divide the pledge by the goal to determine the success of the event where, for example E34 is the pledge and D34 is the goal.  This would give us our percentage funded, ultimately telling us whether or not the project met it's goals.

=ROUND(E34/D34*100,0)

Next, we had to determine our launch date using a timestamp function that converted the given timestamp to a start date of the campaign.  This was accomplished by using the following code where (((J2525/60)/60)/24) divides the launched_at column by 60 (seconds), 60 (minutes), and finally 24 (hours) and adds it to the timesstamp date where DATE(1970,1,1) uses the DATE with the Unix stamp (1970,1,1) given with the dataset.  

=(((J2525/60)/60)/24)+DATE(1970,1,1)

Finally, after making all the calculation we needed for analysis, we careted a pivot table that shows outcomes on launch date by filtering on category and years , showing the relationship between the date created (start date of the campaign) and the total outcomes.  The pivot chart showing this analysis is below.

![alt text](https://github.com/austin020269/kickstarter-analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png)


### Analysis of Outcomes Based on Goals

### Challenges and Difficulties Encountered
The largest challenge for me was the breadth of data associated with the spreadsheet and keeping track of which data were the most vital for the analysis at what process.  Should I take on a project like this of my own in the future, I will be sure to keep the data set smaller and more manageable.   This file was only manageable in a .zip form and was very cumbersome to manage.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?

Analysis of Kickstarter data to identify trends
