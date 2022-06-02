# What is PCA?

From Johnson (1988):

PCA (Principal Components Analysis) involves a mathematical procedure that transforms a set of **correlated variables** into a smaller set of **uncorrelated variables** called **principal components** (PCs). These PCs are **linear combinations** of the original variables and can be thought of as "new" variables.


# Uses of PCA

- Data screening  
Plotting can help to identify outliers, it may be difficult when there are many variables. PCA will help view the data in a smaller # of dimensions that may help identify outliers.  

- Clustering  
Determine how to group like observations.

- Predict classifications  
When classifications of the observations are already know, PCA can be used to help develop ways to predict classifications.

- Regression analysis  
When independent variables are highly correlated with each other, "intercorrelation" or "multicollinearity" is said to exist. This can cause estimates of the $\hat{\beta}$'s to be unstable (meaning that from sample-to-sample-to-sample, the $\hat{\beta}$'s have a lot of variability). Therefore, interpretation of how an independent and dependent variable are related by examining the $\hat{\beta}$ may not give good results.  
When variables are highly correlated, they can often be represented just as well with a smaller set of variables using PCA. However, not everyone agrees this is good to do;see Hadi and Ling (American Statistician, 1998)


# Objectives of PCA

PCA is used primarily as an exploratory technique to be followed up with other analyses. The objectives of PCA are to

1. Discover the **true dimension** of the data.  
If p dimension data (# of columns p) can be represented in q < p (q can be PC1, PC2... PCq) dimensions without losing much information, then do it.

2. Try to interpret the PCs ("new" variables)  
The PCs are **linear combinations** of the "original" variables. The weights for each of the original variables may give meaning to the PCs. For example, a weight of 0 could mean that a particular original variable is not important to the new variable. Finding interpretations for the PCs often is Very **difficult**.


# PCA with the covariance matrix $\Sigma$  
Characteristics of the PCs:

- Uncorrelated
- First principal component accounts for as much variability in the data as possible
- Each successive principal component accounts for as much variability in the data as possible
 
Let X ~ ($\mu$, $\Sigma$) where X is px1. Notice that we do not use a multivariate normal distribution assumption. Mean vector and covariance matrix are required.

---
## First principal component  

**a_1 is a p x 1 eigen vector corresponding the largest eigen value lambda_1**

$y_1$ = $a^{T}_1$(X - $\mu$) = $a_{11}$($X_1 - \mu_1$) + $a_{21}$($X_2 - \mu_2$) + ... _ $a_{p1}$($X_p - \mu_p$)

Where $a_1$ is a p x 1 vector chosen so that Var[$a^{T}_{1}$($X - \mu$)] is maximized over all vectors $a_1$ with a length of 1. 

Note this Var[$a^{T}_{1}$($X - \mu$)] is sqrt(**$\lambda_1$**) which is ```the largest eigen value``` (comp1) from the covariance matrix. The $a^{T}_1$ vector is corresponding eigen vector to $\lambda_1$

Because  the variance $y_1$ = $a^{T}_1$(X - $\mu$) = $a_{11}$($X_1 - \mu_1$) + $a_{21}$($X_2 - \mu_2$) + ... $a_{p1}$($X_p - \mu_p$) is being maximized, the new variable $y_1$ will explain as much variability of X as possible.

Why are concerned about explaining variability? In statistics, we often equate **variability** with **information**. The more variability that you understand about a data set, the more information that you know about the data set. Refer back to when you were introduced to ANOVA or regression methods when explaining variability was focused on.

The PCs are orthogonal because the eigenvectors are orthogonal.

## Total variance
---
The total variance is the sum of the diagonal elements:  
$tr(\Sigma) = \Sigma^p_{i=1}\sigma_{ii} = \sigma_{11} + \sigma_{22} + ... + \sigma_{pp}$  
This can be thought of as a measure of the total variance of the original variables.  
$tr(\Sigma) = \Sigma^p_{i=1}\lambda_{i}$. A measure of the importance of the $j^{th}$ principal component is then $\lambda_j / \Sigma^p_{i=1}\lambda_{i}$. 

We'd like to find the smallest # of PCs such that $\lambda_j / \Sigma^p_{i=1}\lambda_{i}$ values are as large as possible and the sum of these proportions are as close to 1 as possible.  **$\lambda_1$ is the variance of the $PC_1$**

## Scree plot

Plot $\lambda_1, \lambda_2, \lambda_3... \lambda_p$. When the points on the plot level off close to 0, the corresponding PCs are probably not contributing too much information to understanding the data.



# Possible issues with PCA

- If the original set of variables are already uncorrelated, PCA will **not HELP**.
- PCA doesn't generally eliminate variables because the PCs are linear combinations of the original variables.
- Thee original variables need to be measured in the same units and have similar variances.

Remember that PCA relies heavily on examining the variances of the original variables. Larger variance variables will dominate the other variables in the analysis.

For example, suppose there are three variables x1, x2 and x3 with variances of 98, 1.9 and 0.1, respectively. A way to maximize the variance of the first PC is to have it consist primarily of x1.

In general, a solution to this problem is to use standardized data ```scale(matrix)``` in R. Equivalently, use **P** in place of **covariance matrix** because the **P** is the covariance matrix of standardized random variables.       
   

# PCA with the Correlation Matrix P

PCA is most often performed using the correlation matrix **P** rather than the covariance matrix to eliminate the problem with different numerical scales being used with variables.

## PC scores - principal component value

For each observation, we calculate the **j^th principal component value** or score as:

$hat{y_{rj}} = hat{a^*_{j}}* z_r$ (This is from a correlation matrix). The jth PC and the rth observation.

## Component loading vector -> eigen vector also coefficient for the linear combination

princomp output  
Standard deviations:  
comp1, comp2 ... comp_p means PC1, PC2 ... PCp  
comp1^2 = the first eigen value -> the largest eigen value.  
Loadings:
|   |Comp.1   |
|---|---|
|variable1   | 1.xx  |
|variable2   | 1.xx  |
|variable3   | 1.xx  |

Comp.1 -> eigen vector

**Note default calculation of princomp uses divisor N(biased estimate) for the covariance matirx instead of N-1(unbiased estimate)**  

[reference - Applied Multivariate Statistical Analysis lecture note by Prof Chris Bilder ](http://www.chrisbilder.com/multivariate/sections.html)

# Difference between LDA and PCA

PC1 accounts for the most variation in the data, whereas LDA aims to maximaze the separation between the groups. (Both find linear combination of observed varaibles and elements in eigen vectors.)
