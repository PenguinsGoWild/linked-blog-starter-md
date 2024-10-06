**Definition 1.1.6**: A finite set of linear equations in the variables $x_1, x_2,\:\dots,x_n$ is called a system of linear equations (or a linear system)
$$\newcommand{\R}{\mathbb{R}}
\newcommand{\bR}{\bf{R}}
\newcommand{\bA}{\bf{A}}
\newcommand{\I}{\mathit{I}}
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
	b) The system cannot have only one solution.
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

__Definition 2.1.1__: A matrix (plural matrices) is a rectangular array of numbers. The numbers in the array are called entries in the matrix. The size of a matrix is given by $m \times n$ where $m$is the number of rows and $n$ is the number of columns. The $(i,j)$-entry of a matrix is the number which is in the $i$th row and $j$th column of the matrix.

__Definition  2.1.3__: A column matrix (or a _column vector_) is a matrix with only one column. A row matrix (or a _row vector_) is a matrix with only one row.

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

__Definition 2.1.7__: The following are some special types of matrices:
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

__Definition 2.2.1__: Two matrices are said to be equal if they have the same size and their corresponding entries are equal. that is given $A = (a_{ij})_{m \times n}$ and $B = (b_{ij})_{p \times q}$, $A$ is equal to $B$ if $m = p, n = q,$ and $a_{ij}$ = $b_{ij}$ for all $i,j$.

__Definition  2.2.3__: Let $A = (a_{ij})_{m \times n},$ $B = (B_{ij})_{m \times n}$ and $c$ a real constant. We define the matrices $A +B, A - B$ and $cA$ as follows:
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
			$=$ $a_{ij} + [\textnormal{the } (i,j)\textnormal{-entry of } B + C]$
			$=$ $a_{ij} + [b_{ij} + c_{ij}]$
			$=$ $[a_{ij} + b_{ij}] + c_{ij}$
			$=$ $[\textnormal{the } (i,j)\textnormal{-entry of } A + B] + c_{ij}$
			$=$ $\textnormal{the } (i,j)\textnormal{-entry of } (A + B) + C$
			
_Remark 2.2.7_: Let $A_{1},A_{2},\:\dots,A_{k}$ be matrices of the same size. By Associative Law for Matrix Addition, we can write$A_{1},A_{2},\:\dots,A_{k}$ to represent the sum of matrices without using any parentheses to indicate the order of matrix additions.

__Definition 2.2.8 (Matrix Multiplication)__: Let $A = (a_{ij})_{m \times p}$ and $B = (B_{ij})_{p \times n}$ be two matrices. The product $AB$ is defined to be an ${m} \times{n}$ matrix whose $(i,j)$-entry is 
$$
\Huge a_{i1}b_{1j},\:a_{i2}b_{2j},\:\dots,\:+\: a_{ip}b_{pj} = \sum_{k=1}^{p} a_{ik}b_{kj}
$$
for $i = 1,2,\:\dots,m$ and $j = 1,2,\:\dots,n.$

_Remark 2.2.10_: 
1. We can only multiply two matrices $A$ and $B$ (in the manner $AB$) when the number of columns of $A$ is equal to the number of rows of $B$.
2. The matrix multiplication is not commutative, i.e. in general, $AB$ and $BA$ are two different matrices even if the products exits.
3. In view of Part 2 above, it would be ambiguous to say "the multiplication of a matrix $A$ to another matrix $B$" since it could mean $AB$ or $BA$. To distinguish the two, we refer to $AB$ as the *pre-multiplication* of $A$ to $B$ and $BA$ as the _post-multiplication_ of $A$ to $B$.
4. $AB = 0$ does not imply $A = 0$ or $B = 0$
	For example, let $A$ = $\left(\begin{array}{cc}0 & 1 \\ 0 & 1\end{array}\right)$ $B$ = $\left(\begin{array}{cc}1 & 1 \\ 0 & 0\end{array}\right)$. We have $A\ne0$ and $B\ne0$ whilst
$$
	\Huge AB = \left(\begin{array}{cc}0 & 1 \\ 
	0 & 1\end{array}\right)\left(\begin{array}{cc}0 & 1 \\ 
	0 & 1\end{array}\right) = \left(\begin{array}{cc}0 & 0 \\
	0 & 0\end{array}\right) = \mathbf{0}
