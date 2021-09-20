# An Analysis of Kickstarter Campaigns
Performing analysis on kickstarter data to uncover trends
Helping a user by the name of Louise consider trends in theatre kickstarting funding. Primarily using Excel and its native functions for statistical analysis
=======
# Kickstarting with Excel

## Overview of Project

### Purpose
The main purpose of this Excel analysis is to provide a visual on data regarding kickstarters. Specifically, we are looking at dates of launch and their funding goals to see if there are any noticable trends in regards to the month that they start.

## Analysis and Challenges
The main body of data we are using is kickstarter information on various performances (plays/television/film/etc.). From this data, we have narrowed down our results into two PivotTables in Excel.
 
1. Theater Outcomes By Launch Date
    - Outcomes were narrowed down to only focus on a parent category of theatre and focus on the performances on a month by month basis. Counts of three categories (successful/failed/cancelled) were the main focus of the analysis across 12 months. No real challenges were present when trying to format the data.

    The only real challenge with preparing the data and setting the correct filters would be if someone were to put the parent category and/or months on the incorrect axis, leading to data that does not convey any central message about the outcomes. In such case, it would prove inconclusive and irrelevant to what the outcome of performances was.

2. Outcomes Based on Goals
    - To further narrow down the scope of kickstarter data, this set of data focuses on a subcategory called "plays". The intent is to generate descriptive statistics for successful/failed/cancelled plays. The data for play outcomes is dependent on the amount of backing that was received, separated by $5,000 up to $50,000+ (meaning that after $50,000 we consider it one single category)

    In order to get counts for the three categories with money received as the criteria, Excel lookup functions were utilized to reference the plays category and the backing each play received. 

    Some examples of the lookups received are referenced below (specifally for the >$1000 brackets)

    =COUNTIFS(Kickstarter!F:F, "successful", Kickstarter!D:D, "<1000", Kickstarter!R:R, "plays")
        - Counting successful plays that needed less than $1000

    =COUNTIFS(Kickstarter!F:F, "failed", Kickstarter!D:D, "<1000", Kickstarter!R:R, "plays")
        - Counting failed plays with less than $1000 needed

    =COUNTIFS(Kickstarter!F:F, "canceled", Kickstarter!D:D, "<1000", Kickstarter!R:R, "plays")
        - Counting cancelled plays with less than $1000 needed
        - Note: Upon applying filters on the main data, there are no plays that meet the criteria for cancelled across any of the amounts needed. 

    Simpler formulas were used in order to tally the total amounts of plays per backing category. 

    =(B2+C2+D2)
        - Counts all three cells in a row, applied across all backing levels

    Each singular category was divided by the total in order to generate the final percentage (rounding included in end formatting)

    =(B2/E2)

    Challenges that may be present is a new Excel user not being familiar with less than or greater than or equal to when starting. Not being familiar with these symbols will present incorrect data when graphed. The result of incorrect data will lead to incorrect conclusions about the plays and their outcome percentage

### Analysis of Outcomes Based on Launch Date
For theatre productions that are successful, the greatest amount of success that was generated happened in the early months of the year. Productions were steady from January to March with a steep rise that occurred up to the month of May. Lesser amounts of success would occur after September, where most productions generated less successful kickstarters than January. 

Failed productions were less consistent, upon looking at the graph for theater outcomes. Across the entirety of the year, number of profuctions picked up slightly around May and into October, but the difference of cancellations across May to October is ten cancellations more. It is hard to determine if the difference in cancellations across these months is a significant difference.

Cancellations follow a linear trend across all twelve months, with each month having cancellations in the single digits. It could be equally likely that the ambitions of a project were too large to fit the expectations of a ideal theatre performance or it may have been a project with no real interest.

### Analysis of Outcomes Based on Goals

When looking at plays that have succeeded or failed (cancelled had no data points to reference), it appears that the ideal backing bracket where projects experience the most success/failure is at either [$1000 - $4999] or less than $1000. Around 70% of projects have succeeded here, and 30% failed, with a large amount of projects happenning in these brackets as well. In other words, plays are not large productions except for a few select projects that may be ambitious or passion projects. 

Larger amounts than $5000 experience less success up till $30,000, at which we see only single digit amounts of successes and failures. In my opinion, it is unfair to state that 67% of productions at $35000 to $39999 succeeded, when the bracket right below has the opposite observation.

## Results

Some of the limitations of the dataset is not having an even distribution of successful and failed performances at a higher budget. The skew of the data is low budget productions for plays and may not give any insight on how a large production may do in terms of backing. Without any data for cancelled projects available, the category being present in our data is irrelevant and leaves no room to consider cancellation an option.

If we were able to widen our scope to theatre productions and perform an analysis of the amount of backing received per month, those results would allow for a better relationship of start dates and backing to be generated. 

When considering the rises and dips for Outcomes based on goal, I am hesitant to state that there is any real trend for the amount of data needed and the success/failure of a production. If we were considering the entirety of kickstarters or anything close to plays (music/television), maybe that would generate a better graph with more backing across all categories

