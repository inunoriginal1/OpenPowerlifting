# Oklahoma Powerlifting EDA: Project Overview
* Explored Oklahoma competitive powerlifting data from 1991 to 2020.
* Downloaded dataset with over 2.1 million records from [openpowerlifting.org](https://www.openpowerlifting.org/).
* Cleaned the data, paying attention to duplication and reasonableness of values.
* Imputed for missing values and engineered a couple features to assist in the EDA.
* Outputted filtered and cleaned data subset as CSV file.
* Created meaningful visualizations to better understand characteristics and trends in the data.

## Tools Used

**Python**: 3.8.3  
**Packages**: pandas, numpy, matplotlib, seaborn, scipy  
**For exact package versions**: `pip install -r requirements.txt`

## Data Cleaning

The following changes were made to the original data, to best support the analysis I was trying to do:

* Filtered for only tested, full powerlifting meets in Oklahoma
  - `Tested` == 'Yes', `MeetCountry` == 'USA', `MeetState` == 'OK', `Event` == 'SBD'
* Dropped many unneeded features, such as age-related columns, columns filtered for just one value, any lift features other than the lifter's best for each lift, etc.
* Filtered out any records where the lifter was disqualified or failed to register a successful attempt for any of the three lifts
* Removed duplicate records (primarily caused by lifters entering multiple divisions within the same meet, necessitating duplicated results with different `Division` values)
* Created a `MeetYear` feature, from the `Date` column
* Created a corresponding column in lbs for all columns in kgs.

## EDA

A few of the visual highlights:

**Competitive powerlifting is a lot less male dominated than it used to be.**
<p align="center"><img src="./Graphs/pct_results.png" alt="Graph showing the proportion of meet results for men and women." width="450" height="300"/></p>

**While the lifts are all strongly correlated with each other, there is a lot of variation in a lifter's relative strength (especially for women).**
<p align="center"><img src="./Graphs/bodyweight_vs_lifts_heatmap.png" alt="Graph showing the correlation between bodyweight and the different lifts." width="720" height="300"/></p>

**Every pound of bodyweight is expected to add 2.3 times more powerlifting strength for men than for women.**
<p align="center"><img src="./Graphs/mf_bodyweight_vs_total.png" alt="Graph showing bodyweight vs totals for men and women." width="900" height="300"/></p>

## Bonus Section: Impressive Powerlifters

Just wanted to take a second to share some of the impressive powerlifters I learned about during this project!

**[Mike Ewoldsen](https://www.htrnews.com/story/news/local/2016/06/24/powerlifter-mike-ewoldsen-ends-ministry-two-rivers/86342206/)**  
*Traveling minister and world champion lifter*
<p align="center"><img src="./img/MikeEwoldsenSQ.jpg" alt="Ewoldsen lifting 1,000 pounds during one of the Dunamos ministries. Image courtesy of htrnews.com." width="446" height="252"/></p>

**[Teale Adelmann](https://www.liftinglarge.com/Who-We-Are)**  
*NASA Hall of Fame inductee and lifting gear store owner*
<p align="center"><img src="./img/TealeAdelmannDL.jpg" alt="Ewoldsen deadlifting 407.9 pounds in competition. Image courtesy of LiftingLarge.com." width="446" height="252"/></p>

**[Dr. Nathan Burford](https://www.instagram.com/tastynate_phd)**  
*PhD holder, craftsman, and elite powerlifter*
<p align="center"><img src="./img/NathanBurford.jpeg" alt="Nathan with the wooden monolift he built. Image courtesy of his twitter account @tastynate_phd." width="252" height="252"/></p>
