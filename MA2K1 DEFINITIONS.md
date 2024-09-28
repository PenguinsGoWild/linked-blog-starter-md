**Definition 1.1.6**: A finite set of linear equations in the variables $x_1, x_2,\:\dots,x_n$ is called a system of linear equations (or a linear system)
$$\newcommand{\R}{\mathbb{R}}
\newcommand{\bR}{\bf{R}}
\newcommand{\bA}{\bf{A}}
$$
**Definition 1.1.9**: A system of linear equations that has no solution is said to be inconsistent. A system that has at least on solution is called consistent.
_Remark_: Every system of linear equations has either no solution, only one solution or infinitely many solutions.

Given two lines in the $xy$-plane,
	a) The system has no solution if and only if the first line and the second line are different but parallel lines.
	b) The system has only one solution if and only if the first line and second lines are not parallel lines.
	c) The system has infinitely many solutions if and only if the first and second lines are the same line.
	_Note that the two lines are parallel if and only if $a_1 = ka_2$ and $b_1 = kb_2$ for a nonzero real number $k$._

Given two planes in the $xyz$-space,
	a) The system has no solution if and only if the first plane and the second plane are different but parallel.
	b) The system cannot have only one soltuion.
	c) The system has infinitely many solutions if and only if either the first plane and second plane intersect at a line or the first plane and the second plane are the same plane.
	_Note that the two planes are parallel if and only if $a_1 = ka_2$ and $b_1 = kb_2$ and $c_1 = kc_2$ for a nonzero real number $k$._

**Discussion 1.2.3**: The following are the basic techniques for solving a system of linear equations:
	1. Multiply an equation by a nonzero constant.
	2. Interchange two equations.
	3. Add a multiple of one equation to another equation.
In terms of the augmented matrix, these correspond to:
	1. Multiply a row by a nonzero constant. 
	2. Interchange two rows.
	3. Add a multiple of one row to another row.

**Definition 1.2.4**: The three operations of the augmented matrix described above are known as elementary row operations.

**Definition 1.2.4**: Two augmented matrices are said to be _row equivalent_ if one can be obtained from the other by a series of elementary row operations.

**Theorem 1.2.7**: If augmented matrices of two systems of linear equations are _row equivalent_, then the two systems have the same set of solutions.

**Remark 1.2.9**: To see why Theorem 1.2.7 is true, we only need to check that every elementary row operation applied to an augmented matrix will not change the solution set of the corresponding linear system. Since it is easier to work with linear systems using the matrix representation discussed in Chapter 2, we shall postpone the proof of the theorem to Section 2.4, see Remark 2.4.6.

**Definition 1.3.1**: An augmented matrix is said to be in row-echelon form if it has the following properties:
	1. If there are any rows that consist entirely of zeros, then they are grouped together at the bottom of the matrix.
	2. In each pivot column, except the pivot point, all other entries are zero.
	In a *row-echelon form*, the leading entries of **nonzero rows** are also called **pivot points**. A **column** of *row-echelon form* is called a **pivot column** if it contains a **pivot point**; otherwise, it is called a **non-pivot column**.
	An **augmented matrix** is said to be in *reduced row-echelon form* if it is in *row-echelon form* and has the following addition properties:
		3. The leading entry of every nonzero row is 1.
		4. In each pivot column , except the pivot point, all other entries are zero.

_Remark 1.3.2_: In some textbooks, row-echelon forms are required to have the additional property 3 in Definition 1.3.1.

**Definition 1.4.1**: Let $\mathbf{A}$ and $\bf{R}$ be _row-equivalent augmented matrices_, i.e. $\bf{R}$ can be obtained from $\bf{A}$ by a series of elementary row operations. if $\bR$ is in _row-echelon form_, $\bR$ is called a _row-echelon form_ of $\bA$ and $\bA$ is said to have a _row-echelon form_ $\bR$. Similarly, if $\bR$ is in _reduced row-echelon form_, $\bR$ is called a _reduced row-echelon form_ of $\bA$ and $\bA$ is said to have a _reduced row-echelon form_ $\bR$.

