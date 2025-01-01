## Orthogonal Projections
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-11-20-11-37-12]]

#theorem 
If $\set{v_{1}, \dots , v_{k}}$ is an orthogonal basis for a subspace $V \in \mathbb{R}^{n}$, and $w \in V$, then $w = c_{1}v_{1} + \dots + c_{k}v_{k}$ where $c_{i}$ is uniquely defined as $c_{i} = w \cdot \frac{v_{i}}{v_{i}\cdot v_{i}}$

$proj_{v}(w) = w \cdot \hat{v} = \frac{w \cdot v}{\sqrt{v \cdot v}} = \frac{w \cdot v}{v \cdot v} v$ 
(Essentially, we know that orthogonal basis are linearly independent basis. So there has to be a unique linear combination of vectors for $Ax = w$. The catch here is that it just so happens that we can easily find the combination weight for a particular basis vector by just taking **projection** of the vector with that basis vector)

The way you project a vector onto another vector is you take the vector's dot product with a certain vector's direction vector.
So $proj_{u}(w) = w \cdot \hat{u}$ where $\hat{u} = \frac{u}{||u||} = \frac{u}{\sqrt{u \cdot u}}$

Note, the confusion begins when you use different notational definitions of $\hat{u}$
For our coursework, for some reason, Linear Algebra notations sometimes use $\hat{w} = proj_{u}(w)$
at this point, they do not consider the hat to be a direction vector but a projection along a direction. Weird but I don't know how to help it out. After all, notations can be a little arbitrary.
Refer to the image above for the idea.

NOTE HOWEVER, I would continue using my OWN notation of hat being an indicative of a direction vector (a vector with magnitude of 1).


Due to the Pythagorean theorem, the orthogonal distance of a point on a line happens to be the shortest distance from the line. So when referring to the distance of a point from a line, you often mean the shortest, or the orthogonal distance.

Note, this distance corresponds to the vector $w - proj_{u}(w)$, often referred in our course as the vector $z$.
Thus, the orthogonal distance is $||z||$.

#### Example 
- Find the orthogonal projection of $u = \begin{bmatrix}3\\4\end{bmatrix}$ onto $L:y=-2x$ and the distance $u$ to $L$.

The first thing you need is a direction vector for the line. For this, take the difference between any two points on the line. $v = \begin{bmatrix}1\\-2\end{bmatrix}$ is one point vector that satisfies the line (plug in $x=1$ in the equation)
another solution is the zero vector $\begin{bmatrix}0 \\ 0\end{bmatrix}$
Hence, a direction vector here can be $\hat{v} = \frac{v}{\sqrt{v \cdot v}}$.

Then, the projection of $u$ on the line would be $u \cdot \hat{v}$. Hence, the distance would be $||u - u \cdot \hat{v}||$
Since $u - u \cdot \hat{v}$ would be the vector orthogonal to the line, pointing to the point $u$.
## Orthogonal Complement
#def 
The **orthogonal complement** of a nonempty subset $S$ of $\mathbb{R}^{n}$ is 
$S^{\perp} = \set{x \in \mathbb{R}^{n} : x \perp v \text{ for any } V \in S}$

- $S^\perp$ is a subspace of $\mathbb{R}^{n}$ 
- $S^{\perp} = (SpanS)^{\perp}$
- $(S^{\perp})^{\perp} = Span S$ (except if $S$ is not a subspace)

Essentially, for a set of vectors defined in space $\mathbb{R}^{n}$, the orthogonal complement of the set, same as the orthogonal complement of the span of the set of vectors would be the set of vectors perpendicular to all the vectors of in our given set, belonging to the space $\mathbb{R}^{n}$

![[Maths/Intro to Linear Algebra/attachments/Drawing 24-11-21-03-18-35]]

Essentially, for a set of vectors $S = \set{v_{1}, \dots, v_{n}}$, defined on space $\mathbb{R}^{n}$, the orthogonal complement would be a set of vectors that are all perpendicular to $v_{1}, \dots, v_{n}$, all still belonging to space $\mathbb{R}^{n}$

Essentially, we know then that for these vectors, let's say one of the vectors being $u$, $u \cdot v_{1} = u \cdot v_{2} \dots = u \cdot v_{n} = 0$ since these vectors are orthogonal (there is no nonzero component of $u$ in the direction of either of the vectors in $S$)

