
2026-09-23 20:09

Status:

Tags:

# [[Euclid]] Algorithm Notes

##### Author: Elliott Perez


## References



### Notes


## Pseudo code for subtraction of Euclid's algorithm


while a != b
	if a > b
		a = a - b
	else
		b =  b - a


###### Worked example, a = 48,  b = 18

Step 1: 48 > 18 so a = 48 - 18 = 30
Step 2: 30 > 18 so a = 30 - 18 = 12
Step 3: 18 > 12 so b = 18 - 12 = 6
Step 4: 12 > 6 so a = 12 - 6 = 7

###### This is where the algorithm would terminate, as we see that both a and b are equal




