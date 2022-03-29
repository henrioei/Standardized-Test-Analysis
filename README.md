# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: SAT vs ACT and which is better?

### Henri Oei, DSIF2 - Singapore

## Problem Statement

Is there a bias between the ACT and the SAT, and what advise can we provide to the education board of certain states to help increase test scores?

## Executive Summary

For this project we are task to find a correlation between the ACT and the SAT and find out how one differentiate from the other in terms of participation and scores from 2017 to 2019. After much needed data cleaning was done to the datasets, research shows that there is a selection bias between the two tests where lower participation typically means higher mean scores. SAT scores are also found to be strongly correlated to ACT scores when normalized, thus it shows that the education standard is not compromised, which leads to the question if the education board should consider only adopting one standardized test instead. There is a lso a negative correlation in individual subjects, meaning that a lower math score in SAT means a higher math score in ACT.

The comparison between the SAT and the ACT participation rates from 2017 to 2019 shows that although there are more participants for the ACT compared to the SAT, it shows that over the three year period there has been an increase in SAT participation and a decrease in ACT participation indicating a possible shift.

The comparison between the number of ACT test centers across the states, ACT participation, and ACT scores from 2017 to 2019 shows that the number of test centers does not increases or decreases test scores. However, there is a possitive correlation between the number of graduates and the number of test centers per state which makes sense.

As we want to figure out what makes certain states have better mean scores compared to those who have low mean scores, we compared the top and botth 5 states based on per capita income and the percentage of people within a state that has a Bachelors degree or higher and it showed a possitive correlation between income and bachelors degree % between the low and high ACT scoring states. As we compare to all the states it shows the same possitive correlation. However, when we compared SAT scores to per capita income, it showed no correlation and thus suggests that it is more of a fairground between low and high per capita income states.

As we dug deeper, we find that low per capita income states tend to have higher crime rates compared to high per capita income states having lower crime rates, thus suggesting that crime might play a big role in the increase and decrease of scores overall per state. 

## Conclusions and Recommendations

Based on the overall analysis of the data provided including additional data, it is evident that the ACT scores are correlated to the per capita income, whereas the SAT scores are not correlated to the per capita income. And knowing that there is a strong correlation between the ACT and SAT test scores, the education standard is not compromised, thus our recommendation is to advise the education board to only adopt the SAT as the sole standardized test for college applications. 

Additionally, as low per capita income have a direct correlation to test scores, we would recommend that states provide additional monetary support for waivers. The reason being is because nationwide, 765,568 of the 2019 graduates (42.9 percent) taking the ACT two or more times had an average Composite score of 22.7, compared to an average of 19.2 for 1,017,252 of the 2019 graduates (57.1 percent) who took the ACT only once. Thus, it gives unpriviliged students a chance to score higher and be able to be admitted to a college and obtain a bachelors degree and eventually will have a direct influence in the per capita income of a particular state.

## Data

### *Source*

We are provided datasets of SAT and ACT (*standardized tests that are part of college application submissions for certain colleges*) from 2017 to 2019, however I have used the following data for my analysis:

* Participation as a percentage per state of those who took the test.
* Mean of individual subject scores
* Mean of total scores

Additionally I have acquired data from outside sources for the following information:

* [Per Capita Income per state for 2019](https://www.census.gov/quickfacts/fact/table/NH,MA,CT,DC,ME/INC910219#INC910219)
* [Number of highschool graduates for 2017, 2018, and 2019 per state](http://www.act.org/content/dam/act)
* [Percentage of people within a state that acquired at least a Bachelors degree per state for 2019](https://www.census.gov/quickfacts/fact/table/NH,MA,CT,DC,ME/INC910219#INC910219)
* [Crime rate per state for 2019](https://www.statista.com/statistics/200445/reported-violent-crime-rate-in-the-us-states/)
* [Number of test centers per state](https://www.act.org/content/act/en/products-and-services/the-act/registration/test-center-locator.html)

### *Data Cleaning*

The data set contained a lot of issues such as the following:

* Missing Values
	* No null values noted
* Incorrect Data Types
	* Participation rates and scores set to either an integer or a float
* Errors in Data
	* 6 incorrect data observed
* Naming Issues (*lower and upper caps*) and Redudant Rows (*inconsistent with other data sets for analysis*)
	* Standardization of clumn names and dropping of rows not needed

### *Updated Data Dictionary*

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|final_sat_act|State of the data| 
|sat_participation_17|float|final_sat_act|State participation rate for the SAT in 2017|
|sat_reading_writing_17|integer|final_sat_act|State average SAT Evidence-Based Reading and Writing score in 2017|
|sat_math_2017|integer|final_sat_act|State average SAT Math score in 2017|
|sat_total_2017|integer|final_sat_act|State average SAT Total score in 2017|
|act_participation_17|float|final_sat_act|State participation rate for the ACT in 2017|
|act_english_17|float|final_sat_act|State average ACT English score in 2017|
|act_math_17|float|final_sat_act|State average ACT Math score in 2017|
|act_reading_17|float|final_sat_act|State average ACT Reading score in 2017|
|act_science_17|float|final_sat_act|State average ACT Science score in 2017|
|act_composite_17|float|final_sat_act|State average ACT Composite score in 2017|
|sat_participation_18|float|final_sat_act|State participation rate for the SAT in 2018|
|sat_reading_writing_18|integer|final_sat_act|State average SAT Evidence-Based Reading and Writing score in 2018|
|sat_math_2018|integer|final_sat_act|State average SAT Math score in 2018|
|sat_total_2018|integer|final_sat_act|State average SAT Total score in 2018|
|act_participation_18|float|final_sat_act|State participation rate for the ACT in 2018|
|act_composite_18|float|final_sat_act|State average ACT Composite score in 2018|
|sat_participation_19|float|final_sat_act|State participation rate for the SAT in 2019|
|sat_reading_writing_19|float|final_sat_act|State average SAT Evidence-Based Reading and Writing score in 2019|
|sat_math_2019|float|final_sat_act|State average SAT Math score in 2019|
|sat_total_2019|float|final_sat_act|State average SAT Total score in 2019|
|act_participation_19|float|final_sat_act|State participation rate for the ACT in 2019|
|act_composite_19|float|final_sat_act|State average ACT Composite score in 2019|
|state_codes|object|final_sat_act|State Codes for Chloropleth Mapping|
|graduates_act_2017|float|act_test_centers_3|State Graduates that partake in ACT in 2017|
|graduates_act_2018|float|act_test_centers_3|State Graduates that partake in ACT in 2018|
|graduates_act_2019|float|act_test_centers_3|State Graduates that partake in ACT in 2019|
|Income|int|state_income_degree_crime|State Per Capita Income in 2019|
|Degree|float|state_income_degree_crime|State Bachelors Degree % in terms of Acquisition in 2019|
|Crime Rate|float|state_income_degree_crime|State Crime Rate in 2019|
|Income_new|float|state_income_degree_crime|Normalization of Income per State in 2019|
|Degree_new|float|state_income_degree_crime|Normalization of Bachelor Degree obtained per State in 2019|
|CrimeRate_new|float|state_income_degree_crime|Normalization of Crime Rate per State in 2019|