$$
$$
\newcommand{\0}{\mathbf 0}
$$

**Theorem 2.2.11**
1. **(Associative Law for Matrix Multiplication)**
	If $A, B$ and $C$ are ${m} \times{p}$ , ${p} \times{q}$ and ${q} \times{n}$ matrices respectively, then
$$ \Huge A(BC) = (AB)C $$
2. **(Distributive Laws for Matrix Addition and Multiplication)**
	If $A, B_1$ and $B_2$ are ${m} \times{p}$ , ${p} \times{q}$ and ${q} \times{n}$ matrices respectively, then
$$ \Huge A(B_1 + B_2) = AB_1 + AB_2 $$
	If $A, C_1$ and $C_2$ are ${m} \times{p}$ , ${p} \times{q}$ and ${q} \times{n}$ matrices respectively, then
$$ \Huge A(C_1 + C_2) = AC_1 + AC_2 $$
3. If $A, B$ are ${m} \times{p}$ , ${p} \times{n}$ matrices respectively, and $c$ is a scalar, then
	$$\Huge c(AB) = (cA)B = A(cB).$$
4. If $A$ is an ${m} \times{n}$ matrix, then
	$$\Huge A\mathbf{0}_{n\times q} = \0_{m\times q},\quad \0_{n\times q}A = \0_{m\times q} \quad\textnormal{and}  \quad AI_n = I_mA = A $$

**Proof**: To prove the matrix identities above, we need to check that
	(i) the size of the resulting matrix on the LHS is equal to that on the RHS, and
	(ii) the $(i,j)$-entries of the resulting matrix on the LHS are equal to those on the RHS. 
