![[Maths/Intro to Linear Algebra/Lec 6. Linear Transformations#Rank and Nullity|Rank And Nullity - My Version]]


Using our knowledge from [[Maths/Intro to Linear Algebra/Lec 13-15. Vector Space & Subspace & Span|Lec 13-15. Vector Space & Subspace & Span]], 
$$[\vec{x}]_{B} \xleftrightarrow{\vec{x} = [\vec{b_{1}}\dots \vec{b_{n}}][\vec{x}]_{B}} x \xleftrightarrow{\vec{x} = [\vec{c_{1}}\dots \vec{c_{n}}][\vec{x}]_{C}} [\vec{x}]_{C}$$
Hence, we know how to relate the coordinate vectors from any space to those of the Standard Basis Space.
Hence, to compare two different vector spaces and their coordinate vectors,
$$[\vec{b_{1}}\dots \vec{b_{n}}][\vec{x}]_{B} = [\vec{c_{1}}\dots \vec{c_{n}}][\vec{x}]_{C}$$
#theorem Let $B = \set{\vec{b_{1}}, \dots , \vec{b_{n}}}$ & $C = \set{\vec{c_{1}}, \dots , \vec{c_{n}}}$ be bases of a vector space V. Then there is a unique invertible matrix $n \times n$ matrix $P_{B \to C} = [[\vec{b_{1}}]_{C} \dots [\vec{b_{n}}]_{C}]$ such that $[\vec{x}]_{C}= P_{B \to C}[\vec{x}]_B$


In other words, for two different bases spanning the same space, there must exist a matrix to transform between the two spaces such that the coordinate vectors for a Standard Point in 1 space can be converted to the coordinate vectors for the same standard point in the different space simply by multiplying the matrix.

### Finding $P_{B \to C}$
#### Example 
Let $B = \set{b_{1}, b_{2}}$ and $C = \set{c_{1}, c_{2}}$
 - $P_{B \to C} = \begin{bmatrix}[\vec{b_{1}}]_{C} & [\vec{b_{2}}]_{C}\end{bmatrix}$
	 - $\vec{b_{1}} = P_{C}[\vec{b_{1}}]_{C}$
	 - $\vec{b_{2}} = P_{C}[\vec{b_{2}}]_{C}$
	 - solving for $[\vec{b_1}]_C$ & $[\vec{b_2}]_C$ here, $$P_{B \to C} = \begin{bmatrix}[\vec{b_{1}}]_{C} & [\vec{b_{2}}]_{C}\end{bmatrix} = \begin{bmatrix}P_{C}^{-1} \vec{b_{1}} & P_{C}^{-1} \vec{b_{2}}\end{bmatrix} = P_{C}^{-1} \begin{bmatrix}\vec{b_{1}} & \vec{b_{2}}\end{bmatrix} = P_{C}^{-1}P_{B}$$
		 - What this is doing is it first transforms $[x]_{B}$ to $x$ (since $\vec{x} = [\vec{b_{1}}\dots \vec{b_{n}}][\vec{x}]_{B}$) and then $x$ to $[x]_C$ (since $\vec{x} = [\vec{c_{1}}\dots \vec{c_{n}}][\vec{x}]_{C}$)

Essentially, to transform a coordinate vector in $B$ space to that of $C$ space. I.e. (And this is important!)
You take a point $P$ in your standard space (space spanned by the standard matrix), If you know the coordinates of that point in B space (i.e. you know how to get to point P linear combination of basis vectors of B) you can know its coordinates in C space (i.e. as a linear combination of basis vectors of C)

By first finding P as linear combination of standard basis $\vec{x}_{std} = P_{B}[x]_{B}$
and then since $\vec{x}_{std} = P_{C}[x]_C$, $[x]_{C} = P_{C}^{-1} \vec{x}_{std}$
Hence, $[x]_{C} = P_{C}^{-1}P_{B} [x]_B$

Ahaa! That is how you change between different vector spaces.


---
#theorem Any set $S = \set{v_{1}, \dots, v_{m}}$ in $\mathbb{R}^{n}$ is linearly dependent if $m>n$
 - Any linearly independent subset of $\mathbb{R}^{n}$ with exactly $n$ vectors is a basis for $\mathbb{R}^{n}$


---
# Few definitions 
#def The number of vectors in the basis of a vector space is its **dimensions**.
	#def A vector space $V$ is finite-dimensional if it's spanned by a finite set. Otherwise, V is infinite-dimensional 
		The dimension of a nonzero finite dimensional V, denoted by $dim(V)$ is the number of vectors in the basis of the vector space
	The dimensions of the zero vector space $\set{0}$ is defined to be $zero$.

Following naturally from this,
#theorem **(Basis Theorem)**
If there is a set of $n$ linearly independent vectors, it must be a basis of an $n-dimensional$ space. ($1 \leq n \leq \infty$)

A subspace of $\mathbb{R}^{n}$ must be $\mathbb{R}^{m}$ where $m \leq n$ and $\mathbb{R}^{m}$ must have $m$ basis vectors. I.e a subspace will always be a lower (or equal) dimension than a Space. (As long as $n$ is finite!)

# Rank and Nullity (Again)
#def 
	The **rank** of an $m \times n$ matrix A is $dim(Col(A))$, denoted by $rank(A)$
	The **nullity** of an $m \times n$ matrix A is $dim(Nul(A))$, denoted by $nullity(A)$

Recall:
#theorem 

The pivot columns of $A_{m \times n}$ form the basis of $Col(A)$ (other vectors are redundant)
- $rank(A) = \# \text{ of pivot columns}$

The non-pivot columns for $A_{m \times n}$ are the number of free variables we have that do not effect the Matrix vector product. Hence, for equation $Ax=0$, there must be $n$ degrees of freedoms in $x$ for each free variable.
Therefore, dimensions of the null space is equal to the number of free variables in a matrix (i.e. the number of non-pivot columns of A)
- $nullity(A) = \# \text{ of non-pivot columns}$ 

#theorem The Rank Theorem
But since $\text{\# of pivot columns}+\text{\# of non-pivot columns} = \text{total columns of A}$,
- $rank(A)+nullity(A)=nCol(A)$

Note, this is different from Dimensions of Columns Space of A. That IS the rank! The point is the dimensions can be different than the actual number of columns of A.

$dim(Col(A))=dim(Row(A))=rank(A)$
(any non pivot column would correspond to either the difference in the size of columns and size of rows of A or a $0$ row of A in the RREF of A)

---
#theorem The nonzero $rows^T$ of the REF/RREF of A form a basis for Row(A)
$dim(Row(A))=\text{\# non zero rows of the REF/RREF of A = \# pivot positions of A}=rank(A)$
i.e.
$dim(Col(A^{T})) = rank(A^{T})$

Essentially, rank is the number of dimensions that a matrix spans (The number of dimensions for which the points in space $\mathbb{R}^{n}$ can be a linear combination of the *rows* of A)

#### Example

- $A = \begin{bmatrix}1&0&0&3&1\\0&1&0&1&2\\0&0&1&2&3\\0&0&0&0&0\end{bmatrix}$

The number of pivot positions $= 3$
hence, the $rank(A)=dims(Col(A^{T})) = dim(Row(A))=3$
$dim(Null(A)) = nullity(A) = \text{\# of columns of } A^{T} = 5-3=2$

- $A=\begin{bmatrix}1&1&1\\1&1&1\\1&1&1\\1&1&1\\1&1&1\\\end{bmatrix}_{5 \times 3}$
a) determine the dimension of Null(A), Col(A) & Row(A).
$RREF(A) = \begin{bmatrix}1&1&1\\0&0&0\\0&0&0\\0&0&0\\0&0&0\\\end{bmatrix}$    
$dim(Col(A)) = dim(Row(A)) = rank(A)=1$

# Table from Lec 16 notes

| Subspace              | of             | dim        | basis                                                                                  |
| --------------------- | -------------- | ---------- | -------------------------------------------------------------------------------------- |
| $Col(A_{m \times n})$ | $\mathbb{R}^m$ | rank(A)    | {pivot columns of A}                                                                   |
| $Nul(A_{m \times n})$ | $\mathbb{R}^n$ | nullity(A) | {vectors in the parametric<br>vector form of general solution<br>to $Ax=0$}            |
| $Row(A_{m \times n})$ | $\mathbb{R}^n$ | rank(A)    | {nonzero $rows^T$ of the REF/RREF of A}<br> (transpose only to treat as column vector) |


---
- Determine the dimension of the vector space $V = \set{\begin{bmatrix}a+2b+3d\\c+2d\end{bmatrix}:a,b,c,d \space \in \space \mathbb{R}}$
$V = \set{a \begin{bmatrix}1\\0\end{bmatrix}+b \begin{bmatrix}2\\0\end{bmatrix}+c \begin{bmatrix}0\\1\end{bmatrix}+d \begin{bmatrix}3\\2\end{bmatrix}:a,b,c,d \space \in \space \mathbb{R}} = Span \set{ \begin{bmatrix}1\\0\end{bmatrix}+\begin{bmatrix}2\\0\end{bmatrix}+ \begin{bmatrix}0\\1\end{bmatrix}+ \begin{bmatrix}3\\2\end{bmatrix}}$

We know that the span of these set of vectors is equivalent to the column space of the augmented matrix/special matrix whose columns are those vectors.

$V = Col(A), \text{ where }A=\begin{bmatrix}1&2&0&3\\0&0&1&2\end{bmatrix}$
$dim(V)=dim(Col(A))=rank(A)=2$ (since there are only 2 pivot columns in $REF(A)$)

- Determine the dimension of vector space $V = \set{x = \begin{bmatrix}x_{1}\\x_{2}\\x_{3}\\x_{4}\end{bmatrix} \in \mathbb{R}^{4} : \begin{matrix}x_{1} + 2x_{2} + 3x_{4} = 0 \\ x_{3} + 2x_{4} = 0\end{matrix}}$
What that means is $V$ is the solution set of the equation.

$\begin{bmatrix}1&2&0&3\\0&0&1&2\end{bmatrix}x=0$

Hence, the solution space has the dimensions equal to the Span of the columns of the Matrix's column vectors.
you could have said $x_{1} = - 2x_{2} - 3x_{4}$ and $x_{3} = -2x_{4}$
$\implies x = \begin{bmatrix}x_{1}\\x_{2}\\x_{3}\\x_{4}\end{bmatrix} = \begin{bmatrix}-2x_{2}-3x_{4}\\x_{2}\\-2x_{4}\\x_{4}\end{bmatrix} = x_{2} \begin{bmatrix}-2\\1\\0\\0\end{bmatrix}+ x_{4} \begin{bmatrix}-3\\0\\-2\\1\end{bmatrix}$

And then you find the span of these sets of vectors weighted by free variables.

# Conclusion
- Any **non-pivot column** corresponds to a **free variable** in the solution to Ax=0A \mathbf{x} = 0Ax=0 (in the context of the null space). Non-pivot columns indicate **dependencies** in the columns of AAA and do not contribute to the rank.
    
- If AAA has more columns than rows (a **wide** matrix), there will be more non-pivot columns than non-zero rows in the row echelon form. This difference between the number of columns and rows indicates how many columns lack pivots and thus do not contribute to Col(A)\text{Col}(A)Col(A).
    
- Similarly, if there are zero rows in the row echelon form of AAA, these rows also indicate dependencies and do not contribute to Row(A)\text{Row}(A)Row(A).
    

In summary, the rank is determined by the number of pivot positions in AAA, and the remaining columns (if any) correspond to dependencies.