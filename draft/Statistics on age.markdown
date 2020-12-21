In the first part of the year we were told that old people get infected by Covid-19. Now we are told that young people is the one who spreads infection around.
One of the best thing in this digital age is that you can check situation by yourself with open data and open source tools.

I am using the same data source from Lithuanian Open Data Portal to investigate situation on age. Source provides information on age range. 

![]({{"/images/age hist.png" | absolute_url}})

However, categorical data is not very useful for futher analysis. So I converted each range to a number, choosing a middle value. For instance, in a range [0;9] the middle value would be 4.5

With this modification I wanted to see how changes people who get sick age by the time. If I would drow scatter plot for this data ir would be grouped and ploted like dots in line as I have just one number for ten years interval. 
So I added random noise to my scatter plot to have more smooth plot.

![]({{"/images/age scatter.png" | absolute_url}})


