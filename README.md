# Correlation-and-Welch-ANOVA-for-Movies-dataset
![image](https://github.com/rutuja-jadhav-github/Correlation-and-Welch-ANOVA-for-Movies-dataset/assets/160432263/621f832a-0f1e-4bc4-bc5c-82442f5dd243)

## Context
This project explores a Movie dataset pulled form Kaggle. The goal of the study was to study the data and identify opportunities to propose suitable Hypothesis and test their validity with relevant statistical approaches, in order to contribute to the literature associated with this dataset on Kaggle. 

## Goal
The data, containing both numeric and categorical values, seemed like a good fit to derive correlations (if any), and also explain if some movies performed better than other based on any categorial influences.

Part I - Is there a correlation between performance of movies (gross earnings) and budget?
Part II - Do movies with a particular star cast perform significantly better than others?

## Exploration and Data Cleaning 
The dataset had over 7K rows and 15 columns.Initial exploration helped me formulate the above goals.
The next step was to clean the data and make it ready for analysis - dropping null values (since this was practive problem, I wanted to simplify the cleaning and focus more on the statistical section. in real life applications, it would be wiser to have a strong rationale for deleting null values or replacing them with a suitable figure), correcting for the two redundant year and relealse columns, and dropping duplicate rows.

## Correlation, and Welch-ANOVA
Initially I decided to pick gross earnings as a measure of movie's performance and conducted the correlations with other numeric values. There was positive correlation between budget and gross earnings, suggesting the movies that cost more to make, also has higher returns at the box office.

However, later it occured to me that Gross earnings for a particular category, whether its star, company, etc, when summed over a period of time may not account for time value of money. Therfore 'score' or rating column would be a more time-resilient measure of performance. 

Although score may be more time resilient - if it has been determined as an average in the source dataset (mean of votes rather than median) then it may be sentitive to outliers, i.e, few number of voters giving a higher raking may skew the score - therefore this should be used with caution too.

Therefore to explore categorical influences on movie performance I chose to determine if there is a significant difference in the movie ratings of actors with the most no. movies (potentially more popular actors). Since data in one of the categories was not normally distributed I used Welch-ANOVA and followed this with Gameshowell pairwise test for the post hoc analysis. The Gameshowell post hoc test is often used as the non-parametric alternative to the Tukey test, following any significant differences in the Welch-ANOVA test. 

## Requirements and Dependencies
scipy==1.13.1
seaborn==0.13.2
pingouin==0.5.4
pandas==2.2.2
matplotlib==3.9.0
numpy==1.26.4

## Credits
Alex Freberg (correlation) , Data Camp (pingouin ANOVA)
