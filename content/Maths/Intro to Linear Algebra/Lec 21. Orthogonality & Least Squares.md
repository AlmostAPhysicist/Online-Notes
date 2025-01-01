While solving a system $Ax=b$, sometimes we get inconsistencies, that means there is no solution.

But even for inconsistencies, there are few golden zones where we approach the closest to what may have been the true solution.

Essentially, we can optimize our way to **minimize** the error $Ax-b$, to be as small as possible.

## Inner Product, length, orthogonality & orthogonal set 

Multiplying vectors... what does it mean?

$Ax$ is a matrix vector multiplication. Which we know what it means... it is the sum of different column vectors in $A$, scaled by elements in $x$ as weights. ^56f46c

But for the one dimensional matrices, this product is undefined. Hence, we define something on our own...

#def 
Let $u = \begin{bmatrix}u_1 \\ \vdots \\ u_n\end{bmatrix}$ and $v = \begin{bmatrix}v_1 \\ \vdots \\ v_n\end{bmatrix}$ be two vectors in $\mathbb{R}^{n}$.

The **inner product** (or **dot product**) of $u$ & $v$ denoted by $u \cdot v$ is given by $$u \cdot v = u^{T}v = \begin{bmatrix}u_1 & \dots & u_n\end{bmatrix} \begin{bmatrix}v_1 \\ \vdots \\ v_n\end{bmatrix} = u_{1}v_{1} + \dots + u_{n}v_{n}$$

Note, order here doesn't matter, $u \cdot v=v \cdot u$.
Essentially, the inner product is the product of all corresponding elements.
Also note, is is IMPORTANT TO WRITE THE DOT. Otherwise, it is just a matrix vector multiplication which would be undefined for 2 vectors in space $\mathbb{R}^{n}, n>1$.

#def 
The **norm (length)** of the vector $v = \begin{bmatrix}v_1 \\ \vdots \\ v_n\end{bmatrix} \in \mathbb{R}^n$ is denoted by **$||v||$**, is given by

$$||v||= \sqrt{v \cdot v} = \sqrt{v^{T}v} = \sqrt{v_{1}^{2} + \dots + v_{n}^{2}}$$


#def 
The **Distance** between vectors $u, v \in \mathbb{R}^{n}$ is defined as 
$$dist(u,v) = ||u-v|| = ||v-u||$$

---
#cheesy 
Why do we define the norm and distance in this way? Because of the Pythagorean Theorem! But the Pythagorean theorem doesn't work in all geometries. This definition is only true for Euclidean Space.

HOWEVER... once we started thinking about what does it mean to have a particular space, we defined the Euclidean Space to be the space in which distances are described by the above described function.

Circular Proofs?

Yes. 
In mathematics, it turns out, you have to choose your axioms. Different set of axioms may or may not be consistent. Different set of axioms may yield different results with different meanings. But sometimes, you need to start with ideas and premises that you consider to be true, in order to build things on top.

As long as the system is internally consistent with the assumed premise, the premise is valid. There may be multiple valid premises, though.
The idea of **valid premises** is not a weakness, but a strength, allowing for different kinds of mathematical worlds to be explored.

---
### Properties of the Inner Product 
Let $u,v,w \in \mathbb{R}^{n}$ and $c \in \mathbb{R}$, then
- $u \cdot v = v \cdot u$
- $u \cdot u = ||u||^{2} \geq 0$
- $u \cdot u \iff u = 0$
- $u \cdot (v+w) = u \cdot v + u \cdot w$
- $(v + w) \cdot u = v \cdot u + w \cdot u$
- $(cu) \cdot v = c(u \cdot v) = u\cdot(cv)$
- $||cu||=|c|\,||u||$
---
### Inner Product and Orthogonality 
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-11-15-04-27-55]]
We know if 2 vectors are orthogonal, then by Pythagorean theorem,
$||u||^{2}+ ||v^{2}|| = ||u-v||^{2}$ but we just learned, $||u-v||^{2} = (u-v)\cdot(u-v) = ||u||^{2} + ||v||^{2} - 2(u \cdot v)$

Hence, for both to be equal, $$u \cdot v = 0$$
That is hence the condition for orthogonality.

---
#def 
Let $u, v \in \mathbb{R}^{n}$, then $u$ and $v$ are orthogonal if $u \cdot v = 0$

Note, although you see that in 2 dimensions, this holds true for higher dimensions too, since the Pythagorean theorem, given you consider Euclidean geometry would have the same definition. The Pythagorean theorem in $\mathbb{R}^{n}$ is just what we defined for 2 dimensions — the sum squares of side lengths is the square of the hypotenuse.

A weird consequence, (may not be so weird for you) is that $u \cdot 0 = 0 \implies u \perp 0$

---
### Orthogonal & Orthonormal sets 
#def 
A **unit vector** is a vector $v$ of norm $1$, i.e., $||v||=1$.
If $u$ is a nonzero vector, then unit vector in the same direction as $u$ is $v = \frac{u}{||u||}$

(you know what a unit vector is… it is a direction vector that has a length 1)

What is what it means to **normalize** a vector… to divide it by its length.
$$u \xrightarrow{normalize} v \implies v = \frac{u}{||u||}, \quad ||v||=1$$

---
#def 
A set of vectors is an **orthogonal set** if each pair of distinct vectors in the set is orthogonal.
An **Orthonormal set** is an orthogonal set of **unit vectors**.

To convert an orthogonal set to an orthonormal set, you just normalize each vector in the orthogonal set.

---
#theorem Any orthogonal set $S$ of nonzero vectors is linearly independent. 
(it has to be! There is no way you can create an orthogonal vector by just scaling/linear combinations).

Hence, it is a basis for $Span(S)$.


#def 
An **orthogonal basis** for a subspace $W$ of $\mathbb{R}^n$ is a basis for $W$ that is also an orthogonal set.

An **orthogonal basis** for $W$ is an orthogonal basis with unit vectors.

### Vector representations in orthogonal bases 

#theorem If $\set{v_{1}, \dots v_{k}}$ is an orthogonal basis for a subspace $V \in \mathbb{R}^{n}$, and  
$w \in V$, then $w = c_{1}v_{1} + \dots c_{k}v_{k}$, where $c_{i}=\frac{w \cdot v_{i}}{v_{i} \cdot v_{i}}$

