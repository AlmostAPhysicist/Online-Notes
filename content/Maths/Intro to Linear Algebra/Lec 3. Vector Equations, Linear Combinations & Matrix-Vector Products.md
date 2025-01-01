#def a **Vector** is a matrix with exactly one column (or row)

$$column\space vector=v=\left[\begin{array}{c}
v_1 \\
v_2 \\
v_{3}\\
\vdots\\
v_n
\end{array}\right]$$
$v$ is a n-dimensional column vector, $v\in \mathbb{R}^n$ 
- $\mathbb{R}^n$ is the set of all n-dimensional column vectors/n-dimensional space meaning... it is the set of points in an n-dimensional space, hence each point would be of form (x,y,z,w... n elements)
### Parallel Transport 
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-11-10-30-03]]
You can move vectors around in space. The only defining property is that the difference between standard vectors for start and end points must be the same.

### Vector Addition 
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-11-10-38-18]]
We add vectors by parallel transporting them in a way that we were to move along first vector $u$ from start to end. And then the Start of next vector $v$ is kept at the end of first vector $v$ (a, b).

Hence, $v + u$ ends at $(a+c, b+d)$

#### Formal definition

$$Let\space v=\left[\begin{array}{c}
v_1 \\
\vdots\\
v_n
\end{array}\right] \in \mathbb{R}^{n}\quad \& \quad u=\left[\begin{array}{c}
u_1 \\
\vdots\\
u_n
\end{array}\right]\in \mathbb{R}^{n}$$
$$u+v=\left[\begin{array}{c}
u_1+v_1 \\
\vdots\\
u_n+v_n
\end{array}\right]\in \mathbb{R}^{n}$$
## Scalar Multiplication
#def A **scalar** is a real number $c\in \mathbb{R}$
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-11-10-47-30]]

#### Formal Definition
$$Let\space v=\left[\begin{array}{c}
v_1 \\
\vdots\\
v_n
\end{array}\right] \in \mathbb{R}^{n}\quad \& \quad c\in \mathbb{R}$$
then
$$cv=\left[\begin{array}{c}
cv_1 \\
\vdots\\
cv_n
\end{array}\right] \in \mathbb{R}^{n}$$
that is, each element in the vector is scaled by the scalar.
Note, if the scalar is $-ve$, it turns the vector around

### Properties about vector addition and scalar multiplication 
Let $u,v,w\in \mathbb{R}^n$ and $c,d$ be any scalars

- $u+v=v+u$
- $(u+v)+w=u+(v+w)$ (Commutative-Brackets don't matter in addition)
- $u+0=u$ where $0$ vector has the same dimensions as the $u$ vector (0 is a notation of $[0\dots 0]\in \mathbb{R}^n$)
- $(cd)u=c(du)$ (Associative-Brackets don't matter in multiplication (dot product))
- $c(u+v)=cu+cv$ (Distributive)
- $1u=u$
- $-1u=-u$
- $u-u=0$

## Linear Combination of Vectors 
#def A **Linear Combination** of n vectors $v_{1},v_{2}\dots v_n$ in $\mathbb{R}^m$ is a vector in the following form $$c_1v_1+c_2v_2+c_3v_{3}\dots c_nv_n$$ where $c_{1}\dots c_n$ are scalars (weights)

That is to say, we can move in the direction of each of the vectors for any arbitrary magnitude of our choice and are able to reach the final point.

### Example 
Determine whether $u=\begin{bmatrix}-2 \\3 \end{bmatrix}$ is a linear combination of $v_1=\begin{bmatrix}1\\0\end{bmatrix}$ and $v_2=\begin{bmatrix}0\\1\end{bmatrix}$
That is to see if $\exists \space c_{1},c_{2}$ such that $u = c_{1}v_{1}+ c_{2}v_{2}$
$\implies \begin{bmatrix}-2 \\3 \end{bmatrix} = \begin{bmatrix}c_{1}\cdot 1 + c_{2}\cdot 0 \\c_{1}\cdot 0 + c_{2}\cdot 1 \end{bmatrix}= \begin{bmatrix}c_1\\c_2\end{bmatrix}$
Hence, $c_1=-2$ & $c_2=3$
Since $c_1,c_2$ exist, $u$ is a linear combination of $v_1$ and $v_2$.

>i.e. to see if $\begin{bmatrix*}v_{1}& v_{2}&|& u\end{bmatrix*}$ has a solution

![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-11-11-31-46]]
Since here $v$ and $u$ lie on the same support line, we can never get a linear combination of such vectors that move us Beyond the line!

Note... we do not mean $v$ and $u$ here have no unique solution. That is NOT the augmented matrix. if $a$ were to be on the support line, there would obviously be a solution (inifinitely many solutions actually)

So it is the solution for [u v | a] that we need to be consistent... i.e. have any solution at all for a to be a linear combination of u and v

#def **Standard vectors** of $\mathbb{R}^n$ by
$e_1=\begin{bmatrix}1\\0\\0\\\vdots\\0\end{bmatrix}\, ,\, e_2=\begin{bmatrix}0\\1\\0\\\vdots\\0\end{bmatrix}\, ,\, e_3=\begin{bmatrix}0\\0\\1\\\vdots\\0\end{bmatrix}\, ,\, e_n=\begin{bmatrix}0\\0\\0\\\vdots\\ n\end{bmatrix}\,$ where $j^{th}$ elements for each matrix $e_j$ is 1 and every other element is 0, these are all Standard vectors

Obviously,
Every vector in $\mathbb{R}^n$ is a linear combination of the standard vectors of  of $\mathbb{R}^n$ ($v_1e_1+v_2e_{2}\dots v_ne_n$)





