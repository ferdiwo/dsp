[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

**#Reading File**  
import thinkstats2  
resp = nsfg.ReadFemResp() 
  
**#Actual distribution**  
pmf = thinkstats2.Pmf(resp.numkdhh, label = 'actual')  
thinkplot.Hist(pmf)  
thinkplot.Show(xlabel='no. of children', ylabel='probability')  
  
**#Biased distribution**  
biased_pmf = pmf.Copy(label = 'observed')   
for x, p in pmf.Items():  
&nbsp; &nbsp; &nbsp; biased_pmf.Mult(x,x)   
biased_pmf.Normalize()  
  
**#Plotting Distributions**   
thinkplot.PrePlot(2)  
thinkplot.Pmfs([pmf,biased_pmf])  
thinkplot.Show(xlabel = 'no, of children',ylabel = 'probability')   
  
**#Mean**  
print('Actual mean', pmf.Mean())   
print('Biased mean', biased_pmf.Mean()) 

---
When running the code in the terminal, next to the probability distributions, the following output will be displayed: 
  
__Actual mean 1.024205155043831__  
__Biased mean 2.403679100664282__
  
This shows that there is a big difference between the actual and the biased distribution.

