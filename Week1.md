# Supervised Learning
We are told what is the correct answer and use those correct answers to predict the unknown situation.

Training set: Already know answer values. Being taken into learning algorithm, output h --> hypothesis

## Regression
Goal: get a continuous value output

### Cost Function
minimize J(theta0,theta1...) = 1/2m * SUM(h(x) - y)  --> suqared error function / mean squared error

### Gradient Descent
Start with initial guess of thetas. Doesn't matter the particular value.  
Keep changing thetas to reduce J(thetas), until the local minimum

## Classification
Goal: get a discrete value output  
Deal with infinite number of features -> Support Vector Machine.   
θj := θj - a * ∂ J(θ...) / ∂θj
  * := -- assignment
  * = -- asserting
  * a -- how big step between each trial
<strong>All thetas should be updated simutaneously.</strong>
  
Example 1:

Given data about the size of houses on the real estate market, try to predict their price. Price as a function of size is a continuous output, so this is a regression problem.

We could turn this example into a classification problem by instead making our output about whether the house "sells for more or less than the asking price." Here we are classifying the houses based on price into two discrete categories.

Example 2:

(a) Regression - Given a picture of a person, we have to predict their age on the basis of the given picture

(b) Classification - Given a patient with a tumor, we have to predict whether the tumor is malignant or benign.



# Unsupervised Learning 
Unsupervised learning allows us to approach problems with little or no idea what our results should look like. We can derive structure from data where we don't necessarily know the effect of the variables.  
Given a dataset, find pattern in the dataset through specific algorithm.   
## Clustering   
1. Google News --> Clustering algorithm, different 
news about BP oil well news get grouped together.
2. Seperate people through genes.
3. Organize Computing Cluster.  
4. Social network analysis (seperate groups of people)
5. Market segmentation(divide customer through market)  
6. Astronomical data analysis  

## Cocktail Party Algorithm
Two recodings with two voices --> seperate the two voices into indivisual 


Example:

Clustering: Take a collection of 1,000,000 different genes, and find a way to automatically group these genes into groups that are somehow similar or related by different variables, such as lifespan, location, roles, and so on.

Non-clustering: The "Cocktail Party Algorithm", allows you to find structure in a chaotic environment. (i.e. identifying individual voices and music from a mesh of sounds at a cocktail party).
