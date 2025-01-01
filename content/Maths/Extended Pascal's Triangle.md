So we all know Pascal's Triangle.
It's a nice piece of Mathematics that has interesting patterns.

It turns out to be the coefficients of the Binomial expansions, has intriguing prime number patterns and tables. What not.
Really beautiful. 

A quick recap:
Pascal's triangle is a sequence of rows of numbers where each element is the result of the sum of the numbers above it.

![[Maths/attachments/Drawing Pascal's Triangle|1000]]

But we can expand things further, can't we? 
The triangle spans infinitely downwards, I shall explore what lies on top.

## Obvious Puzzle Pieces
There are obviously zeros on the borders to satisfy $1+0=1$ for the 1's in the following columns

![[Maths/attachments/Drawing Pascal's Triangle Fuzzy Areas]]

There's also the fact that only $x=0$ would satisfy $x+0=0$. Hence, Even the sides would have to be $0$.

![[Maths/attachments/Drawing Pascal's triangle unknown top]]

That leaves us with a fuzzy top.


## Attempts for the top

![[Maths/attachments/Drawing Pascal's triangle - what's up there]]

It's obvious that we can have 2 numbers above the number $1$ up top. 
$a \enspace \& \enspace b : a+b=1$
Thereafter, we would have to have an alternating sequence of 
$a$ and $-a$     &     $b$ and $-b$ since $$a+(-a) = 0 \quad \& \quad b+(-b)=0$$

### Binomial expansions
Perhaps the row above the more well known pascal's triangle corresponds to $n=-1$ for $(1+x)^n$

Hence, the 1st term (index 0) would be:
$$n=-1, \quad r=0$$
$$\binom{-1}{0} = \frac{-1!}{0!\enspace((-1)-0)!} = \frac{-1!}{-1!} = 1$$
Now technically, -1! is undefined. But considering both the denominator and numerator have the same term, we can assume here that the number approaches 1.

But what is this? a? b?

Let us see what happens for the 2nd term ($r=1$)
$$\binom{-1}{1} = \frac{-1!}{1!\enspace((-1)-1)!} = \frac{-1!}{-2!} = \enspace?$$
Hmmm... that doesn't look right.
Even with the extended Integral definition of Factorials, the value of $(-1)!$ and $(-2)!$ is undefined.

So maybe we just randomly pick a side and continue a spray of 1

![[Maths/attachments/Drawing Pascal's Triangle sides]]

Let's see if we have something better...

### Maintaining Symmetry

![[Maths/attachments/Drawing Pascal's Triangle -1th row]]
We CAN define both $a$ and $b$ to be $\frac{1}{2}$. This way, we maintain the symmetrical property of the Pascal's Triangle.

That seems promising.
I currently can not think of anything better than that.

Can we however, extend the idea into the fuzziness?


Note: This [[https://youtu.be/q2daqMR3l24?si=DvpdyCu5vauqgHvB|YouTube Video]] by Dr Barker was the one that sparked this question within me. Cool channel!



