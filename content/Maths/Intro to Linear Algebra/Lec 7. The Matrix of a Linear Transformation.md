Recall from [[Maths/Intro to Linear Algebra/Lec 6. Linear Transformations#^429a8d|Lec 6. Linear Transformations]] that A transformation is **linear** if 
$$T(cu+dv)=T(cu)+T(dv)=cT(u)+dT(v)$$
and it follows that  $T(c_{1}v_{1}+\dots+c_{n}v_{n}) = c_1T(v_1)+\dots+c_nT(v_n)$
Which means the Linearly Transformed image of a linear combination can be another linear combination with the same weights.

## Example 
Let $e_{1}= \begin{bmatrix}1\\0\end{bmatrix}$, $e_{2}= \begin{bmatrix}0\\1\end{bmatrix}$, $y_1=\begin{bmatrix}1\\-1\end{bmatrix}$, $y_2=\begin{bmatrix}1\\1\end{bmatrix}$
and let $T:\mathbb{R}^2\to\mathbb{R}^2$ be a linear transformaton that maps $e_1$ into $y_1$ and $e_2$ into $y_1$. Find images of $v=\begin{bmatrix}2\\3\end{bmatrix}$ and $x=\begin{bmatrix}x_1\\x_2\end{bmatrix}$

if $v=c_1e_1+c_2e_2$, then $T(v)=c_1T(e_1)+c_2T(e_2)=c_1y_1+c_2y_2$

So our question boils down to finding what linear combination of $e_1$ and $e_2$ gives us our vector of interest.

So to solve equation $\begin{bmatrix}e_1&e_2\end{bmatrix}\,\begin{bmatrix}c_1\\c_2\end{bmatrix}=v$
Which means to solve for $c_1$ and $c_2$, we can solve the augmented matrix $\begin{bmatrix}e_1&e_2&|&v\end{bmatrix}$

$$\left[\begin{array}{cc|c}
1 & 0 & 2 \\
0 & 1 & 3
\end{array}\right]$$
Hence, $c_1=2$ and $c_2=3$.
Hence, $T(v)=c_1T(e_1)+c_2T(e_2)=c_1y_1+c_2y_2=2\begin{bmatrix}1\\-1\end{bmatrix} + 3\begin{bmatrix}1\\1\end{bmatrix}=\begin{bmatrix}5\\1\end{bmatrix}$

---
Following this, in general, the image of vector $\begin{bmatrix}x_1\\x_2\end{bmatrix}$ would be calculated by finding what linear combination of our known vectors gives us this vector of interest by solving $$\left[\begin{array}{cc|c}
1 & 0 & x_1 \\
0 & 1 & x_2
\end{array}\right]$$
So since  $x=x_1e_1+x_2e_2\implies T(x)=x_1y_1+x_2y_2=\begin{bmatrix}x_1+x_2\\-x_1+x_2\end{bmatrix}$ 

---
In [[Maths/Intro to Linear Algebra/Lec 6. Linear Transformations#^429a8d|Lec 6. Linear Transformations]] we established that every matrix transformation is a linear transformation, it would be interesting to know if the other way around is true as well.

Matrix Transformation $\rightarrow$ Linear transformation
Matrix Transformation $\leftarrow$ Linear Transformation ***?***

## Example 
In the example [[Maths/Intro to Linear Algebra/Lec 6. Linear Transformations#^c92dd6|above]] can we find a matrix $A$ such that $T(x)=Ax$?
That is, we know that we had a linear transformation whose property we used in the question. Can we perform the same Linear Transformation through a matrix vector multiplication?

That is, is the linear transformation equivalent to a Matrix Transformation?

$T(x)= \begin{bmatrix}1\cdot x_{1} + 1\cdot x_2\\-1\cdot x_{1} + 1\cdot x_2\end{bmatrix}$
$= \begin{bmatrix}1&1\\-1&1\end{bmatrix}\,\begin{bmatrix}x_1\\x_2\end{bmatrix}=\begin{bmatrix}y_1&y_2\end{bmatrix}\,x$
$$=\begin{bmatrix}
T(e_1)&T(e_2)\,x
\end{bmatrix}$$

#theorem 
Let $T:\mathbb{R}^2\to\mathbb{R}^2$ be a linear transformation. Then there exists a unique matrix A such that $T(x)=Ax$ for all $x\in \mathbb{R}^n$, 
A is given by $$A_{m\times n}= \begin{bmatrix}
T(e_{1}) & \dots T(e_n)
\end{bmatrix}$$
## Different types of Transformations 

We have a few questions regarding tracking back points in the Co-domain of the transformation to possible images 
1. Is there a pre-image $x$ in Domain for a particular vector $c$ in the Co-domain?
2. Is this $x$ unique?

Answering question 1:
#def 
A transformation $T:\mathbb{R}^{n}\to \mathbb{R}^m$ is said to be **onto** $\mathbb{R}^m$ if each $c \in \mathbb{R}^m$ is the image of at least one $x \in \mathbb{R}^n$. 
meaning, an **onto** function/transformation is defined to have the Range(T)=Co-Domain(T).

Meaning, every point in the Co-Domain can be tracked back to at least 1 value in the Domain.

Answering question 2:
#def 
A transformation $T:\mathbb{R}^{n}\to \mathbb{R}^m$ is said to be **one-to-one** if each $b \in \mathbb{R}^m$ is the image of at most one $x \in \mathbb{R}^n$.
Note:
Here, the transformation can have values in the Co-Domain with ZERO pre-images in the domain. But it should AT MOST have 1 pre-image. Meaning, if $x$ exists, it must be unique for the transformation to be defined as one-to-one.

Hence, based on the two questions, we classify our class of transformation functions as 
- onto
- one-to-one
---
==One-to-one==

Any linear transformation $T(x)$ given by $Ax=b$ is one-to-one if there are several inputs $x$ for the same output $b$.

$x$ is just a solution to solving the augmented matrix $\begin{bmatrix}A|b\end{bmatrix}$ 
meaning, is b a linear combination of columns of matrix $A$.

For multiple $x$ inputs to exist, there must be multiple ways to combine columns of $A$ to get $b$. Meaning, there must be some dependence within columns of $A$.
Meaning, $c_1v_1+c_2v_2\dots+c_nv_n=0$ would have non-trivial solutions such that any 1 of $v_i$ can be a linear combination of all other basis vectors.

i.e. if $\begin{bmatrix}A|0\end{bmatrix}$ has non-trivial solutions, there are multiple ways to reach vector b from our matrix transformation, hence the function is many-to-one and NOT one-to-one.

- $Ax=0$ has only the trivial solution
- columns of A are linearly independent
- A has a pivot position in each **columns** 
	- meaning all columns are pivot columns (hence no free variables)

==Onto==
To check if $T$ maps all of $\mathbb{R}^2$ **onto** $\mathbb{R}^3$, we need to check if $Ax=b$ is consistent for any $b \in \mathbb{R}^3$ or if the $Span\{\text{columns of A}\}=\mathbb{R}^3$

which is to check if rref(A) or ref(A) has a zero row or not.
if $A$ has a $\begin{bmatrix}0&0&0\end{bmatrix}$ row, $\begin{bmatrix}A|b\end{bmatrix}$ would have a $\begin{bmatrix}0&0&0&|&b_i\end{bmatrix}$ row and would hence be inconsistent.

Since $Ax=b$ is equivalent to $\begin{bmatrix}a&b&c\\e&f&g\\h&i&j\end{bmatrix} \begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix}=\begin{bmatrix}b_1\\b_2\\b_3\end{bmatrix}= \begin{bmatrix}x_1a+x_2b+x_3c\\x_1e+x_2f+x_3g\\x_1h+x_2i+x_3j\end{bmatrix}$
we can see that rows of $A$ correspond to dimensional elements of output $b$.

If a row of $A$ is zero, then the output misses any possibility of a dimension.

Since for a matrix $A_{m\times n}$ for $m>n$ there has to be a zero row since you will run out of pivot columns, linear transformation $T:\mathbb{R}^{n} \to \mathbb{R}^m$, $m>n$ can never be Onto.

(You can't map a lower dimensional space into a higher dimensional space while being linear)


- $Span\{\text{columns of A}\}=\mathbb{R}^3$
- rref(A) or ref(A) has no zero rows
- A has a pivot position in each **row**


![[Maths/Intro to Linear Algebra/attachments/Matrix Transformation Notes.jpg]]


If a function is both One-to-one and Onto, it's called a **Bijective** function.