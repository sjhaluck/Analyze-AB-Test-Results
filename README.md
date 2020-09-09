# Analyze A/B Test Results
#### An example of data analysis for a complete cycle of A/B testing to determine practical deployment of a new website
#### Part of Data Analyst Nanodegree Program at [Udacity](www.udacity.com)

## The complete cycle progresses through three stages of analysis
### Probability
Analyze the characteristics of the pandas dataframe. When conflicts are identified (inaccurate data, duplicate data), remove them from the dataset appropriately. Using the methods for pandas dataframes, gather statistics about the data set that will be useful in further analysis (means, differences, comparisons).

### A/B Test
By isolating treatment groups (old vs. new website), data is categorized for comparison and further analysis. The null hypothesis is the assumption that there is no significant difference between the conversion rate for the two websites (difference = 0). With the assumption of the null hypothesis, 10,000 simulations are run (of size equal to the original dataset). From the simulations, differences between conversion rate for the websites are collected (new - old). A histogram is constructed of the 10,000 simulated differences under the null hypothesis. The observed difference from the Probability stage of analysis is then compared to the simulations.

The comparison shows that the observed difference in conversion rate (or greater differences) in the data had an over 90% chance of happening purely by chance if the two customers of both versions website had the same conversion rate (null hypothesis was true). This means that the data collected does NOT support a difference between the two versions of the website.

The simulated finding was also verified using the `proportions_ztest` function of the `statsmodels` library.

### Regression
The final state of analysis was Logistic Regression (due to the categorical nature of customer conversion - True or False). The Logistic Regression model returns a two-sided analysis (probability of a value greater than or less than the observed difference) that verifies our previous analysis as well.

## Further Analysis
Due to the inconclusive results of the analysis, further analysis would be necessary. For the purposes of this project, country of origin is investigated and found to have no significant effect on conversion rate.

## Skills & Libraries
- python
- pandas
- numpy
- matplotlib
- statsmodels
