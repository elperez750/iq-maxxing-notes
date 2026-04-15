


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



#### Question 1: 
Consider the sequence $\left(1, \frac{1}{2}, \frac{1}{4}, \frac{1}{8}, \frac{1}{16}, \ldots\right)$. Let $a_0 = 1$. What is $a_3$? What is $a_4$?


###### To me, it seems like the sequencing is decreasing by half of its value. Like 1 turns to 1/2, then 1/2 turns to 1/4


###### $a_3$ would simply just be $\frac{1}{8}$ . $a_4$ would just be $\frac{1}{16}$


Can you find a formula to represent this sequence?


###### Since we want the first term to be 1, then $a_0$ would simply just be $\frac{1}{2}^n$

#### The recurrence formula is the following: $a_n=\frac{1}{2}a_{n-1}$


#### Question 2: 
Another example would be the number of M&Ms from the M&M death scenario. Say we started with 20 of these, so $a_0=20$ and our data looked like this: (20, 12, 6, 4, 3, 1, 0, 0, 0...).  What is $a_3$? What is $a_5$? What is $a_{10}$?

#### Answer:
#### $a_3$ is simply 4, $a_5$ is 1, and $a_{10}$ is 0.

###### There seems to be no pattern to this, so I do not think this is a recurrence.




## Recurrence Relation
- A recurrence relation is a definition for a sequence of numbers that gives a formula for the current term in the sequence as a function of prior terms of the sequence.
- The order is the spread between the highest term in the sequence that occurs in the recurrence relation and the lowest term in sequence that occurs in the recurrence relation.


Recurrence examples:
 $a_n=2a_{n-3}$ is the same as $a_{n+1}=2a_{n-2}$ and $a_{n+2}=2a_{n-1}$


###### This makes sense. The first term is $2a_{n-3}$ which means that the next term is one more and then the next term is one more than the previous

These are not recurrences: $a_n=2(n-1)$, $b_{n+1}=n+3$, $c_n=\pi^n$

###### This also makes sense, since we cannot get the previous terms from these.



###### So with recurrences we can find an arbitrary element, say $a_{10}$ because there is a formula. There is a pattern



#### Exercise. 
Arithmetic sequence: The current term of a sequence is the sum of the prior term in the sequence and a constant amount which we call p. What is the recurrence?


###### So initial thoughts. There must be a constant p, and we must also include the prior term.

Answer:  $a_n=a_{n-1}+p$

###### So $a_{n-1}$ will represent the previous term, p is the constant.


#### The initial term in the sequence is x. Write down 4-5 terms of the sequence.

###### Since x is the initial term, then $a_0$ is simply just x

$a_0=x$
$a_1=x+p$
$a_2=x+2p$
$a_3=x+3p$
$a_4=x+4p$

###### If we start of by adding a constant p, then that constant p will be added n times depending on the terms that we have. 

By recognizing this pattern, the recurrence is the following:

$a_n=x+np$


#### Exercise: 
The first term in a sequence is 0, and the next term is 1. Subsequent terms are defined as the sum of the two prior terms. Write down the recurrence and initial conditions for this sequence.

$a_0=0$
$a_1=1$

###### This already reminds me of the [[Fibonacci sequence]].

$a_n=a_{n-1}+a_{n-2}$

###### To me this seems like the recurrence formula. We just have to find the previous two terms and then we add them up. 

###### To do this, would we have to start at the bottom and work our way up though.

so
$a_2=0+1=1$
$a_3=1 + 1=2$
$a_4=2+1=3$
$a_5=3+2=5$
$a_6=5+3=8$
$a_7=5+8=13$
$a_8=13+8=21$


Definition: A recurrence relation has the form $a_n=f(a_{n-1}, a_{n-2}, ..., a_{n-k})$ where f is a function of several variables and $a_{n-1}$ and $a_{n-2}$$ are prior terms of the sequence. 


A **Solution to a recurrence** has the form $a_n=f(n)$


#### Exercise: 
Let $a_n=a_{n-1}/a_{n-2} + a_{n-3}$ and $a_0=1, a_1=1, a_2=2$ What is the order of this recurrence relation?


the answer is 3, since this is the spread between the furthest apart terms in the recurrence. Those being 0 and. 3


#### Use the recurrence to write out terms of this sequence to $a_4$ 

$a_n=\frac{a_{n-1}}{a_{n-2}}+a_{n-3}$ 

$a_0=1$
$a_1=1$
$a_2=2$


$a_3=\frac{2}{1}+1=3$

