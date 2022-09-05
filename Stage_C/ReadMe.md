# Stage C Tag - Along Code
## Machine Learning: Classification - Managing the Quality Metric of Global Ecological Footprint

This analysis and the model built was done for submission in response to questions posed to test knowledge gained from Stage C of the Hamoye Summer 2022 internship.


**DataSource:** The data was gotten from [UCI Machine Learning Repository]( https://archive.ics.uci.edu/ml/datasets/Electrical+Grid+Stability+Simulated+Data+)

**Data Description:** The analysis is performed for different sets of input values using the methodology similar to that described in [SchÃ¤fer, Benjamin, et al. 'Taming instabilities in power grid networks by decentralized control.' The European Physical Journal Special Topics 225.3 (2016): 569-582.]. Several input values are kept the same: averaging time: 2 s; coupling strength: 8 s^-2; damping: 0.1 s^-1



**Data Features**

It has 12 primary predictive features and two dependent variables.

*__Predictive features:__*

- 'tau1' to 'tau4': the reaction time of each network participant, a real value within the range 0.5 to 10 ('tau1' corresponds to the supplier node, 'tau2' to 'tau4' to the consumer nodes);
- 'p1' to 'p4': nominal power produced (positive) or consumed (negative) by each network participant, a real value within the range -2.0 to -0.5 for consumers ('p2' to 'p4'). As the total power consumed equals the total power generated, p1 (supplier node) = - (p2 + p3 + p4);
- 'g1' to 'g4': price elasticity coefficient for each network participant, a real value within the range 0.05 to 1.00 ('g1' corresponds to the supplier node, 'g2' to 'g4' to the consumer nodes; 'g' stands for 'gamma');

*__Dependent variables:__*
- 'stab': the maximum real part of the characteristic differential equation root (if positive, the system is linearly unstable; if negative, linearly stable);
- 'stabf': a categorical (binary) label ('stable' or 'unstable').

## Key areas tested in this quiz:

- Building various classification models.
- Tuning hyperparameters using RandomizedSearchCV.
- Measuring performance of various models.