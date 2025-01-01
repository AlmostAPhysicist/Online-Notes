
### Elementary row operations:
- Adding 2 rows
- Multiplying rows by a scalar 
- Shifting rows up and down 

### Elementary Matrices
Say you solve a matrix
$$\begin{bmatrix}
1&2\\3&4
\end{bmatrix}$$
(suppose it has some augmented part $\begin{bmatrix}5\\6\end{bmatrix}$too)

So to solve this, we perform the following row operations to convert it to a row echelon (REF) or reduced row echelon form (RREF):
$R_{2}-3R_{1}\rightarrow new R_{2}$

Now think about it... these series of operations can be performed not just on $A$ but also any other matrix.

If we perform the operations on $I_3$, we get $B=\begin{bmatrix}1&0\\-3&0\end{bmatrix}$.

Now, realize how the matrix product $B \cdot A= \begin{bmatrix}1&2\\0&-2\end{bmatrix}$ which is the same as applying the row operations on the matrix itself.

>If we perform certain operations on a matrix, it is equivalent to multiplying the matrix with an Identity matrix on which you perform the same operations

#def An **elementary matrix** is a matrix obtained by performing elementary operations on an Identity matrix.

The key is, that multiplying an elementary matrix to a matrix is the same as applying the row operations on the matrix.

---
# Why does it matter?

For the matrix equation $Ax=b$, the way you solve for $x$ is you perform row operations on $A$ to get an identity matrix. Then, the weights of the columns of the matrix - $x_1,x_2\dots$ would correspond to whatever value you have for the augmented part of $[A|b]$.

Now... If you rather perform the operations on an Identity matrix to get an elementary matrix $E$, you can say $E \cdot A$ has the same effect as performing the operations on A and transforming it into an identity matrix.

Hence, $E \cdot A = I$.

But wait!
That means $E$ is the inverse matrix of $A$!

Ahaa!
Yes!

that means $$EAx=Eb=Ix=x$$
Hence, you can solve for $x$ by just performing the row operations on an identity matrix and multiplying that by vector $b$.


Again, it's the same thing but now you get an entire matrix that holds the same power as your operations so you can perform the operations on any random matrix/vector.

In essence, by performing the row operations you kinda undo the process of composing matrix $A$ itself, hence matrix $E$ that you get at the end undoes everything that A does which would make sense since it is the inverse matrix.

---
## Mathematical Formalization
An $n \times n$ matrix A is invertible $\iff$ rref(A) $=$ $I_n$
i.e. Any sequence of elementary row operations that reduces A to $I_n$.

But if that is true, the same sequence of elementary operations transforms $I_n$ to $A^{-1}$.

- $B[A|I]=[BA|B]=[rref(A)|B]$
- if $rref(A)=I$, then A is invertible and $A^{-1}=B$

### Matrix Inversion Algorithm
- Input : A square matrix
- Output  : The inverse Matrix of A, or "not invertible"
- Procedure:
	- Form the augmented matrix $[A|I_n]$ (just so any operation on A is performed on $I_n$ as well)
	- Run Gauss Jordan on $[A|I_n]$, obtain the $rref([A|I_n])=[R|B]$
	- Check $R$
		- if $R=I_{n} \implies$ A is invertible, $A^{-1}=B$
		- if $R \neq I_{n} \implies$ A is NOT invertible (there are no set of operations that reverses the effects of A)

#### Example
$$[A|I_{3}]=
\left[\begin{array}{ccc|ccc}
0 & 1 & 0 & 1 & 0 & 0\\
1 & 2 & 1 & 0 & 1 & 0\\
-2 & 0 & 0 & 0 & 0 & 1
\end{array}\right]$$
performing the following row operations:
$r_{1} \rightleftarrows r_2$
$r_{3}+2r_{1} \rightarrow r_3$
$r_{3}-4r_{2} \rightarrow r_3$
$\frac{1}{2}r_{3}\rightarrow r_3$
$r_{1}-r_{3} \rightarrow r_1$
$r_{1}-2r_{2} \rightarrow r_1$

and we get $$[rref(A)|B]=
\left[\begin{array}{ccc|ccc}
1 & 0 & 0 & 0 & 0 & \frac{-1}{2}\\
0 & 1 & 0 & 1 & 0 & 0\\
0 & 0 & 1 & -2 & 1 & \frac{1}{2}
\end{array}\right]$$
Now since $rref(A)=I_{3}\implies B=A^{-1}$.
(Note how this is not true for all matrices... $rref(A)$ might not always be $I$.)

#theorem Invertible Matrix Theorem 
--
Let A be an $n \times n$ matrix. Then the following statements are equivalent:
- A is invertible
- There is an $n \times n$ matrix C, such that $CA=I$
- There is an $n \times n$ matrix D, such that $AD=I$ 
	- Since inverses are unique, $A^{-1}A = AA^{-1}=I$, $C=D$
- $rref(A)=I$
- A has $n$ [[Maths/Intro to Linear Algebra/Lec 4. Matrix-Vector Multiplication#^5b5c39|pivot positions]]
	- Each column has a pivot position
		- since there are same number of rows and columns, each row has a pivot position
- The columns of A are linearly independent
	- If they are instead dependent, you wouldn't get $I$, your matrix would rather have an independent variable and hence you can't have $n$ pivot position
- $Ax=0$ has only the trivial solution
	- Meaning that you can not have  $[a_{1} \dots a_{n} | 0]$
		- none of the columns of $A$ are linear combinations of other columns
- Span{columns of A} = $\mathbb{R}^n$
	- an $n \times n$ matrix would span $\mathbb{R}^n$ given it's columns are linearly independent
- $Ax=b$ is consistent for any $b \in \mathbb{R}^n$ 
	- (i.e. each vector $b$ in $\mathbb{R}^n$ space can be mapped back... Hence, the Span{columns of A} must be $\mathbb{R}^n$)
- $T: x \rightarrow Ax$ is one-to-one (and onto?)
- $T: x \rightarrow Ax$ is maps $\mathbb{R}^n$ to $\mathbb{R}^n$
- $A^{T}$ is also invertible ($(A^T)^{-1}=(A^{-1})^T$)


#def A linear Transformation $T:\mathbb{R}^{n}\rightarrow \mathbb{R}^n$ is invertible if there exists a transformation $S:\mathbb{R}^{n}\rightarrow \mathbb{R}^n$ such that $S(T(x))=x$ & $T(S(x))=x$ fir any $x \in \mathbb{R}^n$. S is called the inverse of $T$, denoted by $T^{-1}$.

Again, since any linear transformation corresponds to a matrix transformation (multiplication of a vector by a matrix [[Maths/Intro to Linear Algebra/Lec 6. Linear Transformations|Lec 6. Linear Transformations - ref!]])
This is an identical definition as an inverse of a *matrix*. 

S would also be unique, like any inverse matrix.

---

#theorem Let $T:\mathbb{R}^{n}\rightarrow \mathbb{R}^n$ be a linear transformation and $A$ be the standard matrix for T (The matrix corresponding to the transformation in terms of a matrix multiplication :[[Maths/Intro to Linear Algebra/Lec 7. The Matrix of a Linear Transformation|ref]])
$$\text{T is invertible} \iff \text{A is invertible}$$
If T is invertible then $T^{-1}$ is a unique linear transformation, given by $$T^{-1}(x)=A^{-1}(x)$$
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-10-02-11-45-37]]
