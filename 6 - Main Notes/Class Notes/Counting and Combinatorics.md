

2026-04-13 11:19

Status:

Tags:

# Counting and Combinatorics

##### Author: Linehart


## References
https://acrobat.adobe.com/id/urn:aaid:sc:VA6C2:512566eb-c936-4977-876c-449e05d09505?locale=en-US&x-product=AdobeHome%2F2.0&guid=d971758a-a491-4193-ba0e-5b3bf2a6c83c&mv2=ahome


### Notes

Let R ={4,6,8}, S = {1,2,3,4,5,6,7,8,9,10}, T = {3,9,12,15} and let our universal set U = {1,2,3,...,20}.

#### Exercise: What is $S\cup{T}$

###### The answer here would be everything in S and everything in T. That is {1, 2, 3, 4, 4, 5, 6, 8, 9, 10, 12, 15}

###### Notice here we do not repeat elements


#### Exercise: What is $S\cap{T}$

###### The answer here is that it would be everything that is in both S and T. So this would be {3,9}


#### Exercise: A restaurant has 12 beverage choices, 6 appetizers, 8 entrees, and 5 desserts. How many ways to order one item from each category?


Answer: $6\times{8}\times{5}\times{12}$

###### The logic here is that if we are picking only one category, then all the combinations that are possible would be all of them multiplied together




#### Exercise: How many ways to order if you skip any category except for a drink and a delicious dessert?


Answer: $12\times{7}\times{9}\times{5}$

###### The logic here is that now since we have the option to skip the appetizer and to skip the entree, we now add an extra option to those categories.


#### Exercise: Assume S has 7 elements and T has 6 elements


#### a) How many total functions are there from S to T?

Answer: $6^7$ 

###### So to recap, a total function is a function where each input must map to an output, meaning we cannot have undefined as one of our outputs. In set S, we have 7 elements, which can map to 6 options. This gives us $6^7$



#### Exercise: In How many ways can 17 students (including Jack and Jill) line up in a row for a photograph if Jack insists on standing next to Jill (to Jill's right or left)


Answer: $16!\times{2!}$ 

###### The logic here is simple. Since we want Jack and Jill to be together, we consider that a group, so that means that the total combinations would be 16!, since we already know the position of one group, which is Jack and Jill. We must then multiply 16! by 2! since we can order Jack and Jill in two different ways



