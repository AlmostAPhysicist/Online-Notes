## Recall 
from [[Maths/Intro to Linear Algebra/Lec 17. Eigenvalues & Eigenvectors|Lec 17. Eigenvalues & Eigenvectors]], we learned that 


---
## Diagonalization (with real eigenvalues)

#def Let A be an $n \times n$ matrix. A is **diagonalizable** if A is similar to some $n \times n$ diagonal matrix D 
(being similar means they have the same characteristic polynomial $\implies$ they have the same Eigenvalues! (and multiplicity))

Diagonal matrix $D : A = PDP^{-1}$, where $P$ is invertible and D is diagonal 

$\implies A^{k} = PD^{k}P^{-1}$

Although $D$ can have complex values too, for this course we only consider matrices that have real eigenvalues.

---
## Diagonalization Algorithm 
#theorem $A_{n \times n}$ is diagonalizable $\iff$ $A$ has n linearly independent eigenvectors (which form the basis for $\mathbb{R}^{n}$) $\iff$ vector space formed by eigenvectors (NOT the eigenspace itself - for that all must correspond to the same eigenvalue) is n dimensional

Which means, if we can find the basis for $\mathbb{R}^{n}$ only using the eigenvectors, we have a diagonalizable matrix.

Say the eigenspace has vectors $\set{v_1,\dots,v_n}$ with corresponding eigenvalues $\set{\lambda_1,\dots,\lambda_n}$

Let $P = \begin{bmatrix}v_{1} & \dots & v_{n}\end{bmatrix}_{n \times n}$  and$D = \begin{bmatrix}\lambda_{1} & 0 & \dots & 0 \\ 0 & \ddots & \ddots & 0 \\ 0 & \dots & 0 & \lambda_{n}\end{bmatrix}$
then $A = PDP^{-1}$
$AP = PDP^{-1}P = PD$

$AP = A\begin{bmatrix}v_{1} & \dots & v_{n}\end{bmatrix} = \begin{bmatrix}Av_{1} & \dots & Av_{n}\end{bmatrix}$
But since $v_{i}$ here is an eigenvector, $Av_{i} = \lambda_{i}v_{i}$
$\implies AP = \begin{bmatrix}\lambda_{1}v_{1} & \dots & \lambda_{n}v_{n}\end{bmatrix} = PD = \begin{bmatrix}v_{1} & \dots & v_{n}\end{bmatrix}\begin{bmatrix}\lambda_{1} & 0 & \dots & 0 \\ 0 & \ddots & \ddots & 0 \\ 0 & \dots & 0 & \lambda_{n}\end{bmatrix} =  \begin{bmatrix}\lambda_{1}v_{1} & \dots & \lambda_{n}v_{n}\end{bmatrix}$
Hence, this particular structure works for $A = PDP^{-1}$

---
#theorem A set of eigenvectors of $A_{n \times n}$ that correspond to distinct eigenvalues is linearly independent.

##### Example 
$A = \begin{bmatrix}3 & 0 & 0 \\ 0 & 1 & 2 \\ 0 & 2 & 1\end{bmatrix}$ ^6ed610

$P(\lambda) = \text{characteristic polynomial} = |A - \lambda I| = \begin{vmatrix}3-\lambda & 0 & 0 \\ 0 & 1-\lambda & 2 \\ 0 & 2 & 1-\lambda\end{vmatrix}$

There is only 1 non zero entry in row 1, hence co factor expansion is very easy.
$|A- \lambda I| = (3-\lambda)((1-\lambda)^{2} - 2^{2}) = (3-\lambda)(1-\lambda+2)(1-\lambda-2) = (3-\lambda)^{2}(-1 - \lambda)$

Hence, $P(\lambda) = 0 = (3 - \lambda)^{2}(1-\lambda)$
hence, $\lambda_{1}=3, \lambda_{2}= -1$