$u$ then can be any vector that satisfies $u \cdot v_{i} = 0$ for all $v_{i} \in S \implies u(v_{i})^{T} = 0$
(remember? [[Maths/Intro to Linear Algebra/Lec 21. Orthogonality & Least Squares#Inner Product, length, orthogonality & orthogonal set|Difference Between multiplication and dot product]] ($uv$ vs $u \cdot v$ is essentially that $uv$ is a matrix multiplication which for one dimensional vectors, is not defined. $v^{T}u = v \cdot u$))
So $u$ is the solution space of vectors for which every $v_{i}^{T}$ when weighted by $u$ gives $0$

Essentially, $v_{1}^{T}u + v_{2}^{T}u + \dots v_{n}^{T}u = 0 \implies A^{T}u=0$ where $A^{T}$ is the transpose of the matrix made by $v_{1}, v_{2}, \dots v_{n}$

Hence, For any subspace $S$,
$S^\perp$, or the orthogonal complement of $S$ is the $Null(A^{T})$ for $A$ being the augmented matrix of all vectors in orthogonal set $S$.

To know really why $S^{T}$ (The orthogonal complement) of The vector space of Columns of a matrix $A$ (Column Space of A) is $Null(A^{T})$:
![[Maths/Intro to Linear Algebra/attachments/Orthogonal Complement and Null of Transpose.jpg|700]]

![[Maths/Intro to Linear Algebra/attachments/orthogonal Complement .jpg|700]]
#### Examples
- $\set{0_{n \times 1}}^{\perp}= \mathbb{R}^{n}$
Taking a orthogonal compliment on both sides:
$(\mathbb{R}^{n})^{\perp} = \set{0_{n \times 1}}$


- Let $S = \set{\begin{bmatrix}1\\1\\0\end{bmatrix}, \begin{bmatrix}1\\-1\\2\end{bmatrix}}$, $W = SpanS$, and $u = \begin{bmatrix}1\\1\\3\end{bmatrix}$
a) Find a basis for $S^\perp$, the orthogonal complement of $S$.
Let $A = \begin{bmatrix}v_{1} & v_{2}\end{bmatrix} \implies A^{T} = \begin{bmatrix}v_{1}^{T} \\ v_{2}^{T}\end{bmatrix}$

$S^{\perp} = \set{x \in \mathbb{R}^{3}: x \perp v_{1}, x \perp v_{2}} = \set{x \in \mathbb{R}^{3} : \cases{v_{1}x = v_{1}^{T}x = 0\\ v_{2}x = v_{2}^{T}x = 0}} = \set{x \in \mathbb{R}^{3} : A^{T}x = 0}$

$S^{\perp} = \set{x \in \mathbb{R}^{3}:A^{T}x = 0} = Null(A^{T})$

Basis of $Null(A^{T}) = \set{\begin{bmatrix}-1\\1\\1\end{bmatrix}}$
b) Find a basis for $W^\perp$, the orthogonal complement of $W$

$W^{\perp} = Span(S)^{\perp} = S^{\perp} = Null(A^{T}) = \set{\begin{bmatrix}-1\\1\\1\end{bmatrix}}$
$(Span \set{v_{1}, v_{2}})^{\perp} = Col(A)^{\perp} = Row(A^{T})^{\perp}$

#theorem 
- For any $m \times n$ matrix $A$, $Col(A)^{\perp} = Row(A^{T})^{\perp}= Null(A^{T})$
- For any subspace $W$ of $R^{m}$, $dim(W) + dim(W)^{T} = m$
(Makes sense, in an $m$ dimensional space, either you or vectors orthogonal vectors would span any given part of a space)

## Orthogonal Decomposition 

#theorem 
If $\set{v_{1}, \dots, v_{k}}$ is an orthogonal basis for a subspace $V$ in $\mathbb{R}^{n}$ and $w \in V$, then $w = c_{1}v_{1} + \dots + c_{k}v_{k}$ where $c_{i} = \frac{w \cdot v_{i}}{v_{i}\cdot v_{i}} = w \cdot \hat{c_{i}}$

### The Orthogonal Decomposition Theorem
#theorem 
Let $V$ be a subspace of $\mathbb{R}^{n}$, then any $w \in \mathbb{R}^{n}$ has a unique decomposition $w = \hat{w} + z$, where $\hat{w} \in V$ and $z \in V^\perp$ and $\hat{w}$ represents the $proj_{v}(w)$ and NOT the direction vector.

- If $S$ is an orthogonal set, then $proj_{v}(w) = w \cdot \hat{v_{1}}v_{1} + \dots + w \cdot \hat{v_{k}} v_{k}$ and $z = w - proj_{v}(w)$ ($proj_v(w)$ is just sum of the vectors projected on top of different orthogonal vectors, scaled by the orthogonal vectors themselves) — Essentially, by scaling everything by the vector itself, if we create a space out of all the orthogonal vectors, $proj_v(w)$ then is the projection of $w$ on the space we form

**why dotted with the vector itself instead of the direction vector?**
- If $S$ is orthonormal, the vectors themselves are $\hat{v_{i}}$, else, to find the projection, you need to first find the direction unit vector for each vector in set $S = \set{v_{1}, \dots v_{k}}$ by $\hat{v_{i}} = \frac{v_{i}}{v_{i}\cdot v_{i}}$

#### Example 
Let $S = \set{\begin{bmatrix}1\\1\\0\end{bmatrix}, \begin{bmatrix}1\\-1\\2\end{bmatrix}} = \set{v_{1} , v_{2}}$, $W = SpanS$ and $u = \begin{bmatrix}1\\1\\3\end{bmatrix}$
c) Find the orthogonal projection onto $W$.

To find the orthogonal projection onto $W$, we just need $(u \cdot \hat{v_{1}}) v_{1} + (u \cdot \hat{v_{2}}) v_{2} = v_{1} + v_{2} = \begin{bmatrix}2\\0\\2\end{bmatrix}$

d) Find the orthogonal decomposition of $u$ with respect to $W$
$u = \hat{u} + z$, where $\hat{u} = \begin{bmatrix}2\\0\\2\end{bmatrix} \in W$ and $z = u - \hat{u} = \begin{bmatrix}-1\\1\\1\end{bmatrix} \in W^\perp$

#def 
The **distance ($||z||$)**  from $w \in \mathbb{R}^{n}$ to a subspace $V$ of $\mathbb{R}^{n}$ is $||w - proj_{V}w||$
- If $w \in V \implies ||w - proj_{V}w||=0 \implies proj_{V}w=w$
- If $w \notin V \implies ||w - proj_{V}w|| < ||w-v||$

![[Maths/Intro to Linear Algebra/attachments/Drawing 24-11-20-11-37-12]]

#theorem The Best Approximation Theorem 
Let $V$ be a subspace of $\mathbb{R}^{n}$ then for any $w \in \mathbb{R}^n$, $\hat{w} = proj_{V}w$ is the closest point (or the best approximation) in $V$ to $w$.