**Algorithm 1.4.2 (Gaussian Elimination)** The following procedures reduce an augmented matrix to a row-echelon form by using elementary row operations.

**Step 1**: Locate the leftmost column that does not consist entirely of zeros.
**Step 2**: Interchange the top row with another row, if necessary, to bring a nonzero entry to the top of the column found in Step 1.
**Step 3**: For each row below the top row, add a suitable multiple of the top row to it so that the entry below the leading entry of the top row becomes zero.
**Step 4**: Now cover the top row in the matrix and begin again with Step 1 applied to the submatrix that remains. Continue in this way until the entire matrix is in _row-echelon form_.
_Algorithm 1.4.3 (Gauss-Jordan Elimination)_ Given an augmented matrix, we use **Algorithm 1.4.2** to reduce it to _row-echelon form_. Then follow the following procedures to reduce it to _row-echelon form_.
**Step 5**: Multiply a suitable constant to each row so that all the leading entire become 1.
**Step 6**: Beginning with the last nonzero row and working upward, add suitable multiples of each row to the rows above to introduce zeros above the leading entries.

**Discussion** 1.4.6: To solve a system of linear equations, what we need to do is to apply either **Gaussian Elimination** or **Gauss-Jordan Elimination** to reduce the augmented matrix to a _row-echelon form_ or the _reduced row-echelon form_. As we have seen in Theorem 1.2.7, the row operations do not change the solutions to the system. Thus by solving the system corresponding to the augmented matrix in a row-echelon form or the reduced row-echelon form, we can find the solutions to the original system easily.

For both methods, to get a general solution, the variables corresponding to non-pivot columns are first set to be arbitrary. Then we equate the other variables accordingly. 

_Remark 1.4.8_
1. A linear system is inconsistent, i.e. has no solution, if the last column of a row-echelon form of the augmented matrix is a pivot column, i.e. there is a row with nonzero last entry but zero elsewhere.
2. A consistent linear system has only one solution if except the last column, every column of a row-echelon form of the augmented matrix is a pivot column.
	In other words, a consistent linear system has only one solution if the number of variables in the linear system is equal to the number of nonzero rows in a _row-echelon form_ of the augmented matrix.
3. A consistent linear system has infinitely many solutions if apart from the last column, a _row-echelon form_ of the augmented matrix has at least one more non-pivot column.
	In other words, a consistent linear system has infinitely many solutions if the number of variables in the linear system is greater than the number of nonzero rows in a _row-echelon form_ of the augmented matrix.

*Notation 1.4.9*: When doing _elementary row operations_, we adopt the following notation:
	1. $kR_i$ means "multiply the $i$th row by the constant $k$".
	2. $R_i$ $\longleftrightarrow$ $R_j$ means "interchange the $i$th row by the constant $k$".
	3. $R_j$ $+$ $k$$R_i$ means "add $k$ times of the $i$th row to the $j$th row".

**Discussion 1.4.11**: Given a consistent system of linear equations in three variables $x,y,z,$ each nonzero equation in the system represents a plane in the $xyz$-space. Solutions to the system are intersection points of these planes. Now, let us first reduce the augmented matrix of the linear system to a _row-echelon form_  $\bR$. Since the system is consistent, there are at most three nonzero rows in $\bR$.
	1. Suppose $\bR$ has three nonzero rows. By *Remark 1.4.8.2,* the system has only one solution. On the other hand, the three rows of $\bR$ represent three planes that intersect at a common point, which is the solution to the system.
	2. Suppose $\bR$ has to nonzero rows. Apart from the last columns, $\bR$ has one more non-pivot column. So a general solution for the system needs only one arbitrary parameter.
	3. Suppose $\bR$ has only nonzero row. A general solution for the system needs two arbitrary parameter. On the other hand, the two nonzero rows of  $\bR$ gives us two non-parallel planes and they intersect at a common line. this means that the line of intersection is described by a general solution with one arbitrary parameter.
	4. Suppose $\bR$ has no nonzero row. The system is a zero system. A general solution needs three arbitrary parameter and it represents the whole $xyz$-space.