*Solving for eigenvectors*
For $\lambda_{1}=3$, solve $(A-\lambda I)x = (A - 3I)x = 0$
$\implies \begin{bmatrix}0 & 0 & 0 \\ 0 & -2 & 2 \\ 0 & 2 & -2\end{bmatrix}$
(The augmented matrix only has zeros, they need not be shown since changing their positions and adding them has no effect)

$rref(A-3I) = \begin{bmatrix}0 & -2 & 2 \\ 0 & 0 & 0 \\ 0 & 0 & 0\end{bmatrix}$
$-2x_{2} + 2x_{3} = 0$

$x = \begin{bmatrix}x_1 \\ x_2 \\ x_3\end{bmatrix}$ (note how $x_{1}$ can take any form and it would not affect the solution)

$= x_{1} \begin{bmatrix}1 \\ 0 \\ 0\end{bmatrix} + x_{3} \begin{bmatrix}0 \\ 1 \\ 1\end{bmatrix}$

- $eigenspace_{\lambda_{1}} = Null(A-\lambda_{1}I) = Span \set{\begin{bmatrix}1\\0\\0\end{bmatrix}, \begin{bmatrix}0\\1\\1\end{bmatrix}}$

Now.. what did that mean?
$Av_{1} = \lambda_{1}v_{1}$ (definition of eigenvectors)
that means each vector $v_{1}$ for which this holds true is in the $Null(A-\lambda_{1}I)$

There are multiple eigenvectors corresponding to the same eigenvalue. That means, 2 different support lines scale by the same factor upon transformation.

**Important**
The reason they make a space is that any vector in the span of these eigenvectors can be a linear combination of these
$v \in Span \set{v_{1}, v_{2}} = c_{1}v_{1}+ c_{2}v_{2}$

Hence, The transformation by $A$, $Av = Ac_{1}v_{1} + Ac_{2}v_{2} = c_{1}Av_{1}+c_{2}Av_{2}$

but $Av_{1} = \lambda_{1}v_{1}$ and $Av_{2}=\lambda_{2}v_{2}$

hence, $Av = c_{1}\lambda_{1}v_{1}+ c_{2}\lambda_{2}v_{2}$

Thus, AvA vAv is a linear combination of v1v_1v1​ and v2v_2v2​ scaled by their respective eigenvalues.

**Conclusion**: The vector $v=c_1v_1+c_2v_2$ = c_1 v_1 + c_2 v_2v=c1​v1​+c2​v2​ is in the span of v1v_1v1​ and v2v_2v2​, but it is only an eigenvector of AAA if λ1=λ2\lambda_1 = \lambda_2λ1​=λ2​. When λ1≠λ2\lambda_1 \neq \lambda_2λ1​=λ2​, vvv will not behave as an eigenvector under AAA because AvA vAv will not be proportional to vvv. Instead, it will generally be a different vector in the span of v1v_1v1​ and v2v_2v2​.

**Key Point**: All linear combinations of eigenvectors with the _same_ eigenvalue (i.e., from the same eigenspace) are also eigenvectors. However, if the eigenvectors have _different_ eigenvalues, their span does not form an eigenspace, and vectors in this span are not eigenvectors.

