# Stat terms
---------------  

### Estimated beta coefficient interpretation  
There is sufficient evidence at the 0.05 level to conclude that a predictor variable is statistically significant or is significantly related to the reponse variable.   
[reference: Penn State State501]

### Extrapolation  
beyond the "scopte of the model" when estimating a mean Uy or to predict a new response y_new for x values int in the range of the sample data  
[reference: Penn State Stat501 lesson-12.8](https://online.stat.psu.edu/stat501/lesson/12/12.8)


### The CLT
The Central Limit Theorem of probability states that the sum of many small, independent RVs will be a RV that approximates what is called a *normal distribution*.  
[reference](Regression and Other Stories)


### Standard error  
The standard deviation of an estimate  
[reference](Regression and Other Stories) 


### Interpretation of regression coefficients  
The safest interpretation of a regression is as a comparison For example   
 1. earnings = -26 + 0.6 x height + 10.6 x male + error  
   1.1. Comparing two people with the same height but different sex, the man's earnings will be, on average, $10,600 more than the woman's in the fitted model.  
 2. kid_score = 26 + 0.6 x mom_iq + error  
   2.1. between groups of children whose mothers' IQ differed by 10 points-these childeren would be expected to have scores that differed by 6 points on average.  
   2.2. Differing in maternal IQ by 1 point  we expect to see that the group with higer maternal IQ achieves 0.6 points more on average.  
 3. kids_score = 26 + 6 x mom_hs + 0.6 x mom_iq + error  
   3.1. The coefficient of maternal high school completion. Comparing kids whose mothers have the same IQ, but who differed in whether they completed high school, the model predicts an expected difference of 6 in their test scores.  
   3.2. The coefficient of maternal IQ. Comparing kids with the same value of mom_hs, but whose mothers differ by 1 points in IQ, we would expect to see a difference of 0.6 points in the child's test score.  

When comparing two kids whose mothers have the same level of education, the kid whose mother is x IQ points higher is predicted to have a test score that is 6x higher, on average.

We interpret regression slopes as comparisons of individulas that differ in one predictor while being at the same levels of the other predictors.  
[reference](Regression and Other Stories) 

### Etc
e-05 notation
1.1e-05 is to be read as 1.1 × 10−5, or 0.000011, and 2e-16 = 2 × 10−16
