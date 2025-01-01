## Fibonacci Sequence as a vector equation 

$f_{n+1} = f_{n} + f_{n-1}$

$\implies \begin{bmatrix}f_{n+1}\\f_{n}\end{bmatrix}=\begin{bmatrix}1&1\\1&0\end{bmatrix}\begin{bmatrix}f_{n}\\f_{n-1}\end{bmatrix}$
But since 
$\implies \begin{bmatrix}f_{n}\\f_{n-1}\end{bmatrix}=\begin{bmatrix}1&1\\1&0\end{bmatrix}\begin{bmatrix}f_{n-1}\\f_{n-2}\end{bmatrix}$

$$\implies \begin{bmatrix}f_{n+1}\\f_{n}\end{bmatrix}=\begin{bmatrix}1&1\\1&0\end{bmatrix}^{2}\begin{bmatrix}f_{n-1}\\f_{n-2}\end{bmatrix}$$

So finding next pairs of Fibonacci numbers is just equivalent to having a matrix power.
But finding Squares for matrices is difficult.
Be can tackle such situations...

# Eigenvalues & Eigenvectors & Characteristic equation

#### Example
- if $v \in \mathbb{R}^{2}, \begin{bmatrix}2&0\\0&2\end{bmatrix}v = 2Iv = 2v$
- if $u = \begin{bmatrix}u_{1}\\0\end{bmatrix} in \mathbb{R}^{2}, \begin{bmatrix}3&1\\0&1\end{bmatrix}u = \begin{bmatrix}3&1\\0&1\end{bmatrix}\begin{bmatrix}u_{1}\\0\end{bmatrix} = 3u$

So essentially, multiplication of certain matrices and certain vectors, we have a matrix vector multiplication equivalent to just the scalar multiplication of a vector.

Ahaa! If matrix multiplication is just multiplication for these vectors it must be so easy!

What are these special vectors for certain matrices?

#def Let A be an $n \times n$ matrix. A number (real or even complex!) $\lambda$ is called the **eigenvalue** of A if $Ax=\lambda x$ has a nontrivial solution (i.e. $x \neq 0$). The nontrivial solution $x$ is called an **eigenvector** of the matrix $A$.

### Example 

- Let $\begin{bmatrix}3&0&0\\0&1&2\\0&2&1\end{bmatrix}, u = \begin{bmatrix}1\\0\\0\end{bmatrix}, v = \begin{bmatrix}0\\1\\1\end{bmatrix}$

To see if $u$ and $v$ are eigen values,

we just see if $Av = \lambda_v v$ and if $Au = \lambda_u u$
Obviously, $Au = \begin{bmatrix}3+0+0\\0+0+0\\0+0+0\end{bmatrix} = \begin{bmatrix}3\\0\\0\end{bmatrix} = 3u$
Similarly, $Av = \begin{bmatrix}0+0+0\\0+1+2\\0+2+1\end{bmatrix} = \begin{bmatrix}0\\3\\3\end{bmatrix}=3v$

Ahaa! Sweet! Note : $\lambda_{u} = \lambda_{v} = 3$ They need not be the same!

---
It seems like there can be many such vectors and values. How do we find all of them in a general sense?

## Finding eigenvalues 
- $\lambda$ is an eigenvalue of A $\iff$ $Ax= \lambda x$ has a non trivial solution (From the definition)
$\implies Ax - \lambda x = 0$
$\implies Ax - \lambda Ix = 0$
$$\implies (A-\lambda I)x = 0$$
This is a homogenous equation! We know how to deal with them.

- homogenous equations have a non trivial solution $\iff$ There is no unique solution to the equation $\iff$ Set of Column Vectors of A are linearly dependent  $\iff$ $A - \lambda I$ is NOT invertible $\iff$ $det(A-\lambda I) = 0$ 
hence, to find the eigenvalues, we just need to find values of $\lambda:det(A - \lambda I)=0$

$P(\lambda) = |A-\lambda I|$ is called the characteristic polynomial of a Matrix. The solution to $P(\lambda)=0$ are the eigenvalues.
#### Example
a) Find the eigenvalues of $A = \begin{bmatrix}-4 & 7 & 7 \\ 0  & 3 & 7 \\ 0 & 0 & -4\end{bmatrix}$

