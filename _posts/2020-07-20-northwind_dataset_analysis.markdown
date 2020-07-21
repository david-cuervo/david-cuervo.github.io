---
layout: post
title:      "Northwind Dataset Analysis"
date:       2020-07-21 01:56:20 +0000
permalink:  northwind_dataset_analysis
---


Hello fellow data scientists! It has been quite a while since my last blog post. I'm sure we're all dealing with our world in our own way but I have to say it has been nice to have this course to keep me focused and occupied! Also, I'm realizing more and more each day how crucial data science and communication is! That being said, this latest project was really fun to work on and it hardly felt like work. 

The Northwind Dataset is a dataset comprised of data from a fictional company. The data in this set includes information on products, employees, shipping, and customers. The main question we tasked with answering is as follows:

**Does discount amount have a statistically significant effect on the quantity of a product in an order? If so, at what level(s) of discount?**

To answer this, I started by sourcing the data using some SQL queries (which have been my favorite labs so far by the way).

```
cur.execute("""SELECT *
               FROM OrderDetail
               ;
               """)
df = pd.DataFrame(cur.fetchall())
df.columns = [x[0] for x in cur.description]
df
```

After I pulled the data I needed I started to explore a bit. I got rid of some discount rates that were outliers and I made a boxplot to get an idea of their relationship to quantity. It seemed like there were some differences so I started my hypothesis testing to see how significant those differences were. I used a two-tailed t-test to measure the differences between the quantities in 5, 10, 15, 20, and 25% discounts and no discount. Turns out all of the discounts had statistically significant differences in their quantities than the quantities with no discount! 

I then used Cohen's d to measure the effect size. The results shows that a 15% discount had the biggest difference in quantities compared to an order with no discount. 

What I really enjoyed about this project was the flexibility to then choose 3 other questions to answer ourselves. I chose to look at unit price, shipping region, and office location and their relationship to quantity of product in an order. 

Out of these 3, only shipping region had some significant differences between their quantities. This time to measure their differences, I used a tukey test. It's basically what I did for the first question but the tukey test measures all the different regions at once! 

```
from statsmodels.stats.multicomp import pairwise_tukeyhsd

tukey_test = pairwise_tukeyhsd(df['Quantity'], df['ShipRegion'] )
tukey_test._results_table
```

It then returns a results table that includes p-values, mean differences, and whether to reject the null hypothesis or not! So quick and easy and definitely something I'll use again in the future. 
