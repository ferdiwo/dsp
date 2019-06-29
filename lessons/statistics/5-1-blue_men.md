[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

import scipy.stats  

#Initiating normal distribution  
mu = 178  
sigma = 7.7  
dist = scipy.stats.norm(loc=mu, scale=sigma)   
  
#Convert height in feet and inches into cm    
feet = 30.48  
inch = 2.54  

#Calulcate boundaries in centimeters  
height_lower_boundary = 5*feet+10*inch  
height_upper_boundary = 6*feet+1*inch  

#Calculate percentage of people falling below a certain value  
cdf_lower = dist.cdf(height_lower_boundary)  
cdf_higher = dist.cdf(height_upper_boundary)  

#Computing the area between the two boundaries  
percentage_between_heights = cdf_higher - cdf_lower  
  
print(str(round(percentage_between_heights,4)*100)+'%')  
  
**34.27% of the male population represented in this survey are between 5'10" and 6'1". Therefore, we know that 34.27% of the male population could be part of the Blue Men Group.**