$\implies$ values for lambda $: |A- \lambda I|=0$ OR Column vectors of $A - \lambda I$ are linearly dependent, i.e. $\begin{bmatrix}A- \lambda I & 0\end{bmatrix}$ has non trivial solutions 

Either way works!

Determinants are much easy to calculate though...
$|A-\lambda I| = \begin{vmatrix}-4- \lambda  & 7 & 7 \\ 0 & 3-\lambda & 7 \\ 0 & 0 & -4-\lambda\end{vmatrix}$
That is a triangular matrix, hence $|A - \lambda I| = (-4-\lambda)(3-\lambda)(-4-\lambda)$
To find the eigenvalues, this determinant must be  $0$

hence $(-4-\lambda)(3-\lambda)(-4-\lambda) = 0$
$\implies \lambda = -4,3$

Ahaa!
Notice how these are just the diagonal entries of the upper triangular matrix. Upper triangular matrices are so easy to work with!

#theorem The Eigenvalues of a triangular matrix are it's diagonal entries.

To solidify this foundational idea:
- Solve $|A-\lambda I|=0$ to find the eigenvalues $\lambda$
- For each $\lambda$, solve $(A-\lambda I)x = 0$ to find the eigenvalues $x \neq 0$

But hold on! The values of $x$ for which $Ax=0$ is the set of all vectors that collapse to zero upon matrix multiplication! [[Maths/Intro to Linear Algebra/Lec 16. Basis & Dimension & Rank & Nullity|recall]] that is just the Null space of a matrix $A$.

Hence, $(A-\lambda I)x = 0$ is true for eigenvalues and eigenvectors.

The determinant being zero gives us eigenvalues. Eigenvectors are the set of vectors in the null space of $A-\lambda I$. Obviously, i.e. to say, the eigenvectors (vectors in the null space) can only be nonzero vectors if there are values of $\lambda$ for which determinant is zero.
Eigenvectors do not include zero vector tho. So yes, eigenvectors only exist if determinant can be equated to zero for a $\lambda \in \mathbb{R} : |A- \lambda I|$

#def The **eigenspace** of $A_{m \times n}$ corresponding to the eigenvalue $\lambda$ is
- the set of all eigenvectors $v$ such that $Av = \lambda I$, i.e. the null space of $(A-\lambda I)$. since $(A- \lambda I)v = 0$ so $v$ is the set of vectors for which the matrix multiplication maps to zero vector. $v$ can not be a zero vector (trivial) though!

#### Example 
$A = \begin{bmatrix}-4 & -3 \\ 3 & 6\end{bmatrix}$
- $p(\lambda) = \set{\lambda: det(A-\lambda I) = 0} \implies \lambda_{1}=3, \lambda_{2}=5$
- For $\lambda = -3$, solve $(A-\lambda_{1}I)x=0 = (A-3I)x=0$
	- $\begin{bmatrix}-1 & -3 \\ 3 & 9\end{bmatrix}x = 0$
	- $\begin{bmatrix}-1 & -3  & 0\\ 3 & 9 & 0\end{bmatrix}$ $\to$ $\begin{bmatrix}3 & 1 & 0 \\ 0 & 0 & 0\end{bmatrix}$
	- $\implies$ $3x_{1} + x_{2} = 0 \implies x = \begin{bmatrix}x_{1}\\x_{2}\end{bmatrix} = x_{2} \begin{bmatrix} \frac{-1}{2} \\ 1\end{bmatrix}$
	- Hence, the eigenspace of $\lambda_{1}$ is the $Span \set{\begin{bmatrix} \frac{-1}{2} \\ 1\end{bmatrix}}$

The eigenvalues need not always be real btw.

---
## Complex eigenvalues 
$P(\lambda) = |A- \lambda I| = \begin{vmatrix}1-\lambda & 1 \\ -2 & -1-\lambda\end{vmatrix}=0$
$\implies (1-\lambda)(-1-\lambda)   - (1)(-2)= \lambda^{2}+1 = 0$
$\lambda = \pm \sqrt{-1}$
$\lambda_{1}=i,\quad \lambda_{2}=-i$
Hence, for complex eigenvalues, they always come in pairs of complex conjugates.

