[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

**Generate 1000 random numbers**   
random_numbers = np.random.random(1000)  
pmf = thinkstats2.Pmf(random_numbers)  
thinkplot.Hist(pmf)  
thinkplot.Show(xlabel = 'number', ylabel = 'probability', axis = [0,1,0,0.005])  
  
**CDF** 
cdf = thinkstats2.Cdf(random_numbers, label = 'random numbers')  
thinkplot.Cdf(cdf)  
thinkplot.Show(xlabel='number', ylabel='CDF')  
  
When trying to plot the PMF, no proability distribution is plotted, probably due to the large amount of different values.
Hence, PMFs are rather useful for datasets with a limited number of occuring values. 
When plotting the CDF, a line chart is displayed which is expressing an almost uniform distribution. To be perfectly uniform, the line should be a straight line representing the function y = x.


