How do we actually find the QR factorization of a matrix $A$, given the matrix.

####  Example 
$A = \begin{bmatrix}1 & -1 & 1 \\ -1 & 3 & 6 \\ -1 & -3 & 3 \\ 1 & 5 & -4\end{bmatrix}$

- By example 1, we know $\set{u_{1}, u_{2}, u_{3}}$ is an orthonormal basis for $Col(A)$ where $u_{1} = \frac{v_{1}}{2}$, $u_{2} = \frac{v_{2}}{3\sqrt{10}}$, $u_{3} = \frac{v_{3}}{\sqrt{26}}$

Where $A = \begin{bmatrix}v_{1} & v_{2} & v_{3}\end{bmatrix}$

Let $Q = \begin{bmatrix}u_{1} & u_{2} & u_{3}\end{bmatrix}$
$\implies R = \begin{bmatrix}||v_{1}|| & c_{12}||v_{1}||  & c_{13}||v_{1}|| \\ 0 & ||v_{2}|| & c_{23}||v_{2}|| \\ 0 & 0 & ||v_{3}||\end{bmatrix}$
$= \begin{bmatrix}2 & 2 & -6 \\ 0 & 2\sqrt{10} & 0 \\ 0 & 0 & \sqrt{26}\end{bmatrix}$

Then $A = QR$

![[Maths/Intro to Linear Algebra/attachments/Pasted image 20241203233303.png]]

---

But is is not quite feasible to always find an orthonormal basis. So we use something smarter...

#theorem An $m \times n$ matrix $Q$ has orthonormal columns $\iff Q^{T}Q = I$

Basically, the transpose of the matrix is it's inverse

For this reason, $A = QR \implies Q^{T}A = Q^{T}QR = Q^{T}A = R$

Ahaa! This is slick! We can now calculate $R$ much easily by just multiplying $A$ by $Q^{T}$

## Why care about $QR$ Factorization
It's useful for solving a matrix equation/system of equations
If $A = QR$, 
$Ax = b \iff QRx = b$
$\implies Q^{T}QRx = Q^{T}b$ (since $Q$ is an orthogonal matrix, hence, $QQ^{T}=Q^{T}Q=I$)
$\implies Rx = Q^{T}b=y$
Since $R$ is an Upper triangular matrix, it is already in REF hence it is easy to solve.
For invertible $A$, this may seem dumb but $QR$ factorization yields solutions if any even for non invertible matrices. 

---
#### Example of solving system with $QR$ Factorization

- Find a QR factorization of $A = \begin{bmatrix}1 & -1 & 1 \\ -1 & 3 & 6 \\ -1 & -3 & 3 \\ 1 & 5 & -4\end{bmatrix}$ and use it to solve $Ax = b$, where $b = \begin{bmatrix}2 \\ 5 \\ 2 \\ -3\end{bmatrix}$
 $Rx = y = Q^{T}b = \begin{bmatrix}u_{1} & u_{2} & u_{3}\end{bmatrix}^{T}b = \begin{bmatrix}u_{1}^{T} \\ u_{2}^{T} \\ u_{3}^{T}\end{bmatrix}b$
$=\begin{bmatrix} \frac{1}{2} & \frac{-1}{2} & \frac{-1}{2} & \frac{1}{2} \\ \frac{-1}{\sqrt{10}} & \frac{2}{\sqrt{10}} & \frac{-1}{\sqrt{10}} & \frac{2}{\sqrt{10}} \\ \frac{4}{\sqrt{26}} & \frac{3}{\sqrt{26}} & 0 & \frac{-1}{\sqrt{26}}\end{bmatrix} \begin{bmatrix}2 \\ 5 \\ 2 \\ -3\end{bmatrix} = \begin{bmatrix}-4 \\ 0 \\ \sqrt{26}\end{bmatrix}$
Essentially, now we have $Rx = \begin{bmatrix}-4 \\ 0 \\ \sqrt{26}\end{bmatrix}$
where we already knew $R = \begin{bmatrix}2 & 2 & -6 \\ 0 & 2\sqrt{10} & 0 \\ 0 & 0 & \sqrt{26}\end{bmatrix}$
Hence, if we already have a QR factorization, it may be very simpler to solve just this and not do Gauss-Jordan.

Hence, solving $Rx = c$ we get $x = \begin{bmatrix}1 \\ 0 \\ 1\end{bmatrix}$

---

## Least-Squares problems

For $Ax=b$, we can have a consistence or inconsistent system.
So far we have dealt with a consistent system and defining solutions sets, etc.

But it can be useful to find an approximate value that works kind of like a solution. 

So the idea is to find an approximate solution $Ax \approx b$ such that the error $Ax-b$ is as small as possible

i.e. $||Ax-b||$ is minimized

But that also means that $||Ax-b||^{2}$ is minimum .

#def Let $A$ be an $m \times n$ matrix and $b \in \mathbb{R}^{m}$. A **least-squares solution** of $Ax=b$ is an $x^{*}$ in $\mathbb{R}^{n}$ such that

$||Ax^{*}-b|| \leq ||Ax-b||$ for any $x \in \mathbb{R}^{n}$

---
### Finding the approximation 
To find $Ax^{*} \in Col(A): Ax^{*}$ is the best approximation to $b$

$Ax^{*} = proj_{Col(A)}b$
(we learnt earlier that the best approximation of $b$ in a space is it's projection on the space)

So what we can do is

- Find an orthogonal Basis for $Col(A)$
	- Remember the Gram-Schmidt process... start with any vector and then find vectors that are perpendicular to that vector by subtracting its projection on that vector (and all the other such vectors you've found) from itself.
- Find the projection of $b$ as a linear combination of those basis vectors.


But there is a more cheaper way to do this.

$b - \hat{b} \in (Col(A))^{\perp} = Null(A^{T})$
($\hat{b}$ here is the projection of $b$)

$$\iff A^{T}(b-\hat{b}) = A^{T}b - A^{T}Ax^{*} = 0$$


---
So
- Solve $A^{T}A$
- Solve $A^{T}b$
Both of $A^{T}A$ is a matrix whereas $A^{T}b$ is a vector.

We now need to solve $x^{*} : A^{T}Ax^{*} = A^{T}b$
which comes down to solving $\begin{bmatrix}A^{T}A  &  |  &  A^{T}b\end{bmatrix}$
