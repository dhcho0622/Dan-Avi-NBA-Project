## NBA Rookie Analysis Project

Flatiron Module 3 Project Daniel Cho & Avidan Berman

### Project Overview

As the sports world continues to grow and devlop, there has been a movement for teams to start building their rosters through the amateur draft. Drafting young players is considered advantageus due to the incredibly low salarys paid out to young players and the ability to hold onto a player for a long period of time due to league negotiating restrictions. While building through the draft has a very high upside, there is also the downside. Team's must take educated guesses on the players they are drafting and hope that the players they pick are going to be successful in the league. In the National Basketball Association (NBA), teams get two picks per draft and the average career length is 5 years. What this tells us is that most organizations are struggling to pick the right rookies to improve their rosters. Our team has set out to find a better way to scout rookies after they have already entered the league. We believe, that being able to predict a young players career outlook can allow organizations better assess the value of rookie players on both their own teams and their potential trade targets.

Besides our model, these are some questions our team looked to address:
- Is there a statistical relationship between the organization a rookie is drafted by and our target variable(career length longer than 5 years)?
- Does the amount of minutes a player receives per game change the probability of success?
- Do some organizations show more of a desire to give their rookies more minutes than others?
- Does a rookies future success have a relationship with how early in the draft he was picked?

### The Approach

- Find review and clean dataset (https://data.world/rvino88/1976-to-2015-nba-draft-data/workspace/data-dictionary)
- Find additional information to supplement current dataset (https://data.world/exercises/logistic-regression-exercise-1) 
- Engineer novel features to give model deeper insight
- Perform EDA on the dataset and create visualizations using the MatPlotlib and Seaborn Libraries
- Build and test multiple prediction models
- Build additional datasets to further test our best model(https://www.basketball-reference.com/)

### Conclusions
- Using a Chi Squared test, we see no relationship between the team and the length of career due to our failure to reject the null hypothesis.
![count_plot_team.png](attachment:count_plot_team.png)

- We have learned that there is a statistical relationship between mean minutes played and the team in which a rookie is on. We see this with the use of a two sample T-test and our rejection of the null hypothesis.


- There is a statistical difference between minutes played and the teams you play for. We see this through the results of our ANOVA test, where we rejected null hypothesis.
![avg_min_team_boxplot.png](attachment:avg_min_team_boxplot.png)


- The last thing we concluded based on our exploratory analysis was that there is a negative relationship between the average minutes a player receives their rookie year and when they were picked in the draft.

### The Model
Our team started by creating a training and test set with a train-test split method. Next, our team tested multiple models and used both the accuracy and f1 metric to judge the abilities of our model. The models we tested were Logistic Regression (with and without GridSearch), KNN, a Decision Tree, Random Forest (with and without GridSearch), Voting Classifier, and an XG-Boost (With and without GridSearch). To solve for class imbalance we generally set the class hyperparameter to 'balanced', however for the KNN model we used upsampling.
We found through the use of GridSearch that XG-Boost produced the best results on the test set. The model's accuracy score was 96.6% and an F1 score of 97.76%.
To further test our model we created an additional test set using the 2012 NBA Draft class. We found that the model predicted with an accuracy of 83.67% and an F1 score of 87.5%.

### Recommendations and Future of the Project
- Our first recomendation is to organizations that are struggling to develop their rookies. Review the average number of minutes your rookie plays per game. Our data shows a significant relationship between a rookies minutes and his future success.
- Our second recomendation is that the pick used to select a player in the draft has a negative relationship with the probability of the player playing for longer than the average NBA career.
- Our third recomendation to organizations is to ignore the NCAA Division I conference a player is coming from. Our data shows that the conference in which a rookie is from doesn't have a significant relationship with his future career length.

Currently our model is able to analyze future success after the rights of a rookie are already owned, but this project can move to the next level if it were based on amateur statistics, could we predict success before a player is even get drafted?
