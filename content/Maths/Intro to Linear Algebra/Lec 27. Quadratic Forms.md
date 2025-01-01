So far, we've learned about using matrices and **Linear** algebra to solve a linear system of equations.

But what about higher order systems of equations?

---
## Quadratic Equation Systems 

### Examples
- $x_{1}^{2} + x_{2}^{2} = 1$
$\implies 1 = (\sqrt{x_{1}^{2} + x_{2}^{2}})^{2}$
$\implies 1 = (||\begin{bmatrix}x_{1} \\ x_{2}\end{bmatrix}||)$

Ahaa!

$\implies 1 = \begin{bmatrix}x_{1} & x_{2}\end{bmatrix} \begin{bmatrix}x_{1} \\ x_{2}\end{bmatrix} = x^{T}x$

- $2x_{1}x_{2} = 1$
$\implies 1 = \begin{bmatrix}x_{1} & x_{2}\end{bmatrix}\begin{bmatrix}x_{2} \\ x_{1}\end{bmatrix}$
This ($x_{1}x_{2}$) is called the cross product term.

This isn't simply a $x^{T}x$ situation 
instead, $\begin{bmatrix}x_{2} \\ x_{1}\end{bmatrix}$ is a rotated form of $\begin{bmatrix}x_{1} \\ x_{2}\end{bmatrix}$

The $x$ is flipped to $y$ and $y$ is flipped to $x$.

$\implies 1 = x^{T} \begin{bmatrix}0 & 1 \\ 1 & 0\end{bmatrix}x$
where the last part is essentially a flipped version of $x$.

---
### Definitions and Formalism
#def A **quadratic form** on $\mathbb{R}^{n}$ is a function $Q$ on $\mathbb{R}^{n}$ such that $Q(x) = x^{T}Ax$, where $A$ is an $n \times n$ symmetric matrix.

$A$ is called the matrix of the quadratic form.

---
### More examples 
- Compute the quadratic form $x^{T}Ax$ when $A = \begin{bmatrix}1 & 2 \\ 2 & 3\end{bmatrix}$
$Q(x)=x^{T}Ax = \begin{bmatrix}x_{1} & x_{2}\end{bmatrix}\begin{bmatrix}1 & 2 \\ 2 & 3\end{bmatrix}\begin{bmatrix}x_{1} \\ x_{2}\end{bmatrix}$
$= x_{1}^{2}+2x_{1}x_{2} + 2x_{2}x_{1} + 3x_{2}^{2}$

Notice how the diagonals are coefficients of $x_{1}^{2}$ and $x_{2}^{2}$ whereas the off diagonals are coefficients of $x_{1}x_{2}$ and the 

#important 
$\text{coefficient of }x_{i}x_{j} = \cases{a_{ii} \quad i=j \\ 2a_{ij} \quad i \neq j}$

---
- Find the matrix of quadratic form assuming $x \in \mathbb{R}^{2}$
a) $Q(x) = x_{1}^{2} - 2x_{1}x_{2}+x_{2}^{2}$

$A=\begin{bmatrix}a_{11} & a_{21} \\ a_{12} & a_{22} \end{bmatrix}$
where $a_{11}$ is the coefficient of $x_{1}^{2}$ and hence, $a_{11} = 1$

$a_{12}= a_{21} = \frac{1}{2}(-2) = -1$ (both add up to coefficient of $x_{1}x_{2}$)
and hence $a_{22}=x_{2}^{2}$

---
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-12-06-04-13-37|800]]

## Change of variable in $Q(x)$

We can, without changing the value, change the type of quadratic form to convert it into a positive/negative/indefinite by **changing the variable**. We can then determine what sign the value has based on the input value in our new space.

I.e., we kind of change the **space** by a transformation matrix $P$ which is **invertible**. 

$x=Py \implies y = P^{-1}x$

$Q(x)=x^{T}A_{n \times n}x = (Py)^{T}A(Py) = (y^{T}P^{T})A(Py) = y^{T}(P^{T}AP)y$

If $P^{T}AP=D$ is a diagonal matrix,
We don't have any cross product term and hence we only have some 
$d_{11}y_{1}^{2} + \dots + d_{nn}y_{n}^{2}$ form which for all real values of $y$ would only be determined by the signs of $d$.

So if all values of $d$ are positive, the quadratic form would be positive definite, etc.
That is, the question to what form it is is determined only by the weights, for all nonzero values of $y$.

$P^{T}AP=D \implies PDP^{T}=A$

Ahaa!

So if $A$ is an orthogonal diagonalizable matrix, then we can transform our space in the way we want.

![[Maths/Intro to Linear Algebra/Lec 26. Diagonalization of Symmetric Matrices#Diagonalization and Orthogonal Matrices|Lec 26. Diagonalization of Symmetric Matrices]]

---
#### Example
Make a change in variable $x=Py$ that transforms the quadratic form into one with no cross product terms. Then classify the quadratic form.

$Q(x)=x_{1}^{2}-2x_{1}x_{2}+x_{2}^{2}$

We know $Q(x)=x^{T}Ax$ has $A = \begin{bmatrix}1 & -1 \\ -1 & 1\end{bmatrix}$
(look at the previous part of the examples)

Next we find the orthogonal Diagonalization of $A$.

So we Find it's eigenvalues, eigenvectors and normalize them.

Then, we can write $A = PDP^{-1}$ where $P$ is the matrix formed by the normalized eigenvectors and $D$ has the corresponding eigenvalues.

Thus, we know $D = P^{-1}AP$
And hence, we can use that to write $x=Py$ in $Q(x) = x^{T}Ax$
$\implies Q(x) = (Py)^{T}A(Py) = (y^{T}P^{T})A(Py) = (y^{T})(P^{T}AP)y$
$\implies Q(x)=y^{T}Dy = \lambda_{1}y_{1}^{2}+\lambda_{2}y_{2}^{2}$
And $x=Py$

For this particular situation, solving the characteristic equation, etc. gives us $\lambda_{1}=\lambda_{2}=1$

---
$Q(x) = -x_{1}^{2}+4x_{1}x_{2}-x_{2}^{2} = x^{T}Ax = y^{T}Dy$
$A=\begin{bmatrix}-1 & \frac{4}{2} \\ \frac{4}{2} & -1\end{bmatrix} = \begin{bmatrix}-1 & 2 \\ 2 & -1\end{bmatrix}$

Solving $P(\lambda) = |A-\lambda I| = 0$ we get $\lambda_{1}=1$, $\lambda_{2}=-3$

The corresponding normalized eigenvectors are $\begin{bmatrix}\frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}}\end{bmatrix}$ and $\begin{bmatrix} \frac{-1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}}\end{bmatrix}$
Hence, $D = \begin{bmatrix}1 & 0 \\ 0 & -3\end{bmatrix}$
$P= \begin{bmatrix} \frac{1}{\sqrt{2}} & \frac{-1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}}\end{bmatrix}$

Hence, $x=Py \implies Q(x)=x^{T}Ax = y^{T}Dy = y_{1}^{2}-3y_{2}^{2}$
Hence, since depending on the values of $y_{1}$ and $y_{2}$, you can have both positive and negative values,

This is an indefinite quadratic form.

---
Since the values of quadratic forms without a cross product term is determined only by the values of $\lambda$, we can find the type of quadratic form by seeing if $\lambda_{i}$ are all positive (in which case )