In the following, we illustrate the proof of $A(B_1+B_2) = AB_1 + AB_2:$
	(i) Since the size of $A$ is ${m} \times{p}$ and the size of $B_1 + B_2) is ${p} \times{n}$, the size of $A(B_1+B_2)$ is ${m} \times{n}$. On the other hand, both the sizes of $AB_1$ and $AB_2$ are ${m} \times{n}$ and hence the size of $AB_1 + AB_2$ is ${m} \times{n}$.
		Thus the sizes of the resulting matrices on both sides of the identity are the same.
	(ii) Let $A = (a_{ij})$, $B_1 = (b_{ij})$ and $B_2 = (b'_{ij})$. For any $i,j$,
		![[Pasted image 20240928214728.png]]
By (i) and (ii), we have proved $\mathbf{A(B_1 + B_2) = AB_1 + AB_2}$

**Definition 2.2.12 (Powers of Square Matrices)** Let $\mathbf{A}$ be a square matrix and $n$ a nonnegative integer. We define $\mathbf{A}^n$ as follows:
![[Pasted image 20241001213132.png]]

![[Pasted image 20240928215222.png]]
![[Pasted image 20240928215754.png]]
![[Pasted image 20240928215818.png]]

_Remark 2.2.17_: Let $A = (a_{ij})_{m \times n}$, $x=\left(\begin{array}{c} x_1\\ x_2\\ \vdots\\x_n\end{array}\right)$ and $b=\left(\begin{array}{c} b_1\\ b_2\\ \vdots\\b_n\end{array}\right)$.
The system of linear equations
$$\Huge\left\{\substack{
a_{11}x_1&+&a_{12}x_2 &+&\:\dots &+& a_{1n}x_n &=& b_1 \\ 
a_{21}x_1&+&a_{22}x_2&+&\:\dots&+&a_{2n}x_n &=& b_2\\
&\vdots &&&&&&\vdots&\\
a_{m1}x_1&+&a_{m2}x_m &+&\:\dots &+& a_{mn}x_n &=& b_m 
}\right.$$
can be written as
$$
\Huge\left(
\begin{array}{cccc}
a_{11} & a_{12} & \dots & a_{1n}\\
a_{21} & a_{22} & \dots & a_{2n}\\
\vdots & \vdots &  & \vdots\\
a_{m1} & a_{m2} & \dots & a_{mn}\\
\end{array}
\right)

\left(
\begin{array}{c}
x_1\\x_2\\\vdots\\x_n
\end{array}
\right)
=
\left(
\begin{array}{c}
b_1\\b_2\\\vdots\\b_m
\end{array}
\right)

$$
or
$$
\Huge\mathbf{Ax=b}
$$
The matrix $A$ is called the *coefficient matrix*, $x$ the *variable matrix* and $b$ the *constant matrix* of the linear system. Furthermore, a solution $x_1 = u _1, x_2 = u_2,\:\dots, x_n = u_n$ to the linear system can be represented by an ${n} \times{1}$ matrix
$$
\Huge u = 
\left(
\begin{array}{c}
u_1\\u_2\\\vdots\\u_n
\end{array}
\right),
$$
i.e. $u$ is said to be a *solution* to the linear system $\mathbf{Ax = b}$ if $\mathbf{Au = b}$.
Let $A = (c_1\quad c_2\quad \dots\quad c_n)$ where $c_j$ is the $j$th column of $A$. The linear system can also be written as
![[Pasted image 20240928221702.png]]![[Pasted image 20240928221707.png]]n
__Definition 2.2.19__: Let $A = (a_{ij})$ be an $m\times n$ matrix. The *transpose* of $A$, denoted by $A^T$ (or $A^t$), is the $n\times m$ matrix whose $(i,j)$-entry is $a_{ji}$. 

_Remark 2.2.21_
1. For a matrix $A$, the rows of $A$ is the columns of $A^T$ and vice versa.
2. In **Definition 2.1.7.6**, a square matrix $A = (a_{ij})$ is called symmetric if $a_{ij} = a_{ji}$ for all $i,j$. Thus a square matrix $A$ is symmetric if and only if $A = A^T$

**Theorem 2.2.22**: Let $A$ be an $m\times n$ matrix.
1. $(A^T)^T = A$.
2. If $B$ is an $m\times n$ matrix, then $(A + B)^T = A^T + B ^T$
3. If $c$ is a scalar, then $(cA)^T = cA^T$.
4. If $B$ is an $n \times p$ matrix, then $(AB)^T = B^TA^T$.
**Proof**: In the following, we illustrate the proof of $(AB)^T = B^TA^T$:
	(i) Since the size of $AB$ is $m\times p$, the size of $(AB)^T$ is $p\times m$. On the other hand, since the size of $B^T$ is $p\times n$ and $A^T$ is $n\times m$, the size of $B^TA^T$ is $p\times m$. Thus the sizes of the resulting matrices on both sides of the identity are the same.
	![[Pasted image 20240928223750.png]]

# Section 2.3 Inverses of Square Matrices
*Discussion 2.3.1*: Let $a,b$ be two real numbers such that $a\ne 0$. Then the solution to the equation $ax=b$ is $x=\frac{b}{a}=a^-1b$. Now, let $A$ and $B$ be two matrices. It is much harder to solve the matrix equation $\mathbf{AX} = \mathbf{B}$ because we do not have "division" for matrices. However, for some square matrices, we can fine their "inverses" which have the similar property as $a_1$ in the computation of the solution to $ax=b$ above

**Definition 2.3.2**: Let $A$ be a square matrix of order $n$. Then $A$ is said to be *invertible* if there exists a square matrix B of order $n$ such that $\mathbf{ AB = I}$ and $\mathbf{BA = I}$. Such a matrix $B$ is called an inverse of $A$. A square matrix is called singular if it has no inverse.

_Remark 2.3.4_
1. **(Cancellation Laws for Matrices)**: Let $A$ be an invertible $m\times m$ matrix.
	(a) If $B_1$ and $B_2$ are $m\times n$ matrices with $AB_1 = AB_2$, then $B_1 = B_2$.
	(b) If $C_1$ and $C_2$ are $n\times m$ matrices with $C_1A = C_2A$, then $C_1 = C_2$
2. If the matrix $A$ in Part 1 is singular, then the Cancellation law may not hold.
	For example, take $A$ $=$ $\left(\begin{array}{cc}1 & 1 \\1 & 0 \\\end{array}\right)$, $B_1$ $=$ $\left(\begin{array}{cc}2 & 0 \\0 & 1 \\\end{array}\right)$, $B_2$ $=$ $\left(\begin{array}{cc}2 & 0 \\1 & 3 \\\end{array}\right)$. Then $AB_1= AB_2=\left(\begin{array}{cc}2 & 0 \\2 & 0 \\\end{array}\right)$ but $B_1\ne B_2$.
**Theorem 2.3.5 (Uniqueness of Inverses)**: If $B$ and $C$ are inverses of a square matrix $A$, then $B = C$.
	**Proof**: Since $B$ is an inverse of A, we have
	$$
	\mathbf{BA = I} \textnormal{ and } \mathbf{AB = I}
	$$
	Also, since $C$ is an inverse of $A$, we have
	$$
	\mathbf{CA = I} \textnormal{ and } \mathbf{AC = I}
	$$
	So $\mathbf{AB = I} \Rightarrow \mathbf{CAB = CI} \rightarrow \mathbf{IB = C}\rightarrow \mathbf{B = C}$.

*Notation 2.3.6* Let $A$ be an invertible matrix. By **Theorem 2.3.5**, we know that there is only one inverse of $A$ and we use the symbol $A^{-1}$ to denote this unique inverse of $A$.

*_Remark  2.3.7_* If we are asked to show that $\mathbf{A^{-1} = B}$  where $A$ and $B$ are square matrices of the same size, what we need to do is to check that $\mathbf{AB = I}$ and $\mathbf{BA = I}$. Actually, in the next section, we shall learn that we only need to check any one of the two conditions. (See **Theorem 2.4.12.**)

**Theorem 2.3.9**: Let $A$, $B$ be two invertible matrices of the same size and $c$ a nonzero scalar. Then 
1. c$\mathbf{A}$ is invertible and $(c\mathbf{A})^{-1}= \frac{1}{c}\mathbf{A}^{-1}$
2. $\mathbf{A}^{-1}$ is invertible and $(\mathbf{A})^{-1}= (\mathbf{A}^{-1})^T$
3. $\mathbf{A}^{-1}$ is invertible and $((\mathbf{A})^{-1})^{-1}= \mathbf{A}^T$
4. $\mathbf{AB}$ is invertible and $(\mathbf{AB})^{-1} = \mathbf{B^{-1}A^{-1}}$

**Proof**: In the following, we only illustrate the proof of Part 2 of the theorem:

To show that $\mathbf{A}^T$ is invertible, we only need to verify that $(\mathbf{A}^{-1})^T$ is the inverse of $\mathbf{A}^T$. Note that
$$
\mathbf{A}^T(\mathbf{A}^{-1})^T = (\mathbf{A}^{-1}\mathbf{A})^T=\mathbf{I}^T=\mathbf{I}\quad\textnormal{and}\quad
(\mathbf{A}^{-1})^T\mathbf{A}^T = (\mathbf{A}\mathbf{A})^T=\mathbf{I}^T=\mathbf{I}
$$
By *_Remark  2.3.7_*, we have proven that $\mathbf{A}^T$ is invertible and $(\mathbf{A}^T)^{-1}=(\mathbf{A}^{-1})^T$.

_Remark 2.3.10_: By **Theorem 2.3.9.4**, if $\mathbf{A_{1},A_{2}},\:\dots,\mathbf{A_{k}}$ are invertible matrices of the same size, then $\mathbf{A_{1}A_{2}}\:\dots\mathbf{A_{k}}$ is invertible and ($\mathbf{A_{1}A_{2}}\:\dots\mathbf{A_{k}})^{-1} = \mathbf{A_{k}}^{-1}\:\dots\mathbf{A_{2}}^{-1}\mathbf{A_{1}}^{-1}$

**Definition 2.3.11 (Negative Powers of Square Matrices)**: Let $A$ be an invertible matrix and $n$ a positive integer. We define $\mathbf{A}^{-n}$ as follows:
$$
\Huge\mathbf{A}^{-n}=(\mathbf{A}^{-1})^n=\underbrace{\mathbf{A^{-1}A^{-1}}\:\ldots\,\mathbf{A^{-1}}}_{n \text{ times}}
$$
_Remark 2.3.13_: Let $A$ be an invertible matrix.
1. $\mathbf{A}^r$$\mathbf{A}^s = \mathbf{A}^{r+s}$ for any integers $r$ and $s$.
2. $\mathbf{A}^n$ is invertible and $(\mathbf{A}^n)^{-1}=\mathbf{A}^{-n}$

# Section 2.4 Elementary Matrices
**Definition 2.4.1**: In **Definition 1.2.4**, **Definition 1.2.6**, **Definition 1.3.1**, **Definition 1.4.1**, _Algorithm 1.4.2_ and _Algorithm 1.4.3_, the concepts of _elementary row operations_, *row equivalent matrices*, _row-echelon forms_, _reduced row-echelon forms_, **Gaussian Elimination**, **Gauss-Jordan Elimination** are defined for augmented matrices. From now on, these terms will also be used for matrices.

**Discussion 2.4.2**: consider the three types of elementary row operations on matrices.
1. **Multiply a row by a constant**:
	Let $\mathbf{A}=\left(\begin{array}{cccc}1 & 0 & 2 & 3\\2 & -1 & 3 & 6\\1 & 4 & 4 & 0\\\end{array}\right)$ and $\mathbf{B}=\left(\begin{array}{cccc}1 & 0 & 2 & 3\\4 & -2 & 6 & 12\\1 & 4 & 4 & 0\\\end{array}\right)$. Note that $B$ is obtained from $A$ by multiplying the second row of $A$ by 2.
	Let :$\mathbf{E_1}=\left(\begin{array}{ccc}1 & 0 & 0 \\0 & 2 & 0 \\0 & 0 & 1 \\\end{array}\right)$. Observe that 
		$\mathbf{E_1A}=\left(\begin{array}{ccc}1 & 0 & 0 \\0 & 2 & 0 \\0 & 0 & 1 \\\end{array}\right)\left(\begin{array}{cccc}1 & 0 & 2 & 3\\2 & -1 & 3 & 6\\1 & 4 & 4 & 0\\\end{array}\right) =\left(\begin{array}{cccc}1 & 0 & 2 & 3\\4 & -2 & 6 & 12\\1 & 4 & 4 & 0\\\end{array}\right)=\mathbf{B}$ 
![[Pasted image 20240930000128.png]]
2. **Interchange two rows**:
	Let $\mathbf{A}=\left(\begin{array}{cccc}1 & 0 & 2 & 3\\2 & -1 & 3 & 6\\1 & 4 & 4 & 0\\\end{array}\right)$ and $\mathbf{B}=\left(\begin{array}{cccc}1 & 0 & 2 & 3\\1 & 4 & 4 & 0\\2 & -1 & 3 & 6\\\end{array}\right)$. Note that $B$ is obtained from $A$ by interchanging the second and third rows of $A$.
	Let :$\mathbf{E_1}=\left(\begin{array}{ccc}1 & 0 & 0 \\0 & 0 & 1 \\0 & 1 & 0 \\\end{array}\right)$. Observe that 
		$\mathbf{E_2A}=\left(\begin{array}{ccc}1 & 0 & 0 \\0 & 0 & 1 \\0 & 1 & 0 \\\end{array}\right)\left(\begin{array}{cccc}1 & 0 & 2 & 3\\2 & -1 & 3 & 6\\1 & 4 & 4 & 0\\\end{array}\right) =\left(\begin{array}{cccc}1 & 0 & 2 & 3\\1 & 4 & 4 & 0\\2 & -1 & 3 & 6\\\end{array}\right)=\mathbf{B}$ 
	In general, let $A$ be an ${m} \times{n}$ matrix and
![[Pasted image 20240930000526.png]]
3. **Add a multiple of a row to another row:**
Let $\mathbf{A}=\left(\begin{array}{cccc}1 & 0 & 2 & 3\\2 & -1 & 3 & 6\\1 & 4 & 4 & 0\\\end{array}\right)$ and $\mathbf{B}=\left(\begin{array}{cccc}1 & 0 & 2 & 3\\2 & -1 & 3 & 6\\3 & 4 & 8 & 6\\\end{array}\right)$. Note that $B$ is obtained from $A$ by adding 2 times of the first row of $A$ to the third row.
	Let :$\mathbf{E_1}=\left(\begin{array}{ccc}1 & 0 & 0 \\0 & 1 & 0 \\2 & 0 & 1 \\\end{array}\right)$. Observe that 
		$\mathbf{E_3A}=\left(\begin{array}{ccc}1 & 0 & 0 \\0 & 1 & 0 \\2 & 0 & 1 \\\end{array}\right)\left(\begin{array}{cccc}1 & 0 & 2 & 3\\2 & -1 & 3 & 6\\1 & 4 & 4 & 0\\\end{array}\right) =\left(\begin{array}{cccc}1 & 0 & 2 & 3\\2 & -1 & 3 & 6\\3 & 4 & 8 & 6\\\end{array}\right)=\mathbf{B}$ 
	In general, let $A$ be an ${m} \times{n}$ matrix and
![[Pasted image 20240930000914.png]]![[Pasted image 20240930000924.png]]
	be a square matrix of order $m$ where all entries not specified are zero. Then $\mathbf{EA}$ is the matrix which can be obtained from $A$ by adding $k$ times of the $i$th row of $A$ to the $j$th row.
	The matrix $\mathbf{E}$ is invertible and 
	![[Pasted image 20240930001036.png]]
	corresponds to the row operation of adding $-k$ times of the $i$th row of a matrix to the $j$th row.

**Definition 2.4.3**: A square matrix is called an *elementary matrix* if it can obtained from an identity matrix by performing a single elementary row operation.

_Remark 2.4.4_
1. The matrices $\mathbf{E}$ described in *Discussion 2.4.2* are _elementary matrix_ and every _elementary matrix_ is of one of these three types.
2. All _elementary matrix_ are invertible and their inverses are also _elementary matrix_.
![[Pasted image 20240930001452.png]]

_Remark 2.4.6 (Proof of Theorem 1.2.7)_: Theorem 1.2.7 states that if augmented matrices of two systems of linear equation are row equivalent, then the two systems have the same set of solutions. Following _Remark 1.2.9_, we need to show the following: Let $(\mathbf{A} | \mathbf{b})$ and $(\mathbf{C} | \mathbf{d})$ be two augmented matrices such that $(\mathbf{C} | \mathbf{d})$ can be obtained from $(\mathbf{A} | \mathbf{b})$ by an elementary row operation. Then the linear system $\mathbf{Ax = b}$ and $\mathbf{Cx = d}$ have the same set of solutions.
__Proof__: By _Discussion 2.4.2_, there exists an _elementary matrix_ $\mathbf{E}$ such that
$$\Huge(\mathbf{C} | \mathbf{d})=\mathbf{E}(\mathbf{A} | \mathbf{b})=(\mathbf{EA} | \mathbf{Eb}),$$
i.e. $\mathbf{C} = \mathbf{EA}$ and $\mathbf{d}=\mathbf{Eb}$.
If $u$ is a solution to $\mathbf{Ax = b}$, then
$$\Huge\mathbf{Au = b} \Rightarrow \mathbf{EAu = Eb} \Rightarrow \mathbf{Cu = d}$$
and hence $u$ is a solution to $\mathbf{Cx = d}$.
If $v$ is a solution to $\mathbf{Cx=d}$, then
$$
\Huge\mathbf{Cv=d}\Rightarrow\mathbf{EAv=Eb}\Rightarrow\mathbf{E^{-1}Eb}\Rightarrow\mathbf{IAv=Ib}\Rightarrow\mathbf{Av=b}
$$
and hence $v$ is a solution to $\mathbf{Ax = b}$.
So we have shown that the linear systems $\mathbf{Ax = b}$ and $\mathbf{Cx = d}$ have the same set of solutions.

*Theorem 2.4.7* (This theorem is part of our main theorem on invertible matrices, see _Theorem 6.1.8_): If $A$ is a square matrix, then the following statements are equivalent:
1. $A$ is invertible.
2. The linear system $\mathbf{Ax = \0}$ has only the trivial solution.
3. The _reduced row-echelon form_ of $A$ is an identity matrix.
4. $A$ can be expressed as a product of _elementary matrices_.

**Proof**
$1\Rightarrow2:$ If $A$ is invertible, then $\mathbf{Ax = \0}$ implies
$$
\Huge\mathbf{x = \I x = A^{-1}Ax=A^{-1}\0=\0}
$$
	and hence the system has only the trivial solution $\mathbf{x=0}$
![[Pasted image 20240930003557.png]]
![[Pasted image 20240930004127.png]]
![[Pasted image 20240930004137.png]]
_Remark 2.4.10_: _Theorem 2.4.7_ tells us that a square matrix is invertible if and only if its _reduced row-echelon form_ is an identity matrix. this can be used to check whether a square matrix is invertible. Actually, to check whether a square matrix is invertible, we only need to reduce the matrix to a _row-echelon form_. If the _row-echelon form_ of a square matrix has no zero row, the matrix is invertible; otherwise, the matrix is singular.

_Theorem 2.4.12_: Let $A$, $B$ be square matrices of the same size. If $\mathbf{AB} = \I$, then $\mathbf{A},\mathbf{B}$ are both invertible,
$$
\Huge\mathbf{A^{-1} = B,\; B^{-1} = A\; \textnormal{ and }\: BA = \I}
$$
![[Pasted image 20240930004813.png]]

_Theorem 2.4.14_: Let $A$ and $B$ be two square matrices of the same order. If $A$ is singular, then $\mathbf{AB}$ and $\mathbf{BA}$ are singular.

_Discussion 2.4.15_: From *Discussion 2.4.2*, we learn that to pre-multiply an _elementary matrix_ to a matrix $\mathbf{A}$ is equivalent to doing an _elementary row operations_ on $\mathbf{A}$. What will happen if we post-multiply an _elementary matrix_ to a matrix?
Let $\mathbf{A}$ be a ${p} \times{m}$ matrix.
1. If $\mathbf{E}$ is the _elementary matrix_ defined in _Discussion 2.4.2.1_, then $\mathbf{AE}$ is the matrix which can be obtained from $\mathbf{A}$ by multiplying the $i$th column of $\mathbf{A}$ by :$k$.
2. If $\mathbf{E}$ is the _elementary matrix_ defined in _Discussion 2.4.2.2_, then $\mathbf{AE}$ is the matrix which can be obtained from $\mathbf{A}$ by interchanging the $i$th and $j$th columns of $\mathbf{A}$.
3. If $\mathbf{E}$ is the _elementary matrix_ defined in _Discussion 2.4.2.3_, then $\mathbf{AE}$ is the matrix which can be obtained from $\mathbf{A}$ by adding $k$ times the $j$th column of $\mathbf{A}$ to the $i$th column.
The three operations on matrices described above are called _elementary column_ operations.

# Section 2.5 Determinants
_Discussion 2.5.1_: By Example 2.4.11.2, we know that a ${2} \times{2}$ matrix $\left(\begin{array}{cc}a & b \\b & d \\\end{array}\right)$ is invertible if and only if $ad-bc\ne 0$. Actually, we have a similar formula to determine whether a square matrix of higher order is invertible. The formula involves a quantity called "determinant". Unfortunately, there is no easy way to define it. In the following, we use an inductive approach to define this quantity.

**Definition 2.5.2**: Let $\mathbf{A} = (a_{ij})$ be an ${n} \times{n}$ matrix. Let $\mathbf{M_{ij}}$ be an $(n-1) \times (n-1)$ matrix obtained from $\mathbf{A}$ by deleting the $i$th row and the $j$th column. Then the *determinant* of $\mathbf{A}$ is defined as
$$det(\mathbf{A}) = \Huge\left\{ \substack{
&a_{11}& &&&&&&&\quad\textnormal{if } n = 1\\ &a_{11}&A_{11}&\:+\:&a_{12}A_{12}&\:+\:&\dots&\:+\:&a_{1n}A_{1n}& \quad\textnormal{if } n = 1
}\right.$$
where
$$
\Huge{A_{ij} = (-1)^{i+j}det(\mathbf{M_{ij}}).}
$$
The number of $A_{ij}$ is called the $(i,j)$-cofactor of $\mathbf{A}$.
The way we defined "determinant" above is known as the cofactor expansion (see also _Theorem 2.5.6_).
![[Pasted image 20240930011550.png]]
![[Pasted image 20240930011638.png]]
*Theorem 2.5.6 (Cofactor Expansions)*: For an ${n} \times{n}$ matrix $\mathbf{A} = (a_{ij})$, det($\mathbf{A}$) can be expressed as a cofactor expansion using any *row* or *column* of $\mathbf{A}$:
![[Pasted image 20240930011914.png]]

_Theorem 2.5.8_: If $\mathbf{A}$ is a triangular matrix, then the determinant of $\mathbf{A}$ is equal to the product of the diagonal entries of $\mathbf{A}$.

**Proof**: We shall prove the following assertion by using mathematical induction on $n$.
![[Pasted image 20240930012139.png]]
![[Pasted image 20240930012149.png]]
![[Pasted image 20240930012757.png]]

**Theorem 2.5.12**
1. The determinant of a square matrix with two identical rows is zero.
2. The determinant of a square matrix with two identical columns is zero.

![[Pasted image 20240930013209.png]]
![[Pasted image 20240930013219.png]]
![[Pasted image 20240930013226.png]]
*Theorem 2.5.15* Let $\mathbf{A}$ be a square matrix.
1. If $\mathbf{B}$ is a square matrix obtained from $\mathbf{A}$ by multiplying one row of $\mathbf{A}$ by a constant $k$, then det($\mathbf{B}$) $=k\,$det($\mathbf{A}$).
2. If $\mathbf{B}$ is a square matrix obtained from $\mathbf{A}$ by interchanging two row of $\mathbf{A}$, then           det($\mathbf{B}$) $=-$det($\mathbf{A}$). 
3. If $\mathbf{B}$ is a square matrix obtained from $\mathbf{A}$ by adding a multiple of one row of $\mathbf{A}$ to another row, then det($\mathbf{B}$) $=\;$det($\mathbf{A}$). 
4. Let $\mathbf{E}$ be an _elementary matrix_ of the same size as $\mathbf{A}$. Then det($\mathbf{EA}$) $=\;$det($\mathbf{E}$)det($\mathbf{A}$). 
*Proof*: In the following, we only illustrate the proof of Part 3: Let $\mathbf{A} = (a_{ij})$ be a square matrix of order $n$ and $\mathbf{B}$ a square matrix obtained from $\mathbf{A}$ by adding $k$ times of the $i$th row of $\mathbf{A}$ to the $j$th row. Then by expanding along the $j$th row of $\mathbf{B}$,
![[Pasted image 20240930014432.png]]

_Remark 2.5.16_: By *Theorem 2.5.15*, we can use elementary row operations to transform a square matrix to a triangular matrix and then by *Theorem 2.5.8*, compute the determinant accordingly.
![[Pasted image 20240930015800.png]]
_Remark 2.5.21_: By *Theorem 2.5.19*, we can use the determinant to check whether a given square matrix is invertible. However, for matrices of higher order, to compute determinants may not be easier than the method discussed in _Remark 2.4.10_

![[Pasted image 20240930020226.png]]
**Definition 2.5.24**: Let $\mathbf{A}$ be a square matrix of order $n$. Then the (classical) adjoint of $\mathbf{A}$ is the ${n} \times{n}$ matrix
![[Pasted image 20240930020724.png]]

_Theorem 2.5.25_: Let $\mathbf{A}$ be a square matrix. If $\mathbf{A}$ is invertible, then
![[Pasted image 20240930020806.png]]

*Theorem 2.5.27 (Cramer's Rule)*: Suppose $\mathbf{Ax = b}$ is a linear system where $\mathbf{A}$ is an ${n} \times{n}$ matrix. Let $\mathbf{A_i}$ be the matrix obtained from $\mathbf{A}$ by replacing the $i$th column of $\mathbf{A}$ by $\mathbf{b}$. If $\mathbf{A}$ is invertible, then the system has only one solution.
![[Pasted image 20240930023239.png]]
![[Pasted image 20240930023244.png]]
![[Pasted image 20240930023654.png]]
![[Pasted image 20240930023700.png]]

# Chapter 3
# Vector Spaces