**If you combine the eigenspaces of different eigenvalues, the resulting set is *NOT* an eigenspace since the $\lambda$ would then be different** It is however important to have the degrees of freedom in that space (even if it isn't eigenspace) to match the degree of freedom in the column space of $A$ for it to be diagonalizable (since you want to be able to reach all vectors even upon Diagonalization).


---
by a similar process of solving $(A-\lambda_{2}I)x = (A+I)x=0$ (solve $[A+I|0]$)

- $eigenspace_{\lambda_{2}} = Null(A-\lambda_{2}I) = Span set{\begin{bmatrix}0\\-1\\1\end{bmatrix}}$

- $\set{v_{1}, v_{2}, v_{3}}$ is a basis for $\mathbb{R}^{3}$ $\implies$ $A$ is diagonalizable.
(this set is a combined set of all the eigenspaces for individual eigenvalues)

- Let $P = \begin{bmatrix}v_{1} & v_{2} & v_{3}\end{bmatrix} = \begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & -1 \\ 0 & 1 & 1\end{bmatrix}$
And Hence, $D = \begin{bmatrix}\lambda_{1} & 0 & 0 \\ 0 & \lambda_{2} & 0 \\ 0 & 0 & \lambda_{3}\end{bmatrix}$



Essentially, $A= PDP^{-1}$ where $P$ is the matrix created by combining all the Eigenvectors and $D$ is the diagonal matrix of all Eigenvalues.
---

#theorem A set of eigenvectors of $A_{n \times n}$ that correspond to distinct eigenvalues is linearly independent.
#theorem If $A_{n \times n}$ has $n$ distinct eigenvalues, then $A$ is diagonalizable.
($A_{n \times n}$ can only have $n$ distinct eigenvalues if n is linearly independent)

$A_{n \times n}$ is diagonalizable $\iff$ $A$ has $n$ linearly independent eigenvectors $\iff$ $n = \sum_{i} dim(eigenspace_{\lambda_{i}}) = \sum_{i} multi_{g}(\lambda_{i})$
(recall, geometric multiplicity $multi_{g}(\lambda)$ was the number of eigenvectors corresponding to the same eigenvalue $\lambda$)
![[Maths/Intro to Linear Algebra/Lec 17. Eigenvalues & Eigenvectors#^1ebdc2|Lec 17. Eigenvalues & Eigenvectors]]
![[Maths/Intro to Linear Algebra/Lec 17. Eigenvalues & Eigenvectors#^c20120|Lec 17. Eigenvalues & Eigenvectors]]

#### Test for diagonalizable matrices 
$A_{n \times n}$ us diagonalizable $\iff$ both of the following conditions are true
- $\sum multi_{a}(\lambda) = n = \# \text{ columns of A}$
- For any eigenvalue $\lambda$ of $A$, $multi_{a}(\lambda) = multi_{g}(\lambda)$


#### Example
![[#^6ed610]]

- Condition 1
We know $P(\lambda) = (3-\lambda)^{2}(-1-\lambda) \implies \lambda_{1}=3, \quad \lambda_{2}=1$
$\implies multi_{a}(\lambda_{1}) = 2 \qquad multi_{a}(\lambda_{2}) = 1$
$multi_{a}(\lambda_{1}) + multi_{a}(\lambda_{2}) = 3$


- Condition 2
$eigenspace_{\lambda_{1}} = Span \set{\begin{bmatrix}1\\0\\0\end{bmatrix}, \begin{bmatrix}0\\1\\1\end{bmatrix}}$
$eigenspace_{\lambda_{2}} = Null(A-\lambda_{2}I) = Span \set{\begin{bmatrix}0\\-1\\1\end{bmatrix}}$
$\implies multi_{g}(\lambda_{2}) = 2 \qquad multi_{g}(\lambda_{2}) = 1$


- Since $multi_{a}(\lambda) = multi_{g}(\lambda)$ for all $\lambda$ for $A$
- Since $\sum_{i} multi_{a}(\lambda_{i}) = \# \text{ columns of A}$

Hence, $A$ is diagonalizable.



---
![[Maths/Intro to Linear Algebra/attachments/2024_11_06 11_42 am Office Lens.jpg|800]]

Although I made a small mistake there while solving for $(A-\lambda_{2}I)x=0$
(just did not consider that $x_{3}=0$ and hence $x_{1}$ must be 0 too for the system to be consistent)

I still find this to be useful to understand the general workflow.

1. Find the Eigenvalues and eigenvectors
2. compare algebraic and geometric multiplicities for each eigenvalue
3. compare the sums of algebraic multiplicity (which should be the same as sum of geometrical multiplicity, which would further just be the dimensions of eigenspace) to the $\#$ columns of A.

If All of them meet, that means for each eigenvalue $\lambda_{1}$
