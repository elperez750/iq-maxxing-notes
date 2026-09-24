
2026-09-23 16:46

Status: #baby 

Tags:

# 7 Regression Problems

##### Author: Elliott Perez


## References
https://cwu.instructure.com/courses/118699/files/16525283?module_item_id=4835522


### Notes

### Omitted Variable Bias

This happens if we forget to account for a variable in our model

![[Screenshot 2026-09-23 at 4.47.31 PM.png]]

Dependent variable: What we are measuring 

Independent variable: Essentially what we are plugging in to see how the dependent variable changes

###### Some examples of this might include: 

Dependent variable: Runtime of computer
Independent variable: RAM/ Any other hardware

Dependent Variable: Test scores
Independent Variable: Time spent studying


### Heterogenetity Bias

This is basically when you make the mistake of grouping the same category for different groups

###### A great example of this would be if we were to compare test scores of people who went to an Ivy league and those who went to a community college. Obviously, with the people that went to  the ivy league school, they most likely have more money and more access  to resources, whereas the community college students might instead be trying to save money.


These are the results when we group certain people together

![[Pasted image 20260923180316.png]]



These are the results that we are going to find when we remove the grouping on certain individuals

![[Pasted image 20260923180337.png]]


### Selection Bias

This is essentially picking people for a study without any randomization.


###### For example, if there was a survey on how much money people made, if the survey was conducted on a community college campus, you could expect people to making a similar amount of money.




### Multicollinearity


This is when multiple independent variables are strongly correlated

This means that we cannot estimate how a certain variable will impact the dependent variable

![[Pasted image 20260923181626.png]]


###### A great example of this would be if we had the size of a house in square feet, and if we then had the number of rooms in the house. These two variables are very closely related to each other, as you can imagine that the area of the house in square feet will be closely related to the amount of rooms, therefore making it hard to distinguish between the two variables


### Measurement error

This is not systematic error, but rather error when measuring certain variables.  This can happen if we just mess up logging the variables

![[Pasted image 20260923183650.png]]



![[Pasted image 20260923183703.png]]

This can happen in both the dependent and independent variables.


### Misspecification Bias

This is basically when we completely misjudge how the data reacts when certain factors are changed

###### A really good example of this would be if we are tracking test scores. If  someone were to go from studying 2 hours to 5 hours, they would see a significant shift in their grades. If that same person were to go from studying 35 hours to studying 37 hours, that two hour increase does not have the same impact, as studying more means that you are getting less sleep, or are just getting more fatigued, meaning the output will not be the same as the first few hours.

![[Pasted image 20260923185012.png]]



### Simultaneity

This is when variables are closely tied together, and form a feedback loop, where one variable impacts the other, and then that variable impacts the other and eventually the last variable will impact the first variable.


![[Pasted image 20260923185556.png]]