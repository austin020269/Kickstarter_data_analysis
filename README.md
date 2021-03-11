# kickstarter-analysis

## Overview of Project

### Purpose
The purpose of the project was to look at data from crowdfunding campaigns to analyze trends and make conclusions based on outcomes (whether the campaign met it’s goals or not).   Specifically, the analysis was done to see the success or failure trends of plays in the theater category.  We ultimately wanted to look at how different campaign successes were based on launch dates and funding goals. 


## Analysis and Challenges
Analysis for this project was completed using the Kickstarter.xls (https://github.com/austin020269/kickstarter-analysis/blob/main/Kickstarter_Challenge.zip) spreadsheet downloaded from the UT Data Analysis Bootcamp website.

### Analysis of Outcomes Based on Launch Date
Using our Kickstarter spreadsheet, Initially, we took the data and applied a conditional formatting to identify whether the outcome of the campaign was successful, failed, live or canceled.  We then used a ROUND() function to divide the pledge by the goal to determine the success of the event where, for example E34 is the pledge and D34 is the goal.  This would give us our percentage funded, ultimately telling us whether or not the project met it's goals.

=ROUND(E34/D34*100,0)

Next, we had to determine our launch date using a timestamp function that converted the given timestamp to a start date of the campaign.  This was accomplished by using the following code where (((J2525/60)/60)/24) divides the launched_at column by 60 (seconds), 60 (minutes), and finally 24 (hours) and adds it to the timesstamp date where DATE(1970,1,1) uses the DATE with the Unix stamp (1970,1,1) given with the dataset.  

=(((J2525/60)/60)/24)+DATE(1970,1,1)

Finally, after making all the calculations we needed for analysis, we created a pivot table that shows outcomes on launch date by filtering on category and years, showing the relationship between the date created (start date of the campaign) and the total outcomes.  The pivot chart showing this analysis is below.

![alt text](https://github.com/austin020269/kickstarter-analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png)


### Analysis of Outcomes Based on Goals
Because we were specifically interested in the plays subcategory, we used a COUNTIFS() function to calculate play outcomes based on goals for 12 categories from $0 to greater than $50,000 as shown in the table below.  In this table, we filtered our data on outcomes, goals and the “plays” subcategory using our COUNTIFS() function.  We also used the SUM() function to get the total number of projects in each goal category.  Finally, the percentages of successful, failed, and canceled projects were calculated based on the data from the "Total Projects," "Number Successful," "Number Failed," and "Number Canceled" columns.  

=COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$D:$D, "<1000",Kickstarter!$R:$R,"plays")

![alt text](https://github.com/austin020269/kickstarter-analysis/blob/main/Outcomes%20Based%20on%20Goals%20Table.PNG)

We finally created another a chart that showed the percentage successful, failed or canceled versus the goal amount ranges as seen below.


![alt text](https://github.com/austin020269/kickstarter-analysis/blob/main/resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered
The largest challenge for me was the breadth of data associated with the spreadsheet and keeping track of which data were the most vital for the analysis at what process.  Should I take on a project like this of my own in the future, I will be sure to keep the data set smaller and more manageable.   This file was only manageable in a .zip form and was very cumbersome to manage.

## Results
With any analysis there are conclusions that can be drawn from the project.  When looking at the Theater Outcomes by Launch Date chart we can see that the theater industry thrives at the beginning of the summer, in the months of May and June.  This might be expected with more favorable weather conditions and children taking their summer leave from school, allowing families the opportunity to exit their normal routines and get out and enjoy themselves.  Additionally, this graph shows that failed and canceled theater campaigns are relatively steady throughout the year while successful campaigns are highly influenced by the time of the year.  Finally, it shows that even successful theater campaigns begin to fail at the end of the year.  This again might indicate that families begin to stay at home more during colder weather months or decide to focus their money more for holiday expenses.

Similarly, conclusions can be drawn from the Outcomes Based on Goals chart.  One conclusion might be that failed projects exceed the successful projects percentage goals between $19,999-$39,999.  Failed projects also begin to exceed their goals at $45,000 while successful projects begin to fail at their goals.  Finally, one could conclude that campaigns in general are more successful when their goal value is less than $20,000.

### Data Limitations
The dataset does take into account the country location but not the individual venue location for the event (specific location the event is taking place).  Being from Austin, TX, which is the music capital of the United States, I know this to be true.  For instance, a certain bar might be more popular than another location and therefore more likely to have a larger crowd in attendance.  This leads to the outcome of the event and influence the overall success of the campaign.  Other cities, states and countries would have similar situations.

### Future Use of the Dataset
In additon to the previously discussed results, similar graphs and analyses could be done.  Some of these are shown below.
1.	Category/Subcategory vs % goal
2.	Country vs % goal
3.	Staff pick vs success

