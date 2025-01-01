#def A **transformation** or **funciton** or **mapping** T from $\mathbb{R}^n$ to $\mathbb{R}^m$ is rule that assigns each vector x in $\mathbb{R}^n$ a vector $T(x)$ in $\mathbb{R}^m$

![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-20-04-05-16|1000]]

The set of all images $T(x)$ is in range T

---
Let A be an $m\times n$ matrix. Fir any $x\in \mathbb{R}^n$, let $T(x)=Ax$, then T is called a **matrix transformation**. ^c92dd6

$$x\in \mathbb{R}^{n}\longrightarrow T(x) = A_{m\times n} x_{n\times 1} \in \mathbb{R}^m$$
$$T: \mathbb{R}^{n}\longrightarrow \mathbb{R}^m$$ where $m$ is the number of rows of A.

Here, all of the elements of $\mathbb{R}^n$ would be mapped to $\mathbb{R}^m$ but note how it's not necessary to have a condition other way around.

So not all elements in the co-domain have an image in the domain.

$$x\longrightarrow Ax = \begin{bmatrix}
a_1&\dots&a_n
\end{bmatrix}\, \begin{bmatrix}
x_1\\\vdots\\a_n
\end{bmatrix} = x_{1}a_{1} + \dots x_na_n$$
The range of T is the set of all linear combinations of columns of A which by definition means range of the is the [[Maths/Intro to Linear Algebra/Lec 4. Matrix-Vector Multiplication#^21b4b3|Span]] of A
$$Range(T) = Span\{\text{columns of A}\}= Span\set{a_1,\dots,a_n}$$
Where $T$ is a transformation for $x$ given by $Ax$

---
## Example 1
$A = \begin{bmatrix}1&2\\2&5\\-1&-2\end{bmatrix}$, $u=\begin{bmatrix}3\\1\end{bmatrix}$, $b=\begin{bmatrix}1\\3\\-1\end{bmatrix}$, $c=\begin{bmatrix}2\\3\\r\end{bmatrix}$ and define a transformation $T:\mathbb{R}^2\to \mathbb{R}^3$ by $T(x)=Ax$

- To find image of you, find $T(u)=A(u)$ which is just a matrix vector product
- To find $x\in \mathbb{R}^2$ whose image under $T$ is b, we need to solve for vector $x$ in $T(x)=b=Ax \implies$ solve $[A|b]$
- Since there is a unique solution for the Matrix equation, there is just 1 unique vector $x\in \mathbb{R}^2$ that maps to $b$
- To check if c is in the range of transformation T is to say whether c is a linear combination of columns of Matrix A $\implies$c is in the span{columns of A}
	- To check if it is a linear combination, we check if [A|c] is consistent, that is if RREF/REF sorts to [0 0 | b] form or not.
		- Setting up we get $[A|c] = \begin{bmatrix}1&2&2\\2&5&3\\-1&-2&r\end{bmatrix}$
		- $REF([A|c]) = \begin{bmatrix}1&2&2\\0&1&-1\\0&0&r+2\end{bmatrix}$

		hence, a vector $c=\begin{bmatrix}2\\3\\r\end{bmatrix}$ is within the range of T only if $r=-2$ else we would have an inconsistent $[A|c]$ which would mean there would be no solvable form of linear combination of columns of A to create c.

![[Maths/Intro to Linear Algebra/attachments/Linear Transformations.jpg]]
## Special Matrix Transformations 
Find images under T of $u=\begin{bmatrix}4\\0\end{bmatrix}$, $v=\begin{bmatrix}0\\2\end{bmatrix}$ and $v+u=\begin{bmatrix}4\\2\end{bmatrix}$


a) $A=\begin{bmatrix}1&0\\0&0\end{bmatrix}$ $\implies$ $Au=\begin{bmatrix}4\\0\end{bmatrix}$, $Av=\begin{bmatrix}0\\0\end{bmatrix}$, $A(u+v)=\begin{bmatrix}4\\0\end{bmatrix}$

![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-20-04-40-04|1000]]

So basically, everything in Space 1 squishes to only x-axis that is we lose all the information about y-axis (everything along that gets multiplied by a $\vec{0}$).

![[Maths/Intro to Linear Algebra/attachments/Linear Transformation Practice .jpg]]


You can have a Contraction (a), Scale (b,c), Rotation (d), Sheer (e) or a Combination of these (Example 3)!

---
Transformation $x \xrightarrow{T} Ax$
- If T is a **Matrix Transformation** given by $T(x)=Ax$ then it follows directly that $T(c\vec{u}+d\vec{v})=A(c\vec{u}+d\vec{v})=cA\vec{u}+dA\vec{v}$ 


A transformation is **linear** if 
$$T(cu+dv)=T(cu)+T(dv)=cT(u)+dT(v)$$
Hence, Every Matrix Transformation is A linear Transformation And Vectors That are Parallel remain parallel, vectors that are scalar multiples remain scalar multiples ^429a8d
---

Properties of Linear Transformations
T is a linear transformation:
- $T(\vec{0}) = T(0\cdot\vec{0})=0\cdot T(\vec{0})=0$
- For any $c,d \in \mathbb{R}$ and $u$ & $v$ in the domain of T
	- $T(cu+dv)=T(cu)+T(dv)=cT(u)+dT(v)$ 
		Note how this is literally the definition of a linear transformation... i.e. the Transformation has a distributive property and the Scalars can be taken out of the function as they are and then applied after the transformation.
	- $\implies T(c_{1}v_{1}+\dots+c_{n}v_{n}) = c_1T(v_1)+\dots+c_nT(v_n)$
		Which means a linear combination of $v_1,\dots,v_n$ with weights $c_1,\dots,c_n$ when Transformed is still a linear combination with weights $c_1,\dots,c_n$ with each corresponding vector now being a vector in the transformed space.


## Rank and Nullity
Rank is the number of independent variables in a System (Number of pivot positions in the RREF(A) for A being the augmented matrix of the vectors in the set)
- The rank represents the order of space that is spanned by the System!
- So if a system is rank 4 that means it has 4 independent vectors and hence spans $\mathbb{R}^4$

Nullity is the number of dependent variables.
This can be figured out by the number of non-pivot columns in the RREF(A). Simply, it is the (total columns) - (pivot columns) or also the (number of vectors) - (rank)