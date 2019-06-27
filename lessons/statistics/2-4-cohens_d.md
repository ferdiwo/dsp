[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> 
CODE:  
firsts = live[live.birthord == 1]   
others = live[live.birthord != 1]   

first_hist = thinkstats2.Hist(firsts.totalwgt_lb, label='first')  
other_hist = thinkstats2.Hist(others.totalwgt_lb, label='other')   


#Creating a histogram  
width = 0.45   
thinkplot.PrePlot(2)  
thinkplot.Hist(first_hist, align='right', width=width)  
thinkplot.Hist(other_hist, align='left', width=width)  
thinkplot.Config(xlabel='Birth weight (pounds)', ylabel='Count', xlim=[0, 25])  


#Summary Statistics  
mean1 = firsts.totalwgt_lb.mean()  
var1 = firsts.totalwgt_lb.var()  
std1 = firsts.totalwgt_lb.std()  

mean2 = others.totalwgt_lb.mean()  
var2 = others.totalwgt_lb.var()  
std2 = others.totalwgt_lb.std()  


#Output  
print('First born babies: \n'+'Mean: '+str(round(mean1,2))+'\nVariance: '+str(round(var1,2))+
      '\nStandard Deviation: '+str(round(std1,2)))      
print('\nOther babies: \n'+'Mean: '+str(round(mean2,2))+'\nVariance: '+str(round(var2,2))+
      '\nStandard Deviation: '+str(round(std2,2)))  

if mean1 > mean2: 
    print('\nFirst born babies are heavier than other babies!')   
else:  
    print('\nOther babies are heavier than first babies!')  


#Computing Cohen's effect size  
diff = mean1 - mean2  
n1, n2 = len(firsts), len(others)  

pooled_var = (var1*n1+var2*n2)/(n1+n2)  
d = diff/(pooled_var**0.5)  

print(round(d,2))  

---
RESULTS:  

Summary Statistics:  
First born babies:   
Mean: 7.2   
Variance: 2.02  
Standard Deviation: 1.42  
 
Other babies:   
Mean: 7.33     
Variance: 1.94  
Standard Deviation: 1.39   

The summary statistics show that first born babies on average are lighter than other babies, as they weigh on average 7.2 pounds, while other babies weigh 7.33 pounds on average. But the variance in weight for first-born babies is also larger than the variance for other babies. Therefore, we should take a look at Cohen's effect size.  
```
Cohen's d: -0.09  
```
The difference in means is -0.09 standard deviations between first born babies and other babies. This value is relatively small and therefore not significant. This could be lead back to outliers or insufficient data.  
