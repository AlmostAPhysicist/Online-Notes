
## Recall 
[[Maths/Intro to Linear Algebra/Lec 4. Matrix-Vector Multiplication|Lec 4. Matrix-Vector Multiplication]]
Is $\begin{bmatrix}1\\-1\\1\end{bmatrix}$ in the span of $S=\displaystyle\{\begin{bmatrix}1\\-4\\0\end{bmatrix}, \begin{bmatrix}3\\-9\\1\end{bmatrix}, \begin{bmatrix}1\\2\\2\end{bmatrix}\}$?

- That is to say if $u$ is a linear combination of $a_1,a_2,a_3$.
- Which is to say whether $\begin{bmatrix}a_1&a_2&a_3&|&u\end{bmatrix}$ is consistent.
- Which is to say $Ax=u, \quad A=[a_1\,a_2\,a_3]$ is consistent.
	- Note how this is just the 2nd iteration, but we explicitly say the coefficients are weights of elements of $x$
So when you see **parametric vector form**:
	- Write equation system
	- Convert to matrix A
	- write augmented matrix $[A\,|\,b]$
	- solve the augmented matrix system by reducing to [[Maths/Intro to Linear Algebra/Lec 2. Row Reduction & Echelon Forms|RREF]]
		- If there is a $[0\,0\,0\,|\,b]$ row, it is inconsistent!
		- else it is consistent
		- $[0\,0\,0\,|\,0]$ row's presence means consistent with $\infty$ solutions

Say you get a RREF as follows:
$$\left[\begin{array}{ccc|c}
1 & 0 & -5 & -2 \\
0 & 1 & 2 & 1 \\
0&0&0&0
\end{array}\right]$$
That means the **Parametric Vector Form** is
$$\begin{cases}
x_1-5x_3=-2 \\
x_2+2x_3=1 \\
0=0
\end{cases}
\implies
\begin{cases}
x_1=-2+5x_3\\
x_2=1-2x_3 \\
x_3=x_3
\end{cases}
$$
$$\implies x=\begin{bmatrix}
x_1\\x_2\\x_3
\end{bmatrix}
=
\begin{bmatrix}
-2\\1\\0
\end{bmatrix}
+ x_3\begin{bmatrix}
5\\-2\\1
\end{bmatrix}$$
## Defining Parametric Vector Form
>Writing a system solution as a linear combination of some vectors with the free variables of our solution set being the weights (or parameters) is called the parametric vector form. $(P+x_3V)$

---
## Parametric Vector Form Solutions for Homogenous vs Non Homogenous systems

$\begin{align}x_1+3x_2+x_3=0\\-4x_1-9x_2+2x_3=0\\x_2+2x_3=0\end{align}$ is a Homogenous System $b=\begin{bmatrix}0\\0\\0\end{bmatrix}$

---

