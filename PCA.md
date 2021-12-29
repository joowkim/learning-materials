## What is PCA?


---
From Johnson (1988):

PCA (Principal Components Analysis) involves a mathematical procedure that transforms a set of **correlated variables** into a smaller set of **uncorrelated variables** called **principal components** (PCs). These PCs are **linear combinations** of the original variables and can be thought of as "new" variables.

---


## Uses of PCA

- Data screening  
Plotting can help to identify outliers, it may be difficult when there are many variables. PCA will help view the data in a smaller # of dimensions that may help identify outliers.  

- Clustering  
Determine how to group like observations.

- Predict classifications  
When classifications of the observations are already know, PCA can be used to help develop ways to predict classifications.

- Regression analysis  
When independent variables are highly correlated with each other, "intercorrelation" or "multicollinearity" is said to exist. This can cause estimates of the $\hat{\beta}$'s to be unstable (meaning that from sample-to-sample-to-sample, the $\hat{\beta}$'s have a lot of variability). Therefore, interpretation of how an independent and dependent variable are related by examining the $\hat{\beta}$ may not give good results.  
When variables are highly correlated, they can often be represented just as well with a smaller set of variables using PCA. However, not everyone agrees this is good to do;see Hadi and Ling (American Statistician, 1998)
---


## Objectives of PCA

PCA is used primarily as an exploratory technique to be followed up with other analyses. The objectives of PCA are to

1. Discover the **true dimension** of the data.  
If p dimension data (# of columns p) can be represented in q < p (q can be PC1, PC2... PCq) dimensions without losing much information, then do it.

2. Try to interpret the PCs ("new" variables)  
The PCs are **linear combinations** of the "original" variables. The weights for each of the original variables may give meaning to the PCs. For example, a weight of 0 could mean that a particular original variable is not important to the new variable. Finding interpretations for the PCs often is Very **difficult**.
---


## PCA with the covariance matrix $\Sigma$  
Characteristics of the PCs:

- Uncorrelated
- First principal component accounts for as much variability in the data as possible
- Each successive principal component accounts for as much variability in the data as possible
 
Let X ~ ($\mu$, $\Sigma$) where X is px1. Notice that we do not use a multivariate normal distribution assumption. Mean vector and covariance matrix are required.


### First principal component

$y_1$ = $a^{T}_1$ (X - $\mu$) = $a_{11}$($X_1 - \mu_1$) + $a_{21}$($X_2 - \mu_2$) + ... _ $a_{p1}$($X_p - \mu_p$)

Where $a_1$ is a px1 vector chosen so that Var[$a^{T}_{1}$($X - \mu$)] is maximized over all vectors $a_1$ with a length of 1. 

Note this Var[$a^{T}_{1}$($X - \mu$)] is **$\lambda_1$** which is ```the largest eigen value``` from the covariance matrix. The $a^{T}_1$ vector is corresponding eigen vector to $\lambda_1$

Because  the variance $y_1$ = $a^{T}_1$ (X - $\mu$) = $a_{11}$($X_1 - \mu_1$) + $a_{21}$($X_2 - \mu_2$) + ... _ $a_{p1}$($X_p - \mu_p$) is being maximized, the new variable $y_1$ will explain as much variability of X as possible.

Why are concerned about explaining variability? In statistics, we often equate **variability** with **information**. The more variability that you understand about a data set, the more information that you know about the data set. Refer back to when you were introduced to ANOVA or regression methods when explaining variability was focused on.

The PCs are orthogonal because the eigenvectors are orthogonal.

The total variance is the sum of the diagonal elements:  
$tr(\Sigma) = \Sigma^p_{i=1}\sigma_{ii} = \sigma_{11} + \sigma_{22} + ... + \sigma_{pp}$  
This can be thought of as a measure of the total variance of the original variables.  
$tr(\Sigma) = \Sigma^p_{i=1}\lambda_{i}$. A measure of the importance of the $j^{th}$ principal component is then $\lambda_j / \Sigma^p_{i=1}\lambda_{i}$. 

We'd like to find the smallest # of PCs such that $\lambda_j / \Sigma^p_{i=1}\lambda_{i}$ values are as large as possible and the sum of these proportions are as close to 1 as possible.  **$\lambda_1$ is the variance of the $PC_1$**







[reference - Applied Multivariate Statistical Analysis lecture note by Prof Chris Bilder ](http://www.chrisbilder.com/multivariate/sections.html)
