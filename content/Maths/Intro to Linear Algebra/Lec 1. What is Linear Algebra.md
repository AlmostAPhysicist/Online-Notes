Linear Algebra -> Study of Linear equation

## Definition
A **Linear Equation** in n variables $x_{1}, x_{2}, ... x_n$ is an equation of the form $$a_1x_{1} + a_2x_{2} \space+ \space...a_nx_{n}= b$$
$a$'s are numbers (coefficients)
$x$'s are variables (c)
$b$ is a constant term/number

## Example

$y=3x+2$ $\iff$ $-3x+y=2$ 
both are equivalent forms of linear equations with form $$Number \times Variable$$ as its term, equated to some $Constant$ term

---
$xy + z = 2$
$x^{2}+2y= 1$
$ln(x) = cos(y)$

These are **NOT** linear equations since they do NOT have the form $Number \times Variable$. Rather, they operate on variables OR have Variables Multiplying with other variable.

## Why Linear Algebra

- It's Simple! - Linear functions are easy to deal with
- It's Powerful!
	- You can find Intersections of 2 lines
	- ![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-04-10-31-58]]
	$$
solve \begin{cases}
y=x  \\
y=-x+2 
\end{cases}
\implies
\begin{cases}
x=1  \\
y=1 
\end{cases}
\implies
\text{A Unique Solution!}$$


## Def 
A **solution** of thr system of n vartiables is a list of n numbers that satisfy all equations in this system

## Def 
A **Solution Set** if the system is a set of all possible solutions for the system

## Example

$$
solve \begin{cases}
y=x  \\
y=-x+2 
\end{cases}
\implies
\begin{cases}
x=1  \\
y=1 
\end{cases}
\implies
\text{A Unique Solution!}$$
```desmos-graph
y=x+1
y=x
```

$$solve \begin{cases}
y=x+1  \\
y=-x 
\end{cases}
\implies
\begin{cases}
-x+y=0  \\
-x+y=1 
\end{cases}
\implies
\text{Since Left hand side is the same but the constants are different, NO SOLUTION! (Parellel Lines)}$$
NO SOLUTION.



```desmos-graph
y=x+c
y=x
```

$$so
NO SOLUTION.



$$$$solve \begin{cases}
y=x+c  \\
y=x 
\end{cases}
\implies
\begin{cases}
-x+y=0  \\
-x+y=c 
\end{cases}
$$
if $c=0 \implies$ infinitely many solutions
if $c \neq \implies$ no SOLUTION

A linear System has a unique solutions OR infinitely many solutions

## Def 
 consistent system => 1 or Infinite SOLUTION
 inconsistent system => no SOLUTION


# Solving a Linear system

## Def 
Two linear systems are called **equivalent** if they have the same solution set

So... $System 1 \rightarrow System 2$ => equivalent. 
To solve a linear system, we can turm 1 System to an equivalent but simpler System 2.


## Practice Sheet

^af8551

$$system 1\begin{cases}
x_{1}+x_{2}= 3 \space \textemdash \space eq1 \\
2x_{1}+ 5x_{2}= 9 \space \textemdash \space eq2
\end{cases}$$
$2\times eq1 \rightarrow new \space eq1$

$$system 1\begin{cases}
2x_{1}+2x_{2}= 6 \space \textemdash \space eq1 \\
2x_{1}+ 5x_{2}= 9 \space \textemdash \space eq2
\end{cases}$$
$eq1 - eq2 \rightarrow new \space eq2$
...
$$system 1\begin{cases}
x_1=2 \space \textemdash \space eq1 \\
x_2=1 \space \textemdash \space eq2
\end{cases}$$
---
## Conclusion of steps
- Interchange 2 equations
- Multiply eq by a non-zero number
- Add a multiple of one equation to the other

As you can see, it's a very lengthy and expensive process.

# Solving through a Matrix

$$\text{System of eq} \begin{cases}
a_{11}x_1+a_{12}x_2+a_{13}x_3=b_{1}\\
a_{21}x_1+a_{22}x_2+a_{23}x_3=b_1
\end{cases}$$
this system can be represented by a matrix

$$```
$$$$
\begin{matrix}
a & | & b & c \\
d & \vline & e & f \\
g & \vline & h & i
\end{matrix}
$$

## Def 
A **Matrix** is a rectangular array of numbers 
The **Size** of a matrix is $\# rows \times \# columns$
If the $\# rows =m \quad \& \quad \# columns = n$ , then the matrix is an $m\times n$ matrix $A_{m\times n}$ 




Thus,

Looking back at the [[#^af8551|Practice Sheet]]
we can represent 

$x_1+x_2=3$
$2x_1+5x_2=9$

as the Augmented Matrix
$$\left[\begin{array}{cc|c}
1 & 1 & 3 \\
2 & 5 & 9
\end{array}\right]
$$
We can then transform this into
$$\left[\begin{array}{cc|c}
1 & 1 & 3 \\
0 & 3 & 6
\end{array}\right]
$$
by subtracting $row_2 - 2row_1$
$$\left[\begin{array}{cc|c}
1 & 1 & 3 \\
0 & 1 & 1
\end{array}\right]
$$
by $row_{2}\rightarrow \space \frac{row_{2}}{3}$
$$\left[\begin{array}{cc|c}
1 & 1 & 3 \\
2 & 5 & 9
\end{array}\right]
$$$$\left[\begin{array}{cc|c}
1 & 1 & 3 \\
2 & 5 & 9
\end{array}\right]
$$

Parallel with Solving Linear equations mechanically:


- Interchange 2 equations $\rightarrow$ row switching ($r_{i}\iff r_j$)
- Multiply eq by a non-zero number $\rightarrow$ row scaling ($r_{i}\rightarrow cr_{i}, \space c\neq 0$)
- Add a multiple of one equation to the other $\rightarrow$ row Addition ($r_{i}+ cr_{j}\rightarrow \space r_i$)

Thus, all the elementary row operations is just a neat way t represent coefficients of a linear equation while solving it through any other algebraic method.


- **Every elementary row operation can be reversed**


## Def 
Matrices $A$ and $B$ are called **row equivalent** if there is a sequence of elementary row operations that transforms $A$ into $B$.

Systems are equivalent.
Hence, by definition, they have the same solution set! $\implies$ augmented matrices are equivalent.


$$System \rightarrow \space \left[\begin{array}{c|c}
A & b \\
\end{array}\right] \quad \overrightarrow{row \space operations}\quad\text{Simpler System}$$
$\int f(x) dx$

