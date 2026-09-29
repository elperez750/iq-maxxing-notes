
2026-09-28 09:49

Status:

Tags:

# Simple Linear Regression Model

##### Author: Elliott Perez


## References



### Notes

Q) Suppose we want to know the impact of fertilizer use on fertilizer yield, holding all else equal (Ceteris Paribus)

$$yield=\beta_{0}+\beta_{1}fertilizer+u{}$$

$$\beta_{0}$$ is the intercept term. Meaning this will be the value if there is no fertilizer that is being used.

$$\beta_{1}$$
$$\Delta yield = \beta_{1}\Delta fertilizer$$

The change in the yield is the slope times the change in the fertilizer

$$u$$
is the error term. This will contain anything other that fertilizer that will affect yield. Things such as soil type, sun exposure, and temperature. All of these are bundled into the error term.


###### It is impractical to hold all other variables equal, so we have to try our best to come up with an environment where all other variables are held equal.



Q2) How do we know about ceteris paribus impact when we are ignoring everything else?

In a random sample, we want to test with different plots of land. We need to have additional assumptions on u, which is the error term. Because x and y are random variables, we need probabilistic restrictions. 


### Zero conditional mean assumption


$$E(u| x)=0$$
"Given what we do know (X), we can't say anything about the stuff we don't know (u)"

if the value is 0, that means that you cannot infer an error from the x value, meaning the term is exogenous


$$E(u)$$
This means the expected value of