**Definition 1.5.1**: A system of linear equation is said to be homogeneous if it has the form
$$\Huge\left\{\substack{
a_{11}x_1&+&a_{12}x_2 &+&\:\dots &+& a_{1n}x_n &=& 0 \\ 
a_{21}x_1&+&a_{22}x_2&+&\:\dots&+&a_{2n}x_n &=& 0\\
&\vdots &&&&&&\vdots&\\
a_{m1}x_1&+&a_{m2}x_m &+&\:\dots &+& a_{mn}x_n &=& 0 
}\right.$$
where $a_{11},a_{12},\:\dots,a_{mn}$ are real constants. a linear system is called non-homogeneous if it is not homogeneous.
Note that $x_1 = 1, x_2 = 0,\:\dots, x_n = 0$ is always a solution to the homogeneous system and it is called the trivial solution. any solution other than the trivial solution is called a non-trivial solution.

**Discussion 1.5.3**
1. In the $xy$-space, the equations
$$\Huge\left\{ \substack{
&a_1x& \, &+& \, &b_1y& \, &=& \, &0& \quad &(L_1)& \\ 
&a_2x& \, &+& \, &b_2y& \, &=& \, &0&, \quad &(L_2)&
}\right.$$
where $a_1,\,b_1$ are not both zero and $a_2,\,b_2$ are not both zero, are straight lines through the origin (i.e. the point $(0,0)$).
	(a) The system has only the trivial solution if the only if $L_{1}$ and $L_{2}$ are not the same lines.
	(b) The system has non-trivial solution if and only if $L_{1}$ and $L_{2}$ are the same line.
 
 2. In the three dimensional space, the two equations in the system
 $$\Huge\left\{ \substack{
&a_1x& \, &+& \, &b_1y& \, &+& \, &c_1z& \, &=& \, &0& \quad &(P_1)& \\ 
&a_2x& \, &+& \, &b_2y& \, &+& \, &c_2z& \, &=& \, &0&, \quad &(P_2)&
}\right.$$
where $a_1,b_1,c_1$ are not all zero and $a_2,b_2,c_2$ are not all zero, represent two planes containing the origin (i.e. the point $(0,0,0)$). The system always has non-trivial solution, see _Remark 1.5.4.2_.

_Remark 1.5.4_
1. A homogeneous system of linear equation has either only the trivial solution or infinitely many solutions in addition to the trivial solution.
2. A homogeneous system of linear equation with more unknowns than equations has infinitely many solutions.

# Chapter 2
# Matrices

_Definition 2.1.1_: A matrix (plural matrices) is a rectangular array of numbers. The numbers in the array are called entries in the matrix. The size of a matrix is given by $m \times n$ where $m$is the number of rows and $n$ is the number of columns. The $(i,j)$-entry of a matrix is the number which is in the $i$th row and $j$th column of the matrix.

_Definition  2.1.3_: A column matrix (or a _column vector_) is a matrix with only one column. A row matrix (or a _row vector_) is a matrix with only one row.

*Example 1*
$$
\left(
\begin{array}{cccc}
a_1 & a_2 & \dots & a_n
\end{array}
\right)
$$
_Example 2_
$$
\left(
\begin{array}{c}
a_1\\a_2\\\vdots\\a_m
\end{array}
\right)
$$
_Notation 2.1.5_: In general, an ${m} \times{n}$ matrix can be written as
$$
A =
\left(
\begin{array}{cccc}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n}\\
\vdots & \vdots &  & \vdots \\
a_{m1} & a_{m2} & \dots & a_{mn}\\
\end{array}
\right),
$$
or simply $A = (a_{ij})_{m \times n}$ where $a_{ij}$ is th $(i,j)$-entry of $A$. Sometimes, if the size of the matrix is already known, we may just write $A$ $=$ $(a_{ij})$.

_Definition 2.1.7_: The following are some special types of matrices:
1. A matrix is called a square matrix if it has the same number of _rows_ and _columns_. In particular, an ${n} \times{n}$ square matrix is called a _square matrix_ of order $n$.
2. Given a square matrix $A = (a_{ij})$ of order  $n$, the diagonal of $A$ is the sequence of entries $a_{11},a_{22},\:\dots,a_{nn}$. The entries $a_{ii}$ are called the _diagonal entries_ while $a_{ij}$, $i \ne j$, are called _non-diagonal entries_. A square matrix is called a _diagonal matrix_ if all its non-diagonal entries are zero, i.e.
		$A = (a_{ij})_{n \times n}$ is a diagonal matrix $\Leftrightarrow$ $a_{ij}$ $= 0$ whenever $i \ne j$.
3. A diagonal matrix is called a _scaler matrix_ if all its diagonal entries are the same, i.e.
		$$A = (a_{ij})_{n \times n} \;\: \textnormal{is a scaler matrix} \Leftrightarrow a_{ij} = \Huge\left\{ \substack{
		0 & \;\;\; & \textnormal{if} & \; i \ne j \\
		c & \;\;\; & \textnormal{if} & \; i \ne j
		}\right.\quad \normalsize\textnormal{ for a constant c.}$$
4. A diagonal matrix is called an _identity matrix_ if all its diagonal entries are 1. We use $I_n$ to denote the identity matrix of order $n$. Sometimes we write $I$ instead of $I_n$ when there is no danger of confusion.
5. A matrix with all entries equal to zero is called a _zero matrix_. We denote the ${m} \times{n}$ zero matrix by $0_{m\times n}$, or simple $0$.
6. A square matrix $(a_{ij})$ is called symmetric if $a_{ij} = a_{ji}$ for all $i,j$.
7. A square matrix $(a_{ij})$ is called _upper triangular_ if $a_{ij}$ $=$ $0$ whenever $i > j$; and a square matrix $(a_{ij})$ is called _lower triangular_ if $a_{ij}$ $= 0$ whenever $i < j$. Both upper and lower triangular matrices are called *triangular matrices*.

_Definition 2.2.1_: Two matrices are said to be equal if they have the same size and their corresponding entries are equal. that is given $A = (a_{ij})_{m \times n}$ and $B = (b_{ij})_{p \times q}$, $A$ is equal to $B$ if $m = p, n = q,$ and $a_{ij}$ = $b_{ij}$ for all $i,j$.

_Definition  2.2.3_: Let $A = (a_{ij})_{m \times n},$ $B = (B_{ij})_{m \times n}$ and $c$ a real constant. We define the matrices $A +B, A - B$ and $cA$ as follows:
1. **(Matrix Addition)** $A + B = (a_{ij} +b_{ij})_{m\times n}.$ 
2. **(Matrix Subtraction)** $A - B = (a_{ij} -b_{ij})_{m\times n}.$ 
3. **(Scalar Multiplication)** $cA = (ca_{ij})_{m \times n},$ where $c$ is usually called a _scaler_.

_Remark  2.2.5_
1. Given a matrix $A$, we normally use $-A$ to denote the matrix $(-1)A$.
2. The matrix subtraction can be define using the matrix addition: Given two matrices $A$ and $B$ of the same size, $A - B$ is defined to be the matrix $A + (-B)$.

**Theorem 2.2.6**: Let $A, B, C$ be matrices of the same size and $c, d$ scalers. Then
1. **(Commutative Law for Matrix Addition)** $A + B = B + A,$
2. **(Associative Law for Matrix Addition)** $A + (B + C) = (A + B) + C,$
3. $c(A+B) = cA + dA),$
4. $(c + d)A = cA + dA,$
5. $c(dA) = (cd)A = d(cA),$
6. $A+0 = 0 + A = A,$
7. $A - A = 0$ and
8. $0A = 0$ (in here, 0 on the LHS is the number zero and $0$ on the RHS is a zero matrix).
**Proof** Since the sizes of all the matrices are the same, to verify the rules above, we only need to show that the $(i,j)$-entries of the resulting matrix on LHS are equal to the $(i,j)$-entries of the resulting matrix on RHS. In the following, we illustrate the proof of $A + (B+C) = (A+B) + C$:
Let $A = (a_{ij}),$$B = (b_{ij})$ and $C = (c_{ij})$. Then for any $i,j,$
			the $(i,j)$-entry of $A + (B+C)$
			$=$ $a_{ij}\; +$ \[the $(i,j)$-entry of $B+C$\]
			$=$ $a_{ij}$ 