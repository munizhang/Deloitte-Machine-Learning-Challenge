
# Deloitte-Machine-Learning-Challenge
#Goal

Use Machine Learning and Statistics to predict winners of NCAA tournament games based on season performance

#Method
This project uses aggregated regular season stats to calculate each team's skill for that metric, then compares the ratio for team 1 and team 2 to predict if team 1 will win.
To reduce noise, regular season games are only included if they are against teams that went on to make the tournament that year. For example, if UNC played Duke and scored 86 points, this is a good indication of how they will perform against the type of teams they will face in the tournament. However if they play Radford and score 95, we should not include the 95 points in their average score because they are unlikely to play a team with such a bad defense in the post season. This applies to all team stats except for Tempo, Offensive Efficiency, and Defensive Efficiency (we could not get game level for these).
The aggregating occurs in excel and the values are the average performance for that stat against quality opponents. The ratio between team 1 and team 2's metrics are used as training and testing data for our classifiers. The standard model used for sports analysis is logistic regression. We will test out a few others. Our final model is an ensemble voting classifier that combines the outputs of logistic regression, support vector machine, neural network, and adaptive boosting to provide and ultimate prediction.
#Results

The final results give about a 74% accuracy in historical predictions for each game that occurred. While this threshold would not be satisfactory for some enterprise models, it is pretty good for sports predictions. Especially considering that we lack player level data to account for injuries etc.
The results for the 2017 tournament are a little 75%. The overperformance is due to the relatively low upset count this year (the model is very reliant on seed as a predictor).
