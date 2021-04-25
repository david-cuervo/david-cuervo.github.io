---
layout: post
title:      "Capstone Project: Environmental Justice"
date:       2021-04-25 00:56:30 +0000
permalink:  capstone_project_environmental_justice
---


I've made it! At the start of this course it seemed as though the final capstone project was eons away but here we are. It was such a great learning experience and I'm excited to share my process with you all.

I was warned that the capstone would be pretty intensive and time consuming so I wanted to pick a subject that I was passionate about. I went back to my environmental health background and chose to have my project related to environmental justice. 

Toxic sites are disproportionately located near poorer neighborhoods and predominantly black and brown neighborhoods. My objective was to see if there was a relationship between socioeconomic factors and pounds of toxins released by industries in Texas. I sourced my data from the EPA's Toxic Release Inventory and the Census Bureau. I merged the two datasets on ZIP code and then began to explore the data. 

I looked at a few things including a map of where the industrial sites are located. 

![Texas Industrial Toxic Releases](https://user-images.githubusercontent.com/57383419/115976222-62881c80-a531-11eb-8be3-b79304b45f31.png)

I then wanted to see which counties have the most releases.

![Top 10 Counties](https://user-images.githubusercontent.com/57383419/115976215-3f5d6d00-a531-11eb-8ad0-c3dee6c7b567.png)

Most of these counties are located along the Gulf coast and Harris county, where Houston is located, has the most releases by far.

I also looked at which chemicals are most common and which companies are the highest polluters. 

For the analysis phase, I began with using just the releases of carcinogens as my dependent variable. The accuracies were very low so I decided to expand to all chemicals. I tried linear and logistic regression, decision tree, and random forest but still could not create a model that was accurate. The highest accuracy achieved was 51% with the random forest and hyperparameter tuning. Even then, when looking at the feature importance, it was unclear. 

![Feature Importance](https://user-images.githubusercontent.com/57383419/115976293-0376d780-a532-11eb-8346-10e6401ef882.png)

Unfortunately for this project, the results were inconclusive. Many things could be done in future studies to continue the research. Instead of using pounds of toxic releases, one could just determine the actual number of industrial sites located in a certain neighborhood. Also, other toxic sites could be considered such as: bus depots, waste sites, and water treatment facilities. 

Although these results were inconclusive, environmental injustice is no myth. I hope research like this continues so that we can strive towards a healthier and equitable society.

Please find the GitHub link below:

[Capstone Project](https://github.com/david-cuervo/Capstone_Project/tree/master)


