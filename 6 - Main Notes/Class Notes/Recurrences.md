


2026-04-01 20:13

Status: #baby 

Tags:[[Latex Templates]]

# Recurrences

##### Author: None


## References
https://cwu.instructure.com/courses/116536/pages/recurrences-introduction


### Notes




| What you want                 | Syntax                          |
| ----------------------------- | ------------------------------- |
| Inline math                   | `$a_n = \frac{1}{2^n}$`         |
| Display math (centered block) | `$$a_n = \frac{1}{2^n}$$`       |
| Subscript                     | `$a_n$` → $a_n$                 |
| Superscript                   | `$x^2$` → $x^2$                 |
| Both                          | `$a_n^2$` → $a_n^2$             |
| Fraction                      | `$\frac{a}{b}$` → $\frac{a}{b}$ |
| Square root                   | `$\sqrt{x}$` → $\sqrt{x}$       |
| nth root                      | `$\sqrt[n]{x}$` → $\sqrt[n]{x}$ |
| Absolute value                | `$                              |
| Infinity                      | `$\infty$` → $\infty$           |
| Dots                          | `$\ldots$` → $\ldots$           |



## Sequence notation
- An ordered list of numbers is called a sequence
- Notation for a sequence is $a_{n}$ or $a_k$   
- The number in the $n = 4$ place for sequence $(a_n)$ is ${a_4}$.


We think of a sequence as a function on the nonnegative integer numbers so ${a_n = a(n)}$. In general, the beginning term of our sequences will be $a_0$, the $n = 0$, the zeroth term. The number at spot $n$ in our sequence where $n \in \mathbb{Z}$, $n \geq 0$ will be called current term $a_n$.



### Question 1: Consider the sequence $\left(1, \frac{1}{2}, \frac{1}{4}, \frac{1}{8}, \frac{1}{16}, \ldots\right)$. Let $a_0 = 1$. What is $a_3$? What is $a_4$?


###### To me, it seems like the sequencing is decreasing by half of its value. Like 1 turns to 1/2, then 1/2 turns to 1/4


###### $a_3$ would simply just be $\frac{1}{8}$ . $a_4$ would just be $\frac{1}{16}$


Can you find a formula to represent this sequence?


###### Since we want the first term to be 1, then $a_0$ would simply just be $\frac{1}{2}^n$

#### The recurrence formula is the following: $a_n=\frac{1}{2}a_{n-1}$


### Question 2: Another example would be the number of M&Ms from the M&M death scenario. Say we started with 20 of these, so $a_0=20$ and our data looked like this: (20, 12, 6, 4, 3, 1, 0,0, 0...). What is $a_3$? What is $a_5$? What is $a_{10}$?