$a_4=\frac{3}{2}+1=\frac{5}{2}$ 


A problem. Calculating the nth term of a sequence using a recurrence is time-consuming, even for a ver fast computer. Generally it is O(n).

###### This is basically what I said before. We have to start from the ground up each time.


Methods for this are:
- Write out terms
- Look for patterns


#### Exercise: Geometric sequence general case.
Let $a_n$ be proportional to the prior term, with proportionality constant c. Let $a_0=b$. Write down the recurrence. Wrote down several terms until you spot a patter. Solve the Recurrence.


###### I'm guessing proportional means that we can multiply the nth term by a certain number to get n times the certain number.

###### To flush that out, basically each new term in the sequence will be x more than the last.


so $a_1=a_0\times{c}$
$a_2=a_1\times{c}$

and another way to write this would be the following:

$a_n=a_{n-1}\times{c}$

So basically the previous term multiplied by that constant c.


###### But wait since for each time we multiply c, then to get the value of c appropriate for the given term, we must raise c to the n power. N being the term we want to calculate


so
$a_n=b\times{c^n}$

$a_1=b\times{c^1}$


$a_2=b\times{c^2}$

$a_3=b\times{c^3}$

###### This is the correct answer. The reason why the others are wrong is because we are not adding terms up like the [[Fibonacci sequence]].


#### Exercise: Geometric sequence.
Let $a_n$ be proportional to the prior term, with the proportionality constant 2. Let $a_0=3$. Write down the recurrence. Write down several terms. Solve the recurrence (using your work above); check that the solution works


$a_1=a_0\times{2}$

$a_1=3\times{2}=6$

$a_2=6\times{2}=12$

$a_3=12\times{2}=24$


###### so basically term is equal to the previous term multiplied by 2.

$a_n=a_{n-1}\times{2}$


#### Exercise:
To describe the M&M model with death an immigration, we found the recurrence was $b_n=0.5b_{n-1}+6$, $b_0=20$. Let's instead look at the general case for this recurrence, which is $a_n=ka_{n-1}+x$, $a_0=y$. Write out terms to $a_5$

$a_0=y$

$a_1=(k\times{a_0})+x$

$a_2=(k\times({k\times{a_0}}+x))+x$

$a_3=k\times({k^2\times{a_0}+kx + x})+x$

###### So here we are literally adding an extra term for each step. For example for $a_4$, there will be 3 more terms the $a_1$ 



#### The Geometric Sum Formula:

$c + cr + cr^2 + \cdots + cr^m = \sum_{i=0}^{m} cr^i = c\left(\frac{r^{m+1} - 1}{r - 1}\right)$


###### So to compare this to our last problem, $a_0$ is c in this case, since it does not change. r would simply be k in this case, since we are multiplying by k each time.

#### Exercise:
Use the geometric sum formula to solve the recurrence in the previous exercise.

using what we already know, we can set up the equation in the following way:


$a_n=k^n \times{a_0}$ + $x (\frac{k^{n-1+1}-1}{k-1})$

###### Never mind. It seems that c in this case is $k^n\times{a_{0}}$ 

###### we will raise k to the power of n, since from the last problem, we were multiplying by another k. So we went from k to $k^2$ and then to $k^3$ and so on.


simplifying the equation, we get:


$a_n=k^n \times{a_0}$ + $x (\frac{k^{n}-1}{k-1})$


###### Now we can use this to find the solution to the M&M Death and Immigration model. Remember the following:

$b_n=0.5b_{n-1}+6$, $b_0=20$

so

$b_n=0.5^n\times{20}+6(\frac{0.5^n-1}{0.5-1})$


###### For this specific problem, 0.5 will be k, since we are always multiplying 0.5 with the previous term. 6 would be x, since that is what we are always adding.


#### Exercise: 
Solve the recurrence $c_n=kc_{n-1}+x$, $c_0=x$ by writing out terms until you see a pattern, then using the geometric sum formula. (This problem has a simpler solution)


###### So I am seeing the same pattern here. I see that k is always going to be multiplied by the previous term. To me it kind of looks like the previous equation that we had. Except this time $c_0$ is equal to x.

so

$c_1=(k\times{x})+x=kx+x$

$c_2=k((k\times{x})+x)+x$ or $c_2=k^2x+kx+x$

$c_3=k((k^2x+kx+x))+x$ or $k^3x+k^2x+kx+x$

###### So it is literally the same pattern here. We are adding an extra term here.


