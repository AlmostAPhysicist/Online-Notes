Physically, determinant is the n-dimensional volume of the n dimensional parallelogram created by vectors of an Matrix in space $\mathbb{R}^n$ ($A_{n \times n}$)

---
## How to calculate 
#def Let $A$ be an $n \times n$ matrix. $A_{ij}$ is then defined as the $(n-1) \times (n-1)$ matrix the you get when you remove the $ith$ row and $jth$ column from the original matrix $A$.

### Example 

$A=\begin{bmatrix}1&2&3\\4&5&6\\7&8&9\end{bmatrix}$
$\implies A_{12} = \begin{bmatrix}5&6\\8&9\end{bmatrix}$
$\implies A_{32} = \begin{bmatrix}1&3\\4&6\end{bmatrix}$
---
# Notation and General Form

$$\sum^{n}_{i=1} a_{ij}\,(-1)^{i+j} \, |A_{ij}|$$ or $$\sum^{n}_{j=1} a_{ij}\,(-1)^{i+j} \, |A_{ij}|$$

---
Determinant of a $1 \times 1$ matrix is just the value of the term itself
---
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-10-11-04-14-33]]

Determinant of a $2 \times 2$ matrix is just 
---
$$product(\text{diagonal terms}) - product(\text{off-diagonal terms})$$
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-10-11-04-17-29]]
(off diagonal being the diagonal in the opposite direction)

Determinant of a $3 \times 3$ matrix
---
# Co-Factor and Co-factor expansion
#def The (i,j)-cofactor is given by $C_{ij}=(-1)^{i+j}|A_{ij}|$
$\sum_{j=1}^{j=n} (-1)^{i+j} \cdot |A_{ij}|$ , $i=1$

![[Maths/Intro to Linear Algebra/attachments/Drawing 24-10-11-04-38-36]]
or simply $\sum_{j=1}^n a_{ij}c_{ij} = a_{i1}c_{i1} + a_{i2}c_{i2} + a_{i3}c_{i3}$ for $3 \times 3$ matrix.

![[Maths/Intro to Linear Algebra/attachments/Drawing 24-10-11-04-43-51]]
Note, cofactor has a sign too!

But actually, you can do it for any row. you can have $i = 0,1,2 \dots n$

![[Maths/Intro to Linear Algebra/attachments/Drawing 24-10-11-04-23-15]]

( #cheesy think about why it is zero? something to do with linear dependency?)

---
So based on whichever is computationally easy, you can chose whatever row you like.

Example:
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-10-11-04-40-46]]
$-3  \begin{vmatrix}\begin{bmatrix}1&2&4\\0&2&-3\\2&0&0\end{bmatrix}\end{vmatrix} = -3* (2*(2(-3)-4(2)))=-6*(-14)=84$

---
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-10-11-04-46-39]]
#theorem The determinant of an $n \times n$ upper/lower triangular matrix is the product of its diagonal entries ^d1f706
(VERY IMPORTANT)
# Determinants and Row reduction
a faster way to compute a determinant is usually to alter the matrix in a form that makes computing a determinant easy. The only thing we need to know to do that is how changing the matrix changes the determinant.

Note, REF(A) is just an upper triangular matrix!

So converting to REF would simplify the determinant.

#theorem Let $A$ be an $n \times n$ matrix
- row switching makes the determinant negative | $A \xrightarrow{r_{i} \rightleftarrows r_{j}} B$, $\quad |B|=-|A|$
- row scaling scales up the determinant by the same scalar | $A \xrightarrow{cr_{i} \rightarrow r_i} B$, $\quad |B|=c|A|$
- row addition does NOT change the determinant | $A \xrightarrow{r_{i}-r_{j} \rightarrow r_{i}} B$, $\quad |B|=|A|$

## Conclusion
The idea is, you can calculate the determinant of a matrix, simply by turning it into it's REF by simple row operations while keeping track of what all the row operations do to the determinant (whether they scale it or negate it.)

Since the REF(A) would be an upper triangular matrix, you just multiply the diagonal elements of the matrix, and you get the determinant since by [[#^d1f706|Theorem]], that is simply the determinant of the triangular matrices (simply because co factor expansion cancels out at all times other than diagonals)

If there are many zeros in a row, simply do the Co-Factor expansion and calculate the determinant. But it's often easier to convert a matrix to it's REF and simply find the product of the diagonals.

---
# Properties out of all this story:
- $|cA_{n \times n}|=c^n|A|$ since we need to transform $c$ rows of $A$ and each time we scale up by $c$.
- $|AB|=|A||B|$
- $|A^T|=|A|$ the idea is, a sequence of row operations on $A$ are the same as column operations on $A^T$. or intuitively, both represent the same thing, choice of row and columns as vectors is arbitrary.
- $A$ is invertible $\iff$ $|A| \neq 0 \iff$ The columns of $A$ are linearly independent
- If $A$ is invertible then $A^{-1}=\frac{1}{|A|}$ since $A^{-1}A = I$ hence $|A^{-1}A| = |I| = 1=|A^{-1}||A|$ 
	- in fact, in general, $A^{n}= |A|^n$


![[Maths/Intro to Linear Algebra/attachments/2024_10_15 1_13 am Office Lens.jpg]]

Essentially, the Determinant is the sum $\sum^{n}_{i=1} a_{ij}\,c_{ij}$ or $\sum^{n}_{j=1} a_{ij}\,c_{ij}$
(i.e. Sum of all the products of elements in a row/column and their respective Co-factors) where $c_{ij}$ or the Co-factor is defined as $(-1)^{i+j} \, |A_{ij}|$ where $A_{ij}$ is further defined as the matrix you get from a parent matrix after removing the $i^{th}$ row and $j^{th}$ column.

So Determinant kinda has this recursive definition where the final form of recursion... the determinant of a $1 \times 1$ matrix is the element in the matrix itself.

This is called the **Co-factor Expansion**.

It turns out that the cofactor expansion of a triangular (either upper or lower) simplifies to the product of the diagonal terms since everything else in the expansion nullifies.

You CAN perform elementary row operations on a matrix and account for how each row operation changes it's determinant. Converting to the REF, you can convert any Matrix into a triangular Matrix and hence, another way of finding the determinant of a Matrix is to perform row operations on it, keep track of how you scale and change the determinant and use the trivial solution for the Triangular Matrix you get at the end (|$\triangle$Matrix|=Product of Diagonals) to get the determinant.


Both are equivalent methods and use the actual cofactor expansion definition just that the solution for Triangular Matrices is very simple.

Depending on how close you are to a scarce row/column.

PHYSICALLY, the determinant represents the n-dimensional area/volume of any n-dimensional parallelogram in space $\mathbb{R}^n$.
#cheesy Determinant of a triangular matrix is like asking the volume of a stretched n-dimensional cube... just products of the perpendicular heights. (the slices still remain the same as the unstretched version... think back [[Maths/Calc 2/2. Applications of Integrals#Washer method|Washer Method]] from Calculus!)
(Determinant of a diagonal matrix in fact, IS EXACTLY the volume of an n-dimensional cube without stretching it!)

