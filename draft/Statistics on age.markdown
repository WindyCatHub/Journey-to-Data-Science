In the first part of the year we were told that old people get infected by Covid-19. Now we are told that young people is the one who spreads infection around.
One of the best thing in this digital age is that you can check situation by yourself with open data and open source tools.

I am using the same data source from Lithuanian Open Data Portal to investigate situation on age. Source provides information on age range. 

![]({{"/images/age hist.png" | absolute_url}})

However, categorical data is not very useful for futher analysis. So I converted each range to a number, choosing a middle value. For instance, in a range [0;9] the middle value would be 4.5

With this modification I wanted to see how changes people who get sick age by the time. If I would drow scatter plot for this data ir would be grouped and ploted like dots in line as I have just one number for ten years interval. 
So I added random noise to my scatter plot to have more smooth plot.

![]({{"/images/age scatter.png" | absolute_url}})

From Scatter plot above we see that actually at the begining of the year there was a bit more older Covid-19 infected people and in the end of the year the differece is gone.

From both plots above, we can guess that there are some outliars in the data. The easiest wayto investigate on outliars is to plot boxplot with shows mean, std, quantile, and outliars. So from the plot below we have 3 age ranges that are outliars. So people in the age range '90-99', '100-109', '120-129' are outliers. I will remove for now this data from my data set for further analysis.

![]({{"/images/age boxplot.png" | absolute_url}})

Now, that I have new data set without missing data and outliars, I can plot Cumulative distribution functions. For this I will use Pythin package `<empiricaldist>`.
It was no surprise that infected people age is distributed very close to normal distribution as a lot of thing in our life can be described by normal distribution. To show comparition I plotted random normal distribution line with the same mean and std. the mean is 45.426437 and std is 18.531993. So it means that peaple at age of 45 (or in range 40 to 49) +/- 18 year are mostly infected.

![]({{"/images/age and sample dist.png" | absolute_url}})

My data set provides data on few other parameters on the infected person:
  * what was an outcome 
  * if the person was hospitalized (yes/no)
  * if the person was treated in intensive care (yes/no)
  * if the person had chronic diseases (yes/no)
  
I converted categorical columns to numeric using `<.cat.codes>` method and calculated correlation matrix.
Correlation matrix is a table showing correlation coefficients between two variables. Keep in mind that correlation do not show cosation. Its only show how strong is linear relationship between variables. The value of correlation coefficient is between -1 and 1 and if correlation is around 0 it means that correcation is weak.

![]({{"/images/corr.png" | absolute_url}})

So from correlation matrix we see that there are no strong liner relationship between age range and other variables. However, it does not mean that there are no relationship.
However, I have feeling that age should have some kind relationship with variable showing if the person was/is treated in intensive care. th boxplot below shows that older people are more likely to be treated in intensive care than younger ones. 

![]({{"/images/age and rean box.png" | absolute_url}})

For now, this is it. In other post I will go to deeper analytsis of the age of people infected to Covid-19.
