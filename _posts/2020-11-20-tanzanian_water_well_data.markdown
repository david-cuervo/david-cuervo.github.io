---
layout: post
title:      "Tanzanian Water Well Data"
date:       2020-11-20 22:14:51 +0000
permalink:  tanzanian_water_well_data
---


Hello readers! In this post I'll go over the Module 3 Project which centered around machine learning. For the project, we were able to select from a list of datasets or choose our own. The Tanzanian Water Well Data definitely caught my eye at first glance. With my public health background, this data seemed right up my alley and I knew it would be interesting to work through.

This data is provided as part of a competition through DrivenData. It includes the condition of the wells throught the country (functional, non functional, and functional needs repair) and many other variables that describe each well. The goal was to build a classification model that could accurately predict the wells' condition based on the data provided. 

Now with every project, we begin with the monumental task of cleaning the data. This dataset was particularly challenging to work through. Sure there were a few columns with missing values (as expected in a real-world dataset) but there were quite a few categorical columns that needed to be made into dummy variables and quite a few duplicate columns. Not to mention the descriptions of the columns that were provided. (insert crying emoji)
I don't want to disparage the good people at DrivenData but readers, if you ever find yourselves in a position where you are collecting/recording data, please keep your dear data scientists in mind when you write out the metadata. 
Signed,
Confused Data Scientists

Nonetheless, this was an excellent excersice for dealing with real-world data and I'm happy to say that I now know what a well's total static head (TSH) is and that LGA stands for local government area. 

By the time I finished cleaning up the dataset, I ended up dropping 18 columns and creating dummy variables for the remaining categorical columns. My cleaned dataset consisted of a table with 115 columns. This seemed daunting at first but luckily I had just learned about a really cool feature selection algorithm that could help. 

Shout out to my patient and brilliant instuctor extraordinaire Jeff Herman for introducing Boruta to me. Here is a link that describes Boruta pretty clearly:

[](http://towardsdatascience.com/boruta-explained-the-way-i-wish-someone-explained-it-to-me-4489d70e154a) 

Basically, Boruta creates "shadow features" that are randomized duplicates of each original feature. The original features then compete with these shadow features instead of competing with themselves. Then Boruta repeats the process multiple times to obtain the best results. The process did take some time (it took me at least 30 min to run) but it was definitley worth it.

Boruta brought my dataset of 115 columns down to 42 (I'll refer to these as "green" features). It also provided another 4 ("blue", explained further in the link) features that could also be used in the model but are probably not as important as the other 42.

Now I was finally ready to start building some classifiers. I started with a logistic regression model using the "green" features first and then adding the "blue " to see if there was a change in the accuracy. The highest score I got was a 72.41 using both green and blue features. 
Next, I wanted to see how a decision tree would stack up. Again, I tried two models with green and with both and the best accuracy was with just the green features with a score of 75.48. 
I was glad to see the score increase slightly but I wanted to try one more classifier. Lastly, I tried a random forest and the best score was a 69.82.

The decision tree model proved to be the most accurate. I then plotted a bar graph that compared each feature on their importance. The construction year, GPS height (altitude of the well), and the waterpoint type were among the most important features.

I think for next steps it would be interesting to analyze the data with a GIS software and see if we can find better predictors focusing on the geographic variables. Overall, this was a great project to work on and I learned so many new helpful skills. 




