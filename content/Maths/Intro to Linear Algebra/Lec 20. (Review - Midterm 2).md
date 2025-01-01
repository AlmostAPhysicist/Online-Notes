## Determinant 
It is, physically, how a certain unit area/n-dimensional volume  (and hence any of it's multiple) is scaled by a transformation.

### How to find it?
- Co-factor expansion
	- along $ith$ row: $|A_{n \times n}| = \sum^{n}_{k=1} a_{ik}(-1)^{i+k} |A_{ik}|$
	- along $jth$ column: $|A_{n \times n}| = \sum^{n}_{k=1} a_{kj}(-1)^{j+k} |A_{kj}|$
		- Here, $|A_{ij}|$ is the determinant of the matrix that does NOT include the $ith$ row and $jth$ column
		- This Definition is recursive!
			- The base case is $|a|$ = $a$ where $a$ is just a singular matrix (one term inside, $A_{1 \times 1}$)
			- You can also quite easily calculate the $det(A_{2 \times 2})$ as the (diagonal product) — (off diagonal product)
			- Essentially, you break a determinant into a determinant of a lower dimensional matrix.
		- It's smart to chose a row/column that has least non-zero entries.

- Triangular matrix
	- Here, the cofactor expansion works out nicely to be the product of the diagonals.

- TURNING A MATRIX INTO TRIANGULAR MATRIX!
	- Keep track of what the elementary row operations do to the determinant while changing the matrix into a row equivalent RREF/REF matrix.
	- RREF/REF are triangular matrices!
		- Row Addition has no effect on determinant $A \xrightarrow{r_{i} + cr_{j} \rightarrow new \space r_{i}}B$, then $|B|=|A|$ (skewing has no effect)
		- Row Scaling scales the determinant $A \xrightarrow{cr_{i} \rightarrow new \space r_{i}}B$, then $|B|=c|A|$ (scaling side lengths)
		- Row Switching flips sign $A \xrightarrow{r_{i} + cr_{j} \rightarrow new \space r_{j}}B$, then $|B|=|A|$ (row addition + row scaling by $-1$, also, flip space)

### Properties of Determinants 
- $|AB| = |A||B|$
- $|cA_{n \times n}| = c^{n}|A|$ (each side is scaled by $c$)
- $|A^T|=|A|$ the idea is, a sequence of row operations on $A$ are the same as column operations on $A^T$. or intuitively, both represent the same thing, choice of row and columns as vectors is arbitrary.
- $A$ is invertible $\iff$ $|A| \neq 0 \iff$ The columns of $A$ are linearly independent
- - If $A$ is invertible then $A^{-1}=\frac{1}{|A|}$ since $A^{-1}A = I$ hence $|A^{-1}A| = |I| = 1=|A^{-1}||A|$ 
	- in fact, in general, $A^{n}= |A|^n$

($A^{-1} = \frac{1}{|A|} adj(A)$ where $adj(A) = cofactor(A)^{T}$)

## Vector Spaces 
$H$ is a vector space if
- $\vec{0}$ (zero vector) $\in H$
	- Usually, you prove this by seeing if the definition of elements hold true for the zero vector.
- $A+B \in H \space \forall \space A,B \in H$
	- You usually do this by taking advantage of the fact that $A(B + C) = AB + AC$, so if for instance $H$ is the space of matrices for which $AH = 0$ then if $B,C \in H$, $\implies AB = 0 = AC$ but then $AB + AC = 0 \implies A(B+C)=0$
		- hence $B+C \in H$
- $cA \in H \forall A \in H \space \& \space c \in \mathbb{R}$
	- i.e. If a $H$ has all linear combinations of elements within itself.
	- eg: $A(cB) = c(AB)$ so if $AB=0$, so is $A(cB)$ hence, $cB$ must also be in $H$


- For a **subspace**, you just prove/state/determine whether all elements within a space are also elements in another space
(i.e. $H \subseteq S \iff e \in S \space \forall \space e \in H$, this is usually true by the definition of elements of $H$)

## Special Subspaces 
### Col(A)
- $Span \set{\text{columns of A}}$
- $u \in Col(A) \iff$ $u$ is a linear combination of Columns of $A$ $\iff$ $Ax=u$ has a solution 
	- $[A|u]$ has no $\begin{bmatrix}0 & 0 & 0 & | & b\end{bmatrix}$ row
### Row(A)
- $Span \set{\text{rows of A}}$
### Null(A)
- $Span \set{\text{Non-Pivot Columns of RREF(A)}}$ (these are the **free variable vectors**. So they are vectors that can take values for pivot column variables being $0$, hence giving us non-trivial solutions for $Ax=0$)
- Solution space for $Ax=0$
	- To find if $v$ is in the $Null(A)$, no funny business required, just do a matrix multiplication! If it is $0$, it is in the null space of $A$. 
	- (You might check if $v$ is a linear combination of basis of $Null(A)$, by saying $\begin{bmatrix}v_{1} & v_{2} & | & v\end{bmatrix}$ is consistent but WHY)


## Basis and Dimensions 
$V$ is the **basis** for the space $H$ if
- V is linearly independent 
- $H = Span(V)$
i.e. $V$ spans all the space and you can reach every point in space $H$ as a linear combination of vectors $V$
And if $V$ is a linearly independent vectors.


| Subspace              | of             | dim        | basis                                                                                                                                                |
| --------------------- | -------------- | ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| $Col(A_{m \times n})$ | $\mathbb{R}^m$ | rank(A)    | {columns of A corresponding to pivot columns in REF(A)}                                                                                              |
| $Nul(A_{m \times n})$ | $\mathbb{R}^n$ | nullity(A) | {vectors in the parametric<br>vector form of general solution<br>to $Ax=0$}                                                                          |
| $Row(A_{m \times n})$ | $\mathbb{R}^n$ | rank(A)    | {non-zero $rows^T$ of the REF/RREF of A} (the rows within the REF(A) itself, not the original matrix)<br> (transpose only to treat as column vector) |

- $dim(Col(A))=dim(Row(A))=rank(A)$ is the dimensions that matrix $A$ outputs
- $dim(Null(A))$ is the dimensions of vectors that goes to $0$ (i.e. $dim(input)-dim(output)$)
- $rank(A^{T})=rank(A)$, i.e. they both have the same degrees of freedom in the output space.
(it's like saying whether you make a choice of looking at rows or vectors, the input and output space are going to be the same in terms of independent directions. 
$A = \begin{bmatrix}1 & 2 & 3 \\ 4 & 5 & 6\end{bmatrix}$
takes in a 3d vector and outputs a 2d vector
$A^{T}$ inputs 2d vectors so it can only output 3d vectors for 2 degrees of freedom.

So even though the vectors are of a higher space, the degrees of freedom for both $A$ and $A^{T}$)


**Note: Column space of $A$ is NOT the same as the Column space of $REF(A)$**
You can have different columns spaces since you have performed some row operations so you may lose few elemental dimensions (not degrees of freedom though)
But the Pivot Columns give you insights about columns of A making up its basis.

**The ROW space of A IS the same as Row space of REF(A).**
But the rows do not correspond to the same rows in A since obviously you shifted rows around (but you maintained their dimensions)

Hence, for the Basis of Col(A), you use columns of A corresponding to Pivot columns in REF(A)
But for the basis of Row(A), you use the non zero rows of REF(A) itself.

## Coordinates 
Coordinates vectors of a space are the weights that when you multiply by the matrix gives you a certain vector in the standard matrix.

It is the coordinates for a space (particular basis) that marks the same point in the standard basis space.

$x = A[x]_{A}$

To change between spaces and their coordinates, you use something that follows Immediately after, i.e. $[x]_{A} =  A^{-1}x$

Hence, to find coordinates for space $B$, 

$[x]_{B} \rightarrow [x]_A$, you convert $[x]_{B}$ to $x$ and then $x$ to $[x]_A$

$P_{B \to A}[x]_{B} = [x]_{A} = A^{-1}x = A^{-1}B[x]_{B}$

---

## Eigenvalues and Eigen vectors 

For particular 
