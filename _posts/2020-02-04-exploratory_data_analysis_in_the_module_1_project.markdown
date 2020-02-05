---
layout: post
title:      "Exploratory Data Analysis in the Module 1 Project"
date:       2020-02-05 03:29:49 +0000
permalink:  exploratory_data_analysis_in_the_module_1_project
---


Sifting through your data will likely be the most time consuming part of your analysis. However, after working through the Module 1 Project, I've found that it is definitely the most interesting and fun part! It can be exciting to see a visual description of each variable and how each one is related to the other. Slowly, this giant mass of numbers begins to become something you can understand and control. 

For the Module 1 Project, I first created histograms to see the distribution of each variable. This gave me an idea of how to manipulate each one accordingly. For example, I could distinguish which variables were categorical. This would then help me decide which visualization technique I would use for them later on. Seeing their distribution would also let me know if I needed to log transform any variables so that they could better fit a normal distribution. I did not log transform any variables for this project for the sake of interpretability. 

The following code is short and sweet and provides a histogram for each variable:
```
df.hist(figsize=(18,18))
``` 
		 
After making the histograms, I wanted to see the relationship each predictor had on my dependent variable, price. For the categorical variables I used box plots. Specifically, I used Seaborn to make the box plots. I found the code straight forward and I also prefer it visually. Here is the code I used (make sure to import it as well!):

```
import seaborn as sns
sns.boxplot(x="floors", y="price", data=df).set(title='Floors and Sale Price')
```

The boxplots made it very clear to see the relationship between the categorical variables and price. From these visualizations, I was able to pick out the 'grade', 'waterfront', and 'view' variables for my regression model. 

For the continuous variables, I chose to make scatterplots. Also with Seaborn, I was able to figure out if there was any kind of linear relationship between price and the other continuous variables. Here is the code for scatterplots with Seaborn:

```
sns.scatterplot(x='sqft_above', y='price', data=df).set(title='Square Feet Above the Basement and Sale Price')
```

Keep in mind there are many other parameters you can set to change the size or color and you can group the data with different colors or markers! Here is a link to a website for reference:

[](http://seaborn.pydata.org/generated/seaborn.scatterplot.html) 

These scatterplots allowed me to choose appropriate features to add to my model as well. Ultimately, these ended up being just the number of bathrooms in the house and the square footage of the nearest 15 neighbors. 

In addition to visualization techniques, I used another really useful code to help modify my data to remove multicollinearity. 

'abs(data.corr()) > 0.75' is a short and easy way to visualize the correlation of your features. True and False stand out much better than a lot of scattered numbers so you can quickly identify the problematic features. 

This code, in addition to the box and scatterplots, greatly helped me to understand this newly encountered dataset. I'm definitely glad I now have these in my tool belt so that exploring future datasets will be much easier. 