The Eigen Vectors for which the characteristic equation holds true for these particular values:
$A-\lambda I = 0$
$A - iI = 0$
$\implies \begin{bmatrix}1-i & 1 \\ -2 & -1-i\end{bmatrix} \rightarrow \begin{bmatrix}1-i & 1 \\ 0 & 0\end{bmatrix} \implies (1-i)x_{1} + x_{2} = 0 \implies x_{1} = \frac{-x_{2}}{1-i}$
hence, we have a free variable
$x = \begin{bmatrix}x_{1} \\ x_{2}\end{bmatrix} = x_{2}\begin{bmatrix}\frac{-1}{1-i} \\ 1\end{bmatrix}$
Hence, the eigen space for $\lambda_{1} = Span \set{\begin{bmatrix}\frac{-1}{1-i} \\ 1\end{bmatrix}}$
And similarly, you have a space for $\lambda_{2}$. (these vectors would be complex conjugates for the vectors in space for $\lambda_{1}$, i.e.
- if $v_{1}$ is an eigenvector for real-valued $A_{n \times n}$ with $\lambda_1$, then $v_{2} = \bar{v_{1}}$ is the eigenvector of $A$ with $\lambda_{2} = \bar{\lambda_{1}}$
	- $Av_{2} = A\overline{v_{1}} = \overline{\overline{A}v_{1}}$ (since $\overline{(\overline{A})}=A$)
	- $\implies Av_{2} = \overline{\overline{A}v_{1}} =  \overline{Av_{1}}$ (since A is just real valued, hence $\overline{A} = A$, there are no complex numbers $bi$ to turn into $-bi$)
	- $\implies \lambda_{2}v_{2} = conjugate$
)

### What does it physically mean to have complex eigen values 
Eigen Vectors, physically, are vectors in a vector space that decay into zero vectors after a matrix multiplication/linear transformation.

It's like multiplying certain entries of the vector with certain entries in the matrices and getting a zero.

Having only complex eigenvalues means there are no nontrivial solutions for $A-\lambda I = 0$ for $\lambda \in \mathbb{R}$
But there would be a solution in the complex space $\mathbb{C}$.

These Complex Eigenvalues correspond to complex eigenvectors
That means, there would be a vector with entries $\in \mathbb{C}$, that would decay to zero upon the linear transformation.

---
#### Examples 
If v is an eigenvector of both A & B
$\implies$ v is an eigenvector of $A+B$ & $AB$

Statement 1 means $v$ satisfies $Av=\lambda_{A}v$ and $Bv = \lambda_{B}v$ for some numbers $\lambda_{A}$ and $\lambda_{B}$
$(A+B)v = Av+Bv = \lambda_{A}v + \lambda_{B}v = (\lambda_{A} + \lambda_{B})v$

Ahaa!

$(AB)v = A(Bv) = A(\lambda_{B} v) = \lambda_{B}(Av) = \lambda_{B} \lambda_{A} v$

---
$A-\lambda I$ is NOT invertible $\iff$ $|A - \lambda I|=0$ $\iff$ $\lambda$ is an eigenvalue of $A$ (by definition)

#theorem $A_{n \times n}$ is not invertible $\iff$ $0$ is not the eigenvalue of $A$
- if $0$ were to be the eigenvalue, $|A-0I|=0=|A|$ which obviously means $A$ is not invertible.

If $\lambda$ is an eigenvalue of an invertible matrix $A_{n \times n}$
$\implies$ $\lambda^{-1}$ is an eigenvalue of $A^{-1}$
- Proof:
	- $AA^{-1} = I \qquad Av=\lambda v$
	- $A^{-1}v = A^{-1}(\frac{\lambda}{\lambda}v)=\frac{A^{-1}Av}{\lambda} = \frac{1}{\lambda}Iv=\lambda^{-1}v$

#funfact 
If zero is an eigen value of a matrix, that means that there are multiple vectors in a space collapsing to zero upon the matrix transformation. Hence, the matrix would then NOT be invertible.

---
## Multiplicity of Eigenvalues

### Repeated Eigenvalues
- $A = \begin{bmatrix}3 & 0 \\ 0 & 3\end{bmatrix}$
we already know for a triangular matrix (every diagonal matrix is a triangular matrix), $|A-\lambda I|=0$
yields $(3-\lambda)^{2}=0$
i.e. for a diagonal matrix, the diagonal entries are the eigenvalues.

