## Special Matrices
#def A matrix is called a **square matrix** if the n(rows)=n(columns)
#def The **diagonal entries** of a matrix A are the $(i,i)$ entries.
		$$\begin{bmatrix}
a_{11} & a_{12} & a_{13} & \dots \\ a_{21} & a_{22} & a_{23}  \\ a_{31} & a_{32} & a_{33} \\ \vdots & & &\ddots
\end{bmatrix}$$
#def The **diagonal matrix** is a square matrix where $a_{ij}=0,\quad \forall \enspace i\neq j$
		$$\begin{bmatrix}1&0&0\\0&2&0\\0&0&-10\end{bmatrix}$$
#def The **Transpose** of an $m \times n$ matrix A is an $n \times m$ matrix $A^T$, obtained by switching rows of A with it's columns
- ith column of A $\iff$ ith row of $A^T$
- jth row of A $\iff$ jth column of $A^T$
- $A_{ij}=A^T_{ji}$
- Example:
	- $A = \begin{bmatrix}1&2&3\\4&5&6\end{bmatrix}$
	- $A^{T}=\begin{bmatrix}1&4\\2&5\\3&6\end{bmatrix}$
	- $(A^{T})^T = \begin{bmatrix}1&2&3\\4&5&6\end{bmatrix}=A$

#def A square matrix A is called **symmetrical** if $A^T=A$
#def A matrix is **upper/lower triangular** matrix if all entries are below/above the diagonal are zeroes
		![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-27-04-04-36|800]]

---
# Matrix Operations

### Matrix Addition 
Matrix Addition, like vector addition is just adding the corresponding elements of a matrix.

### Matrix Scaling
Multiplying by scalar means scaling each entry by the scalar, just like a vector.

### Matrix Multiplication 

#def Let A be an $m \times n$ matrix and B be an $n \times p$ matrix

Then the **matrix product** AB is an $m \times p$ matrix whose $jth$ column is $Ab_{cj}$
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-27-04-11-20|1000]]

Essentially, A matrix-matrix product is whose columns are the matrix vector products for each column vector of the other matrix.

## Row-Column rule for the matrix product 
(here, instead of calculating )
This happens to be equivalent to the fact that for 
$A = \begin{bmatrix}a_{r_1}\\\vdots\\ a_{r_m}\end{bmatrix}$ and $B = \begin{bmatrix} b_{c_{1}}& \dots & b_{c_p}\end{bmatrix}$

then the $ab_{ij}^{th}$ entry of the product $AB$ is the product $a_{r_{i}}\cdot b_{c_{j}}$ = ith row of a * jth column of b 

- $col_j(AB)=A\space col_j(B)$
- $row_i(AB)=row_i(A)\enspace B$

---
#theorem Properties of the matrix product 
- $\alpha (AC)= (\alpha A)C=A(\alpha C)$, $\alpha$ is any scalar     (Commutative).
- $A(CP)=(AC)P=ACP$     (Associative)
- $(A+B)C =AC + BC$     (Distributive)
- $I_kA_{k \times m}=A_{k \times m}I_m=A_{k \times m}$, $I$ is the identity matrix 
- $AB \neq BA \enspace \forall A,B \in \mathbb{R}^n$ (except a few special cases) 
- $AB=0$ does NOT imply $A=0$ or $B=0$
	- therefore, $A(B-C)=0 \implies AB=AC$ does NOT imply $B=C$
	- IF A is invertible, then yes,
		- $AB=0 \implies A^{-1}AB=A^{-1}0 \implies IB=0 \implies B=0$

### The **inverse** of a matrix
#def An $n \times n$ matrix A is **invertible** if there exists an $n \times n$ matrix B such that $AB = I = BA$. Otherwise, A is **singular**.
(singular = non-invertible)

B is called an (unique) inverse of A denoted by $A^{-1}$. (A is also the inverse of B)
- If A & B are squares and $AB = I = BA$, then $B = A^{-1}$ and $A = B^{-1}$
	- $[a]^{-1}= \frac{1}{[a]}$
		- if $a=0$, $[a]$ is not invertible since $\frac{1}{[0]}$ is undefined! 
	- $A^{-1}=\frac{adj(A)}{|A|}$
		- $$\begin{bmatrix}a&b\\c&d\end{bmatrix}^{-1}= \frac{1}{ad-bc}\begin{bmatrix}d&-b\\-c&a\end{bmatrix}$$
		- $$\begin{bmatrix}1&2\\3&4\end{bmatrix}^{-1}= \frac{1}{-2} \begin{bmatrix}4&-2\\-3&1\end{bmatrix}$$
		- if $|A|=0$ then the $A$ is singular!
		
	- Given $A_{n \times n}$, $\rightarrow$ $A^{-1}=?$
		- $AB_{n \times n}=A[b_{1} \dots b_{n}]=[Ab_{1} \dots Ab_{n}]$
		- so if A is invertible, $AB = I = [e_{1} \dots e_n]$
		- $Ab_j=e_j$ for any $j=1,\dots,n$
	- If $Ax=e_j$ is consistent with solition $x=b_j$ for any $j=1,\dots,n$ then A is invertible and $AB=I$, $B=[b_1 \dots b_n]$ {B is unique}

## Why care about Inverses?

$Ax=b$
$A^{-1}Ax=A^{-1}b$
$Ix=x=A^{-1}b$
Hence, we can find solutions to matrix product equations.

And since the inverse is a very unique matrix, $x$ is also unique.

---
# A deeper Understanding of Inverses — Functional Mathematics
## What makes a matrix Invertible?
A matrix corresponds to a transformation function. Like any mathematical function, an inverse only exists if the function is Bijective!
- You can only map back to an element in the domain if you have only one element domain mapping to a certain image in the Co-Domain (one-to-one)
- To be able to map all values from the Co-Domain back to the Domain, you need to have a mapping to all values in the Co-Domain in the first place. I.e. the Range must equal the Co-Domain. (onto)
If a function satisfies both of these, it is invertible.

Extending this idea to Matrices, a matrix is invertible if it's corresponding transformation maps all of Space $\mathbb{R}^n$ to $\mathbb{R}^n$. If it maps it to a dimension lower than that, we would not have preimages defined for all values in the Co-Domain ($\mathbb{R}^n$) since the function in not onto.

Another way to look at it is, if a function maps several inputs to one collapsed value, it's not one-to-one.

In matrix notation, this corresponds to the system $Ax=b$ not be consistent for certain values $b$ in the co-domain (i.e. it has the $\begin{bmatrix}0&0&|&b\end{bmatrix}$ row) 
&/Or
$Ax=b$ having multiple values $x$ in the Co-Domain mapping to the same value $b$ in the Co-Domain (i.e. it has free variables $\iff$ non-pivot columns)

So for a Matrix to be invertible, it must have all columns as pivot columns (hence no free variables) which automatically also means it must not have a $\begin{bmatrix}0&0&|&b\end{bmatrix}$ row.

Hence, for a matrix to be invertible, it must have a RREF equal to the Identity matrix of same dimensions
