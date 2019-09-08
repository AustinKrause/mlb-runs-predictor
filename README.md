<h1>Flatiron Mod 2 Project</h1>
<ul>
Flatiron School Mod 2 Project - Linear Regression - Predict number of runs a team will score in a season
<br><br>
<li><h2><b>Project goals: </b> run linear regression model to try to predict number of runs that a MLB team will score in a season using yearly team hitting statistics.<br></h2>
The data used for this project came from baseball-reference.com. The initial dataframe consisted of each team's seasonal hitting statistics from 1990-2018 (excluding 1994-1995 due to MLB strike). Data was split into 2 groups: 1990-2017 and 2018 for testing.<br><br></li>
<li>Preview of Dataframe:<br>

<img src='Images/Dataframe.png'>
</li>
<li>
Columns include: 'Team', 'W', 'L', 'W/L', 'GB', 'Abv', 'Num_Hitters', 'BatAge', 'R/G', 'G', 'PA', 'AB', 'R', 'H', 'Doubles', 'Triples', 'HR', 'RBI', 'SB', 'CS', 'BB', 'SO', 'BA', 'OBP', 'SLG', 'OPS', 'OPS_Plus', 'TB', 'GDP', 'HBP', 'SH', 'SF', 'IBB', 'LOB', 'Year', 'H/G', 'Extra_Base_Hits', 'BABIP', 'OBP_times_SLG', 'Age_of_Hitters'<br></li>
<li>Target Variable: Runs in a season<br><br></li>
<li>Independent Variables: PA (plate appearances), LOB (left on base), OBP (on base percentage), OBP_times_SLG (interaction variable created from on base percentage and slugging percentage)<br><br></li>
<li>Model: R ~ PA + LOB + OBP + OBP_times_SLG<br><br></li>

<li>Distributions:<br> <img src='Images/Distributions.png'> <br></li>

<li>3D visualizations:<br>  <img src='Images/3D.png'> <br></li>

<li>Regression Analysis:<br> <img src='Images/Model_Summary.png'><br>
Interpretation of Coeffitients: <ul><li>Intercept: -1867.7977</li>
  <li>PA 0.3672: holding all else equal, a unit increase in PA will result in a 0.3672 increase in runs scored per season</li>
  <li>LOB -0.6483: holding all else equal, a unit increase in LOB will result in a 0.6482 decrease in runs scored per season</li>
  <li>OBP 2148.2308: holding all else equal, a unit increase in OBP will result in a 2148.2308 increase in runs scored per season. This number is so high due to the fact that OBP is a percentage between 0 and 1.</li>
  <li>OBP_times_SLG 2633.9704: holding all else equal, a unit increase in OBP_times_SLG will result in a 2633.9704 increase in runs scored per season. This number is so high due to the fact that OBP_times_SLG is a percentage between 0 and 1.</li>
  <li>R-Squared 0.960: this value represents that 96% of the variance shown in the model can be explained by our independent variables</li>
</ul><br></li>

<li>Q-Q Plot:<br> <img src='Images/q_q_plot.png'> <br></li>
<li>Residual Plot:<br> <img src='Images/Residuals.png'><br>
The residual plot looks to be normally distributed.</li>

<li><h2><b> TEST MODEL ON STATS FROM 2018:</h2><br>
2018 predicted values using linear regression model:<br>
<img src='Images/2018_Predicted_Vals.png'><br>
  <img src='Images/2018_RMSE.png'><br>
  As seen above, the average error for each prediction is about 17 runs per season. Comparing this to the mean runs scored in 2018, we get an average error of about 2.45%.</li>

<li><h2>Hypothesis Test:</h2><br>
The New York Yankees have won the most World Series Championships within the span of 1990-2018 (5). Let's look into how they match up to the rest of the MLB in terms of runs scored.<br><br>
H0: The mean runs for NYY = the mean runs for of all of MLB<br>
Ha: The mean runs for NYY > the mean runs for of all of MLB<br>
<img src='Images/Hypothesis_Test.png'><br>
  <b>With a z score of .95 we fail to reject the null hypothesis that the New York Yankees significantly score more runs than the rest of the MLB</li><br><br>

<li><h2>Conclusion</h2><br>
After obtaining the data and doing my initial EDA, it seems that the most valuable hitting statistics for predicting runs scored per season are Plate Appearances, Left On Base, On Base Percentage, and On Base x Slugging Percentage. These variables together account for 96% of the variance in runs scored per season within the dataset. Going forward, I would like to test this model on future seasons as well as turn my focus toward the target variable of wins per season. 
  </li>
</ul>