$c_n=k^nx+k^{n-1}x+k^{n-2}+kx_+x$+

###### So if we had 10 terms here, then we start with $k^{10}$ and then $k^9$ and so on.


This is equal to the following


$\sum_{i=0}^{m}k^ix$

###### This is the same thing, but instead of writing out all the terms, we use the summation notation to say that we are summing all of the terms from $k^0x$ to $k^ix$

#### More Practice


#### Recurrence definition:
 - A recurrence relation is a definition for a sequence of numbers that gives a formula for the current term in the sequence as a function of prior terms of the sequence.
 
- The order is the spread between the highest term in the sequence that occurs in the recurrence relation and the lowest term in sequence that occurs in the recurrence relation.

#### Question 1:
Which of the following are recurrence relations and which are not.\
a) $a_n=2a_{n-1}+3a_{n-2}$

###### This is for sure a recurrence. It gives a way to give the current term using prior terms in the sequence. Those being the following:

$a_{n-1}$, $a_{n-2}$ 


b) $a_k=2(3^k)+5(4^k)$

###### This is not a recurrence. We are raising 3 and 4 to the power of k, but we are not using the previous term to derive the current term. K is independent.

c) $b_{n-1}=2n^2+3n+4$


###### Again, this is not a recurrence, since we are not using previous terms to get the current term.


d) $b_{n-1}=2(b_{k-3})^k$


###### To me, this seems to be a recurrence, since we are using a previous term, that being 

$b_{k-3}$

###### But I also see it not being a recurrence, since the definition of a recurrence specifies that it must be the term before that is used to get the current number in the sequence.



e) $c_{n+1}=2n^2+c_n$


###### This is a weird notation, since usually we are calculating the current term, and not the next term. To make this clear let me write them out:


Current term: $c_n$
Next term: $c_{n+1}$

###### But nonetheless, this would still be a sequence, since we are using the previous term to calculate the next term.


f) $c_{k+1}=3(5^{k+2}) + 2(6^{k+1})+k^2$


###### This would not be a recurrence, since we are using the next term and the term after that.



g) $d_n=4d_{n+1}$


###### The question as to whether we can use this is kind of iffy, since we are using the next term to calculate the current term. I'll come back to this.


h) $2^2+3^{k+2}=d_k+d_{k+1}$

###### This is kind of weird. But in a way I see it being a recurrence since we are using the current term and the next term to calculate the next next term if that makes any sense.


#### Question 3. 

The current term of a sequence is proportional to the prior term, with proportionality constant equal to 2. Write down this recurrence. Let the initial term of the recurrence be equal to 2. Write down several terms and solve this recurrence.



###### Ok so since we know the first term is 2, then its easy to figure out $c_0$ from here.



$c_0=2$

$c_1=c_0\times{2}$ or 4

$c_2=c_1\times{2}$  or 8

$c_3=c_2\times{2}$ or 16

$c_4=c_3\times{2}$ or 32

$c_5=c_4\times{2}$ or 64.


###### Alright now we are going up by powers of two.


so the recurrence would be the following:

$c_n=c_{n-1}\times{2}$

## Example Questions for 2nd order linear homogeneous recurrences

#### Question 1:
Find a solution to the following recurrence:
$c_n=-16c_{n-1} - 64c_{n-2}$
with initial condition $c_0=-4$ and $c_1=8$

Answer:
The characteristic equation is the following:

$x^2+16x+64$

To find the roots you can use a calculator or you can factor out this equation by hand. Either way works

The roots are $(x+8)(x+8)$

Since both of our roots are the same, our final solution must take the final form:

$C(r)^n+Dk(r)^n$

We will now plug in our $c_0$ and $c_1$ values

$-4=C(-8)^0+D(0)(-8)^0)$ so $C=-4$

###### The D values gets erased since 0 times any number will just be 0.

Plugging in C into our next equation, we get the following


$8=-4(-8)^1+D(1)(-8)^1$

so $D=3$

Now that we have our values, we can test an find the next few values in the sequence.


$c_2=-4(-8)^2+3(2)(-8)^2=128$



## Examples of Homogenous and Nonhomogeneous linear second order recurrences


Homogenous example:  $a_n=Aa_{n-1}+Ba_{n-2}$

Nonhomogeneous example: $a_n=Aa_{n-1}+Ba_{n-2}+hp^n$

Homogenous Example: $2a_{n-1} + 3a_{n-1}$

Nonhomogeneous example: $a_n=2a_{n-1}+3a_{n-1}+10(-2)^n$