Hence, for repeated entries in the diagonal of a triangular matrix, the eigenvalues are repeated.

To find the eigenspace of this eigenvalue, we solve for the $Null(A-\lambda I) = Null(A-3I)=Null(0)$
Hence, this includes the entire space $\mathbb{R}^{2}$
hence, $Span \set{\begin{bmatrix}1\\0\end{bmatrix}, \begin{bmatrix}0\\1\end{bmatrix}}$

- $A = \begin{bmatrix}4 & -1 \\ 1 & 2\end{bmatrix}$
- $p(\lambda) = A-\lambda I = (4-\lambda)(2-\lambda) - (-1)(1) = (\lambda-3)^{2}=0$
Hence, $\lambda = 3$
The solution set of $(A-\lambda I)x=0$
is this the $Null(A- \lambda I)= Null(A-3I)$
Thus solve $[A-3I|0]$ 
this gives is the equation $x_{1}-x_{2}=0$
hence eigenspace $= Span \set{\begin{bmatrix}1\\1\end{bmatrix}}$
$dims(eigenspace)=dims(Null(A-\lambda I)) = 1$

---
#theorem $dims(eigenspace) \leq \text{\# of times }\lambda \text{ repreated}$ 

#def  The **algebraic multiplicity** of the eigenvalue $\lambda$ of $A_{n \times n}$ is the power of $t-\lambda$ in the characteristic equation $p(\lambda) = |A - tI|=0$. ^1ebdc2

#def The **geometric multiplicity** is the dimension of the eigenspace for $A_{n \times n}$ for a particular $\lambda$. ^c20120

Geometric Multiplicity $\leq$ Algebraic Multiplicity

#def The **defect** of $\lambda$ is the $multi_{a}(\lambda) - multi_{g}(\lambda)$
the defect can never be negative and if it is non zero, the eigenvalue is defective.

(interesting and useful properties emerge when they are equal)

Basically, each eigenvalue corresponds to a diagonal entry in the REF of a square matrix. The each diagonal entry also corresponds to a possible non-pivot column 

#theorem Let $\lambda$ be an eigenvalue of $A_{n \times n}$ then
$1 \leq multi_{g}(\lambda) \leq multi_{a}(\lambda)$

---
Finally, getting onto the starting golden question... how can we multiply a matrix by itself repeatedly in an easy way?
## Similarity 
#def Two matrices $A_{n \times n}$ and $B_{n \times n}$ are called similar if there is an invertible matrix $P$ such that $A = PBP^{-1}$ 

- $A^{n} = (PBP^{-1})^{n} = PBP^{-1}PBP^{-1} \dots PBP^{-1} = PIBIB \dots IBP^{-1} = PB^{n}P^{-1}$

The trick is, if $B$ happens to be a diagonal matrix, $B^{n}$ is literally a matrix where all it's entries are raised to the power $n$.
$\begin{bmatrix}b_{11} & 0 & 0 \\ 0 & b_{22} & 0 \\ 0 & 0 & b_{33}\end{bmatrix}^{n} = \begin{bmatrix}b_{11}^{n} & 0 & 0 \\ 0 & b_{22}^{n} & 0 \\ 0 & 0 & b_{33}^{n}\end{bmatrix}$

So the idea is, the entire problem for boils down to just 2 matrix multiplications instead of $n$ matrix multiplications to raise $A^{n}$.

The question is, how do we find those similar matrices?

$|A-\lambda I| = |PBP^{-1} - \lambda I| = |PBP^{-1} - \lambda PP^{-1}| = |PBP^{-1} - P \lambda P^{-1}|$
Hold on... this is looking interesting...
$= |P(B-\lambda I)P^{-1}| = |P||(B-\lambda I)||P^{-1}| = |B - \lambda I|$ 
(since the $det(P) = \frac{1}{det(P^{-1})}$)

Hence, $|A-\lambda I| = |B-\lambda I|$
since they have the same characteristic polynomial, they have the same Eigenvalues! (and multiplicity).

$B$ is just a diagonal matrix. Eigenvalues of a diagonal matrix is just the diagonal entries itself. So finding eigenvalues of $A$ would give us directly the matrix $B$. The only thing we need is to find matrix $P$ such that $A = PBP^{-1}$!
