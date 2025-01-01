
All of the following are equivalent statements:

- $Q$ is an **orthogonal matrix**
- Columns of $Q$ form an **orthonormal basis** for $\mathbb{R}^{n}$
- $Q^{T}Q = I_{n}$
- $Q$ is invertible and $Q^{-1}=Q^{T}$
- **$Q$ preserves inner products** $Qu \cdot Qv = (Qu)^{T} Qv = uQ^{T}Qv = u^{T}v = u \cdot v$
- **Q preserves norms** $||Qu||=\sqrt{Qu \cdot Qu} = \sqrt{u \cdot u} = ||u||$

AN ORTHOGONAL MATRIX HAS ORTHONORMAL COLUMN VECTORS

So to simply check if a matrix is orthogonal, we just need to check if $A^{T}A = I$

---
#theorem Let $P$ and $Q$ be an $n \times n$ matrices. Then 
- $|Q|=1$ or $-1$ $\qquad |Q|^{2} = det(Q)^{2} = |Q||Q| = |Q^{T}||Q|=|Q^{T}Q|=|I|=1$
	- Basically, using $det(A)=det(A^{T})$, we prove that orthogonal matrices must always scale spacial volumes by $1$ or $-1$.
	- Think Geometrically, they are just hypercubes oriented at an angle.
- $Q^{-1}$ and $Q^{T}$ are also orthogonal 
	- $(Q^{T})^{T} = Q$ and $Q^{T}(Q^{T})^{T} = I$
	- meaning that not only the column vectors but row vectors are also orthonormal 

---

## Diagonalization and Orthogonal Matrices
Recall [[Maths/Intro to Linear Algebra/Lec 19. Multiplicities of Eigenvalues & Diagonalization#Diagonalization Algorithm|Lec 19. Multiplicities of Eigenvalues & Diagonalization]]

$P = \begin{bmatrix}v_{1} & \dots & v_{n}\end{bmatrix}$  where $v_{i}$ is an eigenvector and $D$ is a diagonal matrix of corresponding eigenvalues 

If $P$ is an orthogonal matrix and diagonalizable, 
$\implies A^{T} = (PDP^{-1})^{T}= (PDP^{T})^{T} = (P^{T})^{T}D^{T}P^{T} = PDP^{T} = A$
(Note, $D^{T}=D$ since it is just a diagonal matrix)

Hence, if $A$ is an **orthogonal diagonalizable matrix** then A is **symmetric** 
#theorem 

---
## Recall:
#theorem A set of eigenvectors of $A_{n \times n}$ that correspond to distinct eigenvalues is linearly independent.
(They sit on the different support lines only meeting at the origin)

Then
#theorem If $u$ and $v$ are eigenvectors of a symmetric matrix $A$ that corresponds to distinct eigenvalues, then $u \perp v$ (i.e. $u \cdot v = 0)$.

Proof:
Assumption
$Au = \lambda_{1}u$ and $Av = \lambda_{2}v$ where $\lambda_{1} \neq \lambda_{2}$ and $A^{T}=A$ (i.e. $A$ is symmetrical)

$\implies Au \cdot v = \lambda_{1}u \cdot v = \lambda_{1}(u \cdot v)$
and $Av \cdot u = \lambda_{2} v \cdot u = \lambda_{2} (u \cdot v)$

$Au \cdot v = (Au)^{T} v = u^{T}A^{T}v = u^{T}Av$ (by $A^{T}=A$)
$\implies u \cdot (Av) = Av \cdot u$

Hence, we proved $Au \cdot v = Av \cdot u$ $\implies 0 = Au \cdot v - Av \cdot u = (\lambda_{1} - \lambda_{2})u \cdot v$
But we know $\lambda_{1} \neq \lambda_{2}$ hence, the only way $(\lambda_{1} - \lambda_{2})u \cdot v=0$ is if $u \cdot v = 0$

Hence, $u \perp v$

---

#theorem $A_{n \times n}$ is orthogonally diagonalizable $\iff$ $A_{n \times n}$ is Symmetrical 

But didn't we just prove that?
NO! It is something deeper.

Not only are all orth. diag. matrices symmetrical but **all symmetrical matrices are diagonalizable orthogonally Where $A=PDP^{-1}$ and $P$ is an orthogonal matrix (i.e. it has orthonormal column vectors)**

---

## Spectral Decomposition 

Let $A$ be an $n \times n$ symmetric matrix and $P = \begin{bmatrix}u_{1} & \dots  & u_{n}\end{bmatrix}$ where $u_{i}$ is an orthonormal eigenvector, $D$ is the diagonal matrix of corresponding eigenvalues.

I.e. you have an orthogonal Diagonalization of $A$, then:

$A = PDP^{T} = \lambda_{u_{1}} u_{1}u_{1}^{T} + \dots + \lambda_{u_{n}}u_{n}u_{n}^{T}$

i.e. 
- Symmetric Matrix $P_{u_{i}} = u_{i}u_{i}^{T}$ is the orthogonal projection matrix onto $u_{i}$
- $rank(P_{u_{i}})=1$ (each decomposition spans one degree of freedom but that perpendicular to all other degrees of freedom)
- $P_{u_{i}}u_{j} = \cases{0 \quad i \neq j \\ u_{j} \quad i=j}$
- $P_{u_{i}}P_{u_{j}} = \cases{0 \quad i \neq j \\ P_{u_{j}}} \quad i=j$