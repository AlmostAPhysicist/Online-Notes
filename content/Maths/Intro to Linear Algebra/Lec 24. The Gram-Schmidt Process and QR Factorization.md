## Orthogonal Projection Matrix 
Recall:
#theorem Let $S = \set{u_{1}, \dots, u_{k}}$ be a basis for a subspace $V$ of $\mathbb{R}^{n}$. For any $w \in \mathbb{R}^n$,
- If $S$ is orthonormal, then $proj_{v}(w) = (w \cdot u_{1})u_{1} + \dots (w \cdot u_{k})u_{k}$

The question is, can we do this process of dot multiplication as a matrix?
$proj_{v}(w) = P_{v}w$?

Yes! 
Let $U = \begin{bmatrix}u_{1} & \dots & u_{k}\end{bmatrix}$ and $P_{v} = UU^{T}$ then $proj_{v}(w) = P_{v}W$
$P_{v}$ is the orthogonal projection matrix.

Proof:
$$proj_{v}(w) = (w \cdot u_{1})u_{1} + \dots (w \cdot u_{k})u_{k} = u_{1}(u_{1}^{T} w) + \dots u_{k}(u_{k}^{T} w) = (u_{1}u_{1}^{T} + \dots u_{k}u_{k}^{T})w$$
$UU^{T} = \begin{bmatrix}u_{1} & \dots & u_{k}\end{bmatrix} \begin{bmatrix}u_{1}^{T} \\ \vdots \\ u_{k}^{T}\end{bmatrix} = u_{1}u_{1}^{T} + \dots u_{k}u_{k}^{T}$
Hence, $proj_{v}(w) = UU^{T}w$ for $U$ being the augmented matrix of the orthogonal vectors.

#### Example 
- Find the orthogonal projection matrix of $W$ where $W$ is the $Span \set{\begin{bmatrix}1\\1\\0\end{bmatrix}, \begin{bmatrix}1\\-1\\2\end{bmatrix}}$
The vectors here are orthogonal. Let $\tilde{v_{1}} = \frac{v_{1}}{||v||} = \frac{v_{1}}{\sqrt{2}}$, $\tilde{v_{2}} = \frac{v_{2}}{\sqrt{6}}$

Let $U = \begin{bmatrix}\tilde{v_{1}} & \tilde{v_{2}}\end{bmatrix}$, $P_{w} = UU^{T} = \begin{bmatrix}\tilde{v_{1}} & \tilde{v_{2}}\end{bmatrix} \begin{bmatrix}\tilde{v_{1}}^{T} \\ \tilde{v_{2}}^{T}\end{bmatrix} = \frac{v_{1}v_{1}^{T}}{2} + \frac{v_{2}v_{2}^{T}}{6} = \frac{1}{2}\begin{bmatrix}1 \\ 1 \\ 0\end{bmatrix}\begin{bmatrix}1 & 1 & 0\end{bmatrix} + \frac{1}{6}\begin{bmatrix}1 \\ -1 \\ 2\end{bmatrix}\begin{bmatrix}1 & -1 & 2\end{bmatrix}$
$\implies U = \frac{1}{2} \begin{bmatrix}1 & 1 & 0 \\ 1 & 1 & 0 \\ 0 & 0 & 0\end{bmatrix} + \frac{1}{6}\begin{bmatrix}1 & -1 & 2 \\ -1 & 1 & -2 \\ 2 & -2 & 4\end{bmatrix} = \frac{1}{3} \begin{bmatrix}2 & 1 & 1 \\ 1 & 2 & -1 \\ 1 & -1 & 2\end{bmatrix}$

What multiplying our vector will give us is the projection of $w$ for space $V$. Note! This may not be the same as vector $w$ unless $w$ lies within the space $V$.


---
## The Gram-Schmidt Process 
Q) Does every non zero subspace of $\mathbb{R}^{n}$ have an orthogonal basis?

Yes! Here's how you find it...

#theorem Let $\set{w_{1}, \dots, w_{k}}$ be a basis for a nonzero subspace $W$ of $\mathbb{R}^{n}$. It can be converted to an orthogonal basis $\set{v_{1}, \dots, v_{k}}$ for $W$ as follows.

Let's consider a base vector for our set, 
- $v_{1} = w_{1}$
we want to now define each vector to be orthogonal vector to $v_{1}$ and all other vectors defined before that.
So we want $v_{2} \perp v_{1} : Span \set{v_{1}, v_{2}} = Span \set{w_{1}, w_{2}}$
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-11-22-04-18-28]]

Hence, 
- $v_{2} = w_{2} - proj_{v_{1}}(w_{2})=w_{2}- \frac{w_{2}\cdot v_{1}}{v_{1}\cdot v_{1}}v_{1}$
Similarly,
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-12-03-10-31-19]]
- $v_{3} = w_{3} - (proj_{v_{1}}(w_{3}) + proj_{v_{2}}(w_{3}))=w_{3}- \frac{w_{3}\cdot v_{1}}{v_{1}\cdot v_{1}}v_{1} - \frac{w_{3}\cdot v_{2}}{v_{2}\cdot v_{2}}v_{2}v_{3}$
- $v_{k} = w_{k} - (proj_{v_{1}}(w_{3}) + \dots + proj_{v_{k-1}}(w_{3}))=w_{k}- \frac{w_{k}\cdot v_{1}}{v_{1}\cdot v_{1}}v_{1} - \dots - \frac{w_{3}\cdot v_{k-1}}{v_{k-1}\cdot v_{k-1}}v_{k-1}$

Essentially, sum of projections is the closest vector and hence, the difference $v_{n}-proj_{v_{n-1}}$ gives you the shortest vector (the orthogonal vector!) to the space $\mathbb{R}^{n-1}$ and spanning the space of vectors $\set{v_{1}, \dots, v_{n}}$



---
## QR Factorization 
Decomposing a matrix as a product of two other “special” matrices.
- Another use-case of the Gram-Schmidt process


#theorem If $A$ is an $m \times n$ matrix with linearly independent columns, then $A$ can be factored as $A=QR$, where $Q$ is an $m \times n$ matrix whose columns form an orthonormal basis for $Col(A)$ and $R$ is an $n \times n$ upper triangular, invertible matrix with positive diagonal entries.

Why?
- If $A$ has linearly independent columns, columns of $A$ form the basis of $Col(A)$.
Columns of $Q$ form an orthonormal basis for $Col(A)$. That's exactly what we did! We transformed a basis to an orthonormal basis.

---
### Computing $A = QR$
Let $A_{m \times n} = \begin{bmatrix}w_{1} & \dots & w_{n}\end{bmatrix}$ and $W = \set{w_{1}, \dots, w_{n}}$ is a basis for $Col(A)$
$W \xrightarrow{Gram-Schimdt} \text{orthogonal basis} \xrightarrow{normalize} \text{(orthogormal basis) } Q$

$A = \begin{bmatrix}w_{1} & w_{2} & \dots & w_{n}\end{bmatrix} \begin{bmatrix}1 & c_{12} & c_{13} & \dots c_{1n} \\ 0 & 1 & c_{23} & \dots  & c_{2n} \\ \vdots & \dots \end{bmatrix}$
But this is still not an orthonormal matrix $Q$, we need to normalize the first matrix and multiply the corresponding rows by the normals of the vectors.

![[Maths/Intro to Linear Algebra/attachments/2024_12_04 12_30 am Office Lens.pdf|2024_12_04 12_30 am Office Lens]]
