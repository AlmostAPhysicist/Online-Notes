---
~
---
## Matrix equation
#def A Matrix Equation:
$$Ax=b$$ ^101c64
$$\begin{align}

\text{where} \space x,b \text{ are Vectors }\in R^{n}\\
A \text{ is a matrix of dimensions } (m\times n) 
\end{align}
$$
$$A_{m \times n} = \begin{bmatrix} a_{1} & a_{2} & a_{3} \dots & a_n
\end{bmatrix}, \enspace x_{n \times 1}= \begin{bmatrix}
x_1 \\ x_2\\ x_3 \\ \vdots \\ x_n
\end{bmatrix}$$
Here, $a_i$ is a Column with $m$ elements and $x_i$ is just a scalar.

The Matrix-Vector Product is defined to be the weighted sum of each of the columns of matrix $A$, weighed by the corresponding element in the vector $x$.

>the linear combination of the columns of $A$ using the corresponding entries in $x$ as weights.
>-Zehui Zhou

Mathematically, $$Ax = x_1a_1+x_2a_2+x_3a_3\dots x_na_n$$
See? All the columns of the matrix $A$ scaled by their corresponding element in vector $x$, added together.

## Geometrical/Spacial Interpretation of a Matrix-Vector Product 

I love how Grant Sanderson presents this idea in his series: The Essence of Linear Algebra and so I would love to add that here...

Think of a vector $$x=\begin{bmatrix}
x_{1}\\x_2
\end{bmatrix}$$ as an arrow in space. But not just any space!

Think of it as a weighed sum of the arrows $\hat{i}$ and $\hat{j}$, i.e. the orthogonal unit vectors of a regular coordinate system.

![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-14-08-23-45]]

i.e. $x=x_{1} \begin{bmatrix}1 \\ 0 \end{bmatrix} + x_{2} \begin{bmatrix}0 \\ 1\end{bmatrix}$

This idea of breaking down a space into it's base vectors/unit vectors can be through of thinking about the space as a matrix

$$\text{Unit Vectors} = \begin{bmatrix}
\hat{i} & \hat{j} & \hat{k}
\end{bmatrix} = \begin{bmatrix}
1 & 0 & 0 \\ 0 & 1 & 0  \\ 0 & 0 & 1
\end{bmatrix}$$
Now to get to any vector $x$, you scale each of the base vectors with the weights $x_1$, $x_2$ and $x_3$ (and so on for higher dimensional spaces).

$$x =
x_1\hat{i} + x_2\hat{j} + x_3\hat{k}
 = \begin{bmatrix} 
 1x_1 \\ 0x_2 \\ 0x_3 
 \end{bmatrix} 
 + 
 \begin{bmatrix} 
 0x_1 \\ 1x_2 \\ 0x_3  
 \end{bmatrix} 
 + 
 \begin{bmatrix} 
 0x_1 \\ 0x_2 \\ 1x_3
\end{bmatrix} 
=
\begin{bmatrix}
x_1\\x_2\\x_3
\end{bmatrix}$$
THAT is Matrix-Vector Multiplication in action!

We just scale columns of a matrix (which in this case signifies a physics space's **Base Vectors**) by corresponding elements of a vector as weights and then sum them up.

---
$$\begin{bmatrix}
1 & 0 & 0 & \dots \\ 0 & 1 & 0  \\ 0 & 0 & 1 \\ \vdots & & &\ddots
\end{bmatrix}$$
This Matrix that corresponds to the Augmented (meaning combined) columns of unit-orthogonal-base vectors is called the **Identity Matrix** (usually denoted by I) ^63eb16

A vector $x$ can thus be said to be the Matrix-Vector product of $$Ix=x$$
Note however, that the matrix need not always be Identity. You can have all kinds of base pairs!


## Change of Bases
What if instead of $\hat{i}$ and $\hat{j}$ you had $\hat{i}$ and $\begin{bmatrix}1\\1\end{bmatrix}$, say $\vec{v}$?

![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-14-11-27-03]]


Could we still represent Vectors in this case?

Yes!
Note: change of bases does not mean you are changing the vectors' positions in space. It means you're Changing the way you get to a certain position in space... that is to say you are Changing the Linear combination of your basis vectors.

This is DIFFERENT from just multiplying a certain vector with a matrix. That WOULD change the vector indeed!

### Example 
Say we have a vector pointing to the point $(2,3)$ in space.
This can be done by a linear combination of $$2\hat{i} + 3\hat{j} = 2 \begin{bmatrix}1\\0\end{bmatrix} + 3 \begin{bmatrix}0\\1\end{bmatrix}=\begin{bmatrix}2\\3\end{bmatrix}=\vec{a}$$ (which ever form you prefer)

Thus we can, in terms of matrix vector multiplication, say that $\vec{a}$ is the Matrix vector Multiplication $$I_2\vec{a}=\begin{bmatrix}1&0\\0&1\end{bmatrix}\begin{bmatrix}2\\3\end{bmatrix}=\begin{bmatrix}2\\3\end{bmatrix}=\vec{a}$$
But say we had to represent the same point with bases $\hat{i}$ and $\vec{v}$ ($\hat{i} = \begin{bmatrix}1\\0\end{bmatrix}$ and $\vec{v}=\begin{bmatrix}1\\1\end{bmatrix}$)

WE COULD STILL SET UP A LINEAR COMBINATION 
$$\vec{a} = a_1\hat{i}+a_2\vec{v}=\begin{bmatrix}
1a_1\\0a_1
\end{bmatrix}+\begin{bmatrix}
1a_2\\1a_2
\end{bmatrix}=\begin{bmatrix}
a_1+a_2\\a_2
\end{bmatrix}$$
which should be equal to the actual value $\vec{a}=\begin{bmatrix}2\\3\end{bmatrix}$

Hence, we get 2 equations...
$a_1+a_2=2$
$a_2=3$
Which yes, we can solve it...
$a_1=-1,\quad a_2=3$

BUT! Notice how all we did was just $$\left[\begin{array}{cc|c}1 & 1 & 2\\0& 1 & 3\end{array}\right]$$
See if the above matrix is consistent or not and find its unique solution!

Ahaaa!

SOOO...

## Relation with Matrix solution
For an augmented matrix:
$u$ is a linear combination of vectors $v_1,v_2\dots\,v_n$
IF $\begin{bmatrix}v_1&v_2&v_{3}&\dots &|&u\end{bmatrix}$ is consistent ([[Maths/Intro to Linear Algebra/Lec 3. Vector Equations, Linear Combinations & Matrix-Vector Products#Linear Combination of Vectors|Lec 3. Vector Equations, Linear Combinations & Matrix-Vector Products]])

which to say u can be $u=a_1v_1+a_2v_2\dots a_nv_n$

SIMILARLY,
$Ax=b$ is the [[#^101c64|Matrix Vector Equation]] where $$A_{m \times n} = \begin{bmatrix} v_{1} & v_{2} & v_{3} \dots & v_n
\end{bmatrix}, \enspace x_{n \times 1}= \begin{bmatrix}
x_1 \\ x_2\\ x_3 \\ \vdots \\ x_n
\end{bmatrix}$$
You can say $\begin{bmatrix} v_{1} & v_{2} & v_{3} \dots & v_{n} \end{bmatrix} \begin{bmatrix}x_1\\x_2\\x_3\\\vdots\\x_n\end{bmatrix}=b$ (here $b$ is another vector)
$\implies \begin{bmatrix}v_1&v_2&v_{3}&\dots &|&x\end{bmatrix}$ is consistent

### Conclusion
>What that means is, that if you write your basis vector as a matrix of augmented vectors, augmented further with your required vector, the solution set to the augmented matrix that you get by solving for the [[Maths/Intro to Linear Algebra/Lec 2. Row Reduction & Echelon Forms#^402862|RREF]] would be the weights for the constituent basis vectors that you need to get to that certain vector.

Having a solution for the Augmented Matrix and having such a linear combination means $Ax=b$ is consistent.

Which is simply to say there are certain valid values for vector $b$ that make the Equation hold true.


AND THAT IS IMPORTANT!

---
It's not always the case that you can get from 1 vector to the other. Say both your vectors were parallel.
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-15-12-10-38]]In that case, you could no longer move at any point NOT on the x-axis. ^c70e7f

If you were to go to some point, say $(0,4)$, there would be no way to do so!

Everything, **every combination** of these basis vectors you try would fail to **SPAN** every single point outside the x-axis line. 

Hence, to span the entire space, vectors must NOT be parallel or themselves be a linear combination of other vectors in the base.

---
This is different than say multiplying our vector $\begin{bmatrix}2\\3\end{bmatrix}$ by a matrix. That would change the vector itself and point us to a different point altogether!

$(2,3)$ was only meant to be reached for weights $2$ and $3$ for basis $\hat{i}$ and $\hat{j}$. Changing the Basis might lead to a change in the point. 
>For points that do not change, those are called eigen vectors.

## Properties of Matrix-Vector Multiplication 
- $A(u+v)=Au+Av$
- $(A+B)u=Au+Bu$
- $Acu=c(Au)$ ($c$ is a scalar)
- $0_{m \times n}u=0_{m \times 1}$ (Zero Matrix... Obviously would lead you to itself)
- $Ae_i=b_i$ (The $i$th column in $b$ is just sum of the $i$th values of $A$ in each of it's columns scaled by the $i$th element of $u$)
- $A0=0$ (multiplying by a Zero Vector would lead you to a Zero Vector)
- $Iu=u$ ([[#^63eb16|Identity Matrix]])

## Homogenous and Non-Homogenous Equations 
If the Matrix equation $Ax=b$ has a valid solution $b$, i.e. it has a valid vector, it is consistent.

If that solution happens to be $0$ (i.e. $b=0$) then we say the equation is Homogenous. It's non-homogenous otherwise

So remember...
$Ax=0$ is a homogenous equation... kinda like the equation of a polynomial.

- A trivial solution to this equation would be $x=0$ (or even $A=x$ for that matter).
- If it has any more solutions, it MUST have infinite solutions. Since any more solution would mean 1 basis vector can be written as a linear combination of the others so as to nullify all of them.
	- This would mean you have more vectors than required and would hence have free variables (atleast 1)
	- $A$ would at least have 1 non-pivotal^[[[Maths/Intro to Linear Algebra/Lec 2. Row Reduction & Echelon Forms#^aea1b9|Lec 2. Row Reduction & Echelon Forms - Pivot Columns]]] column.

## More about Span 

^21b4b3

#def For a nonempty set $S = [V, \dots, V_n]$ of rectors in RM,  
we define the span of $S$ to be the set of all linear combinations of $V, \dots, V_n$, denoted by $SpanS$ or $Span\{V, \dots, V_n\}$.  
If $Span S = V$, then we say that $S$ is a generating set for  
$V$ or that $S$ generates $V$.

It is the solution set of the equation $Ax=0$
Essentially, Span is the region of space that you can get to as a linear combination of your Basis Vectors included in set $S$.

Some Obvious spans:
- $Span\{0\}=\{0\}$, a solution set would be $Ax=0$ is a span
- $Span$ of a single Vector would be it's Support line (a line passing through the origin)
- $Span$ of two non-parallel vectors would be a plane 
- $Span$ of 3 non-parallel vectors would be a space
- $Span$ of [[#^c70e7f|2 parallel vectors]] would still be a line

^5b5c39




