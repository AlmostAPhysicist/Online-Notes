$\begin{bmatrix} a & b & c \\ d & e & f \\ g & h & i \end{bmatrix}$ $\begin{array}{cc|c}1 & 2 & 3\end{array}$
$$\left[\begin{array}{cc|c}
1 & 1 & 3 \\
2 & 5 & 9
\end{array}\right]$$


## Def 
A row of matrix is a **zero row** if all its entries are zero and a **nonzero row** otherwise.

The **leading entry** is the leftmost nonzero entry of a nonzero row. 
>$\begin{bmatrix} 0 & 0 & \boldsymbol{1} & 2 \end{bmatrix}$
**1** is the leading entry

A matrix is in the **Row-echelon form (REF)** if:
- The zero rows are at the bottom of the matrix
- Each leading entry is in the column to the right of the one in the previous row
- The entries under leading entries are equal to zero
### Example:
$\begin{bmatrix} 0 & 0 & \boldsymbol{1} & 2 \\ * & * & * & \boldsymbol{2}\end{bmatrix}$

$\begin{bmatrix} 1&2&3&4 \\ 0 & 0 & \boldsymbol{1} & 2 \\ 0 & 0 & 0 & \boldsymbol{2}\end{bmatrix}$

- if there is a staircase and the height of each step is 1, then it is in the row-echelon form.
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-06-04-02-40]]

$\begin{bmatrix}1&0&0\\0&0&1\\0&0&1\end{bmatrix}$
This is NOT the Row-echelon form either!

---
## Def
A matrix is in the **reduced row-echelon form (RREF)** if: ^402862
- It is in REF
- The leading entries are equal to 1
- Each leading entry is the only non-zero entry in it's column

$\begin{bmatrix} 1&-1&0&0 \\ 0 & 0 & \boldsymbol{1} & -2 \\ 0 & 0 & 0 & 0\end{bmatrix}$
Note how it makes a staircase of height 1
- is in the REF 
- all the leading entries (if any) are 1 too!
- each leading entry is the only non-zero entry in it's column
$\begin{bmatrix} 0&1&0&0 \\ 0 & 0 & \boldsymbol{1} & 0 \\ 0 & 0 & 0 & \boldsymbol{1}\end{bmatrix}$
Again, these are examples of RREF (REDUCE ROW-ECHELON FORM!)

$\begin{bmatrix} 1&-1&2&0 \\ 0 & 0 & \boldsymbol{1} & -2 \\ 0 & 0 & 0 & 2\end{bmatrix}$
This one is REF but NOT RREF! (note how all first entries are not the only nonzero entries in their column (the vertical))

---
$\begin{bmatrix} 1&0&0&3 \\ 0 & \boldsymbol{1} & 0 & -2 \\ 0 & 0 & \boldsymbol{1} & 2 \\ 0&0&0&0\end{bmatrix}$
**THIS IS A RREF!**
Note now it satisfies are the conditions...
- It's an REF
	- Leading nonzero entries are always in right of leading nonzero entries in rows above
	- Entries below the leading nonzero entries are 0
- All leading non-zero entries are 1
- All entries in the same row as the leading entries are 0
- The non zero elements in 4th column do not cause any trouble since they are not the first non-zero elements in their row and are not above any such element in any other row either.
# Theorem
Each matrix A is row equivalent to a unique matrix in RREF called **RREF of A (rref(A))**

$system \rightarrow [A|b] \quad \overrightarrow{\text{elementary row operations}} \quad [R|c]\rightarrow system$

When solving a system of linear equations, we try $[R|c]$ to be $rref([A|b])$ or $ref([A|b])$

To solve the system and reduce $[A|b]\rightarrow[R|c]$, we use the algorithm/method called **Gaussian elimination (row reduction) & Gauss-Jordan Algorithm**

## Def 
The **pivot position** of A are the positions that contain the leading entries of $rref(A)$

The **pivot column** of A is the column of A that contain the same pivot position of A. ^aea1b9

![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-06-04-19-42]]
The circled numbers are at the pivot positions, red columns are pivot columns and blue columns are non-pivot positions.

## Algorithm:
Input: Any Matrix A
Output: An REF of A
Procedure:
- Start with the left most nonzero column. The pivot position is at the top.
- Select a nonzero entry in the column to be the pivot. Move it into the pivot position.
- Kill the entries below that pivot.
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-06-04-25-45]]


## Finding Solutions to Linear equations

$$\left[\begin{array}{ccc|c}
1 & 0 & 0 & 2 \\
0 & 1 & 0 & 7 \\
0 & 0 & 0 & 4
\end{array}\right]\implies \text{no solution}$$
$$\left[\begin{array}{ccc|c}
1 & 0 & 0 & 1 \\
0 & 1 & 0 & 1 \\
0 & 0 & 1 & 2
\end{array}\right]\implies \text{unique solution}$$
$$\left[\begin{array}{ccc|c}
1 & 0 & 0 & 2 \\
0 & 1 & 1 & 1 \\
0 & 0 & 0 & 0
\end{array}\right]\implies x_{2} \space basic/dependent\space variable \text{is a variable dependent on }x_3$$

here, $x_{1}=2 \quad | \quad x_2=1-x_{3} \quad| \quad x_3=x_3$ 
$x_3$ is a free variable hence there are Infinitely many solutions.

## Def
Linear system is consistent for any solution (1 or Infinite) and inconsistent for no solutions.

# Theorem — Test For Consistency 
Solve the system with $[R|c]$ where $R$ is a RREF/REF:
$[R|c]$ contains a row of form $[0 \space 0 \space 0 \dots \space| \space d]$ where $d\neq 0$, then it has no solution and is inconsistent.

**If there are no such rows, it is *consistent***
- If all columns of R are **pivot columns $\rightarrow$ Unique solution**
- If no, there are **free variables $\rightarrow$ infinitely many solutions**


# Conclusion

To Solve a linear system:

- Find the Augmented Matrix $[A|b] of the system$
- $[A|b] \quad \overrightarrow{\text{row reduction \& Gauss-Jordan}} \quad [R|c]$ where $R=rref(A)$
- Solve the system with $[R|c]$
- 