$\begin{align}x_1+3x_2+x_3=1\\-4x_1-9x_2+2x_3=-1\\x_2+2x_3=1\end{align}$ is a Non-Homogenous System $b\neq\begin{bmatrix}0\\0\\0\end{bmatrix}$
[[Maths/Intro to Linear Algebra/Lec 4. Matrix-Vector Multiplication#Homogenous and Non-Homogenous Equations|Lec 4. Matrix-Vector Multiplication]] recall from here

Solution for Homogenous equation would be $x_3V$
Solution for Non-Homogenous equation would $P+x_3V$
(Note if the constant vector $b$ is the only point of difference, $x_3V$ term would be same. $P$ would be the only difference in the solution)

![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-18-10-49-22]]
Essentially, 
The homogeneity if only differs due to $b$, the solution sets would be identical except shifted across the plan by a vector $P$.

#theorem
Let p be a solution of $Ax=b$, then the solution set of $Ax=b$ is set of all vectors of form $w=p+V_h$ , where $V_h$ is any solution of $Ax=0$.
(Any point lying on a certain line can be sum of Position vector $P$ on the line and vector $V$ scaled by scalar $x_i$. (The  2nd term... $x_iV$ happens to also be solutions to a homogenous matrix vector))

$\begin{cases}Ap=b\\AV_h=0\end{cases}\implies A_w=A(p+V_h)=Ap+AV_h=b+0=b$

$Ap=b$ has a variable $p$ that can be any vector in the Solution set.
we know vector $b$ is just 1 of the solutions, to the line of the solution sets must be $V_h+b$

---

## Linear Independence

$Ax=0$
When does this have a 
- Unique solution (Linearly Independent)
- Infinitely many solutions? (Linearly Dependent)

That is what we're gonna answer.

$Ax= \begin{bmatrix}a_1&a_2&\dots &a_n\end{bmatrix}\begin{bmatrix}x_{1}\\x_{2} \\\vdots\\x_n\end{bmatrix}$

$\vec{v_1}+2\vec{v_2}=3\vec{v_3}=\vec{0}$
then $\vec{v_1}$ is a linear combination of $\vec{v_2}$ and $\vec{v_3}$

**$\vec{v_1}$ depends on $\vec{v_2}$ and $\vec{v_3}$**

#def 
A set of n vectors in $\mathbb{R}^m$ is linearly dependent if there exists scalars $c_1,\dots c_n$, not all zero, such that $c_{1}v_{1}+\dots c_nv_n=0$ implying that at least 1 vector is a linear combination of the other vectors.

That is to say equation $x_1v_1+\dots x_nv_n=0$ has non trivial solutions ($c_1,\dots c_n$ as discussed earlier).

#def 
A set of n vectors in $\mathbb{R}^m$ is linearly independent if equation $x_1v_1+\dots x_nv_n=0$ has only a trivial solution ($c_1,=\dots c_n=0$)

## Example
If solution set has just 1 vector $S=\{\vec{v_1}\}$ ($v_1\neq0$) then it is linearly independent. since $x_1=0$ is a trivial solution, there wouldn't be any other solution for $A\cdot e(S)=0$

If $S=\begin{Bmatrix}\vec{v_2}&\vec{v_1}\end{Bmatrix}$
if in this set, $\vec{v_1}$ is given/proven to be a linear combination of $\vec{v_2}$ then it is linearly dependent.

$S=\begin{Bmatrix}\vec{0}&\vec{v_1}&\vec{v_2}\end{Bmatrix}$
is linearly dependent since 1 of the vectors ($\vec{0}$) can be written as a linear combination of other vectors $\vec{0} = 0\vec{v_1}+0\vec{v_2}$.

#theorem 
If a set $S=\set{v_1,v_2,\dots,v_n}$ in $\mathbb{R}^m$ contains the zero vector, then $S$ is linearly dependent right off the back.
if $x_1\vec{v_1}+\dots+x_n\vec{v_n}=0$ has nonzero solution that means 
- $Vx=0$ matrix equation where $V=\begin{bmatrix}v_1&v_2&\dots&v_n\end{bmatrix}$ has nonzero solution
- There are free variables in the RREF or the solution set of augmented matrix



![[Maths/Intro to Linear Algebra/attachments/WhatsApp Image 2024-09-18 at 11.56.00_afe9143f.jpg]]


To prove:
Any set $S=\set{v_1,\dots,v_n}$ in $\mathbb{R}^m$ is linearly dependent if $n>m$. ^826bcf

$v = \begin{bmatrix}v_1&\dots&v_n\end{bmatrix}_{m\times n}$   $n>m \implies$
- Number of Pivots $\leq$ m
- non-pivot column = n $-$ # pivot > 0
- at least 1 non pivot column
- at least 1 free variable 
- infinity many solutions 
- has a nonzero solution 
- S is linearly dependent.

---
## Example 
b) $$S = \set{\begin{bmatrix}
1\\0\\0
\end{bmatrix},
\begin{bmatrix}
2\\1\\0
\end{bmatrix},
\begin{bmatrix}
0\\2\\1
\end{bmatrix}}
$$Let $A = \begin{bmatrix}a_1&a_2&a_3\end{bmatrix}$
solve $Ax=0$ 
if in RREF/REF there is no free variable, S is linearly independent
else it is linearly dependent.
