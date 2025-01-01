## Matrix Algebra
$A_{m \times n}\enspace, B_{m \times n}\enspace, C_{n \times p}\enspace \quad m \neq n \neq p$

$A + B$ is well defined since they have the same Dimensions.
$AB$ is not defined since for the product, n(Columns of A) {m} must equal n(Rows of B) {n}

$A+C$ is undefined since their dimensions are the same.
$AC$ is well defined since n(Columns of A) {n} is equal to n(Rows of C) {n}

---
$AC = \begin{bmatrix}A_{r_{1}} \\ \vdots \\ A_{r_{n}}\end{bmatrix}\, \begin{bmatrix}C_{c_{1}}& \dots &C_{c_n}\end{bmatrix}$
$= \begin{bmatrix}A_{r_{1}}C_{c_{1}} & \dots & A_{r_{1}}C_{c_{n}} \\ \vdots \\ A_{r_{n}}C_{c_{n}} & \dots & A_{r_{n}}C_{c_{n}}\end{bmatrix}$

Basically, the $AC_{ij} = \text{ith row of A * jth column of C}$  (same number of rows down and same number of columns right)

---
## Solving a Matrix equation
$Ax=b$ is solved by finding an equivalent RREF of $[A|b]$
the corresponding rows of the RREF(A) is weighed by elements of $x$

Say you solve $\begin{bmatrix}1 & -1 & -2 & 0 \\ 0 & 0 & 0 & 1\end{bmatrix}x = \begin{bmatrix}6\\-3\end{bmatrix}$
So here, 
$1x_1-1x_2-2x_3+0x_4=6$
$0x_1+0x_2+0x_3+1x_4=-3$

Hence, we have free variables!

We can also write this as a parametric vector form.
we know the solution $$x = \begin{bmatrix}x_1\\x_2\\x_3\\x_4\end{bmatrix}=\begin{bmatrix}6+x_2+2x_3\\x_2\\x_3\\-4\end{bmatrix}=\begin{bmatrix}6\\0\\0\\3\end{bmatrix}+x_2\begin{bmatrix}1\\1\\0\\0\end{bmatrix}+x_3\begin{bmatrix}2\\0\\1\\0\end{bmatrix}$$

---

## Consistency
If $[RREF(A)|b]$ is consistent, then $[A|b]$ is consistent.

So we solve a matrix system to it's RREF.

### Consistent
- if all columns have a pivot position, then we have no free variables
- system is linearly independent
- unique solution

- if there are free variables (always true if n(columns)>n(rows))
	- infinite solutions


### Inconsistent
- $[0 \space 0 \space 0 | b]$ is there

---

>Every linear transformation is a Matrix transformation and every Matrix transformation is a linear transformaton.

---
## Linear Transformation 

To find the standard matrix, 
- See what vectors correspond to the transformed versions of elementary columns $e_1$, $e_2$, $e_3$
- These are columns of the standard matrix

$T(c_1v_1+c_2v_2)=c_1T(v_1)+c_2T(v_2)$

Since we can write any vector as a linear combination of $e_1$, $e_2$, $e_3$, we can now solve for the it's image too.

With the standard Matrix, we have the transformation Represented as a Matrix equation $Ax=b$ which we can solve to find images (b) and preimages (x) given the other.


- If T is one-to-one that means every element $b$ in equation has a unique solution for equation $Ax=b$ where $A$ is the standard matrix associated with the Linear Transformation.
	- A is linearly independent
	- pivot position in each column
	- $Ax=0$ has only the trivial solution (nice easy way to test consistency)
- T maps $\mathbb{R}^{n}$ to $\mathbb{R}^m$ for all $m$ columns that have a pivot position (there is a degree of freedom in that)
- ![[Maths/Intro to Linear Algebra/attachments/Linear Algebra Review 1.jpg]]
- 

---

## Matrix inversion
- FOR SQUARE MATRICES!
- A matrix is invertible if there exists a matrix that undoes everything that it does.
- If we solve Solve the RREF(A) for Augmented system $[A|I_n]$ by Gauss-Jordan
	- we get $[RREF(A)|B]$
	- $BA = RREF(A)$ since $B$ is a result of same elementary operations on $I_n$ as those on $A$ to get $RREF(A)$
		- i.e. An elementary Matrix when multiplied has the same result as performing the elementary matrix
		- B is a product of elementary matrices (and is itself an elementary matrix too!)
			- If RREF(A) is $I_n$:
				- $BA=I_{n}\implies$ B is the inverse matrix of A
			- To just realise if A is invertible or not, we know that having a pivot position in each column is enough to have a way to convert to $I_n$ means if **REF(A) having n pivot positions (equal as num of columns) is enough to prove invertibility**
			- 

- We can also solve $Ax=0$. 
	- If the Matrix is sparse, we can try to simplify the system as well.
	- If x only has a trivial solution that means $Ax=b$ only has a unique solution
		- set of columns of $A$ would be linearly independent
			- It would be invertible (since there would be n pivot columns)



				- Since a set has no order, $\begin{bmatrix}a_1&a_2\end{bmatrix}$ being invertible means $\begin{bmatrix}a_2&a_1\end{bmatrix}$ is invertible
				- $\implies \begin{bmatrix}1&2&3\\0&4&5\\0&0&6\end{bmatrix}$ being invertible means $\begin{bmatrix}2&1&3\\4&0&5\\0&0&6\end{bmatrix}$ is invertible
					- Hence, to test invertablity, you can swap columns too
- 



