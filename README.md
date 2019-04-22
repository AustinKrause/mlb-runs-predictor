<h1>Flatiron_Mod_2_Project</h1>
Flatiron School Mod 2 Project - Linear Regression - Predict number of runs a team will score in a season
<br><br>
<h2><b>Project goals: </b> run linear regression model to try to predict number of runs that a MLB team will score in a season using yearly team hitting statistics.<br></h2>
The data used for this project came from baseball-reference.com. The initial dataframe consisted of each team's seasonal hitting statistics from 1990-2018 (excluding 1994-1995 due to MLB strike). Data was split into 2 groups: 1990-2017 and 2018 for testing.<br><br>
Preview of Dataframe:<br>

<img src='Dataframe.png'>


Columns include: 'Team', 'W', 'L', 'W/L', 'GB', 'Abv', 'Num_Hitters', 'BatAge', 'R/G', 'G', 'PA', 'AB', 'R', 'H', 'Doubles', 'Triples', 'HR', 'RBI', 'SB', 'CS', 'BB', 'SO', 'BA', 'OBP', 'SLG', 'OPS', 'OPS_Plus', 'TB', 'GDP', 'HBP', 'SH', 'SF', 'IBB', 'LOB', 'Year', 'H/G', 'Extra_Base_Hits', 'BABIP', 'OBP_times_SLG', 'Age_of_Hitters'<br>
Target Variable: Runs in a season<br><br>
Independent Variables: PA, LOB, OBP, OBP_times_SLG (interaction variable created)<br>
Model: R ~ PA + LOB + OBP + OBP_times_SLG<br>

Distributions:<br> <img src='Distributions.png'> <br>

3D visualizations:<br>  <img src='3D.png'> <br>

Regression Analysis:<br> <img src='Model_Summary.png'><br>
Interpretation of Coeffitients: <ul><li>Intercept: -1867.7977</li>
  <li>PA 0.3672: holding all else equal, a unit increase in PA will result in a 0.3672 increase in runs scored per season</li>
  <li>LOB -0.6483: holding all else equal, a unit increase in LOB will result in a 0.6482 decrease in runs scored per season</li>
  <li>OBP 2148.2308: holding all else equal, a unit increase in OBP will result in a 2148.2308 increase in runs scored per season. This number is so high due to the fact that OBP is a percentage between 0 and 1.</li>
  <li>OBP_times_SLG 2633.9704: holding all else equal, a unit increase in OBP_times_SLG will result in a 2633.9704 increase in runs scored per season. This number is so high due to the fact that OBP_times_SLG is a percentage between 0 and 1.</li>
  <li>R-Squared 0.960: this value represents that 96% of the variance shown in the model can be explained by our independent variables</li>
</ul><br>

Q-Q Plot:<br> <img src='q_q_plot.png'> <br>
Residual Plots:<br> <img src='Residuals.png'><br>

<h2><b> TEST MODEL ON STATS FROM 2018:</h2><br>
2018 predicted values using regression model:<br>
<img src='2018_Predicted_Vals.png'><br>
<img src='2018_RMSE.png'>

<h2>Hypothesis Test:</h2><br>
The New York Yankees have won the most World Series Championships within the span of 1990-2018 (5). Let's look into how they match up to the rest of the MLB in terms of runs scored.<br><br>
H0: The mean runs for NYY = the mean runs for of all of MLB<br>
Ha: The mean runs for NYY > the mean runs for of all of MLB<br>
<img src='Hypothesis_Test.png'><br>
<b>With a z score of .95 we fail to reject the null hypothesis
