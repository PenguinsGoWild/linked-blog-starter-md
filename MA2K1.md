Consistent (One solution) -->> All columns on the left are pivot columns entries
Consistent (Infinitely many solution) -->> At least one column on the left are non pivot columns
Inconsistent (No solution) -->> At least one column on the right is a pivot column

When considering a more complicated linear system in augmented form/row echelon form, use branch diagram to consider if the system is consistent or inconsistent.

Presuming we have a linear system with 3 variables, x, y, z, and 4 rows,

xingyao@u.nus.edu


R^2 - Zero Vector, Line Passing through origin, R^2
R^3 - Zero Vector, Line Passing through origin, R^3, Plane passing through origin

Linear Independence: The list v1...vn is independent if a1v1+a2v2+....+anvn = 0 implies that all ai = 0
If redundant, is linearly dependent, else is linearly independent

If a set contains the zero vector, then it is linearly dependant. 
Growing a linearly independent et by adding in a new vector that is not a linear combination of the existing vectors in the set.
$$
\newcommand{\R}{\mathbb{R}}
$$
Line on $xy$-plane can be represented by:
		$ax + by = c$
		where $a, b \ne 0$
This is known as a linear equation.


**Definition 1.1.12** A linear equation in $n$ variables $x_1,\; x_2,\; \dots,\;x_n$ has the form:
		$a_1x_1+a_2x_2+\dots+a_nx_n=b$

where $a_1, a_2,\:\dots,a_n \in \R$ 
The variables in a linear equation are also called the unknowns.
We do not need to assume $a_1,a_2,\:\dots,a_n$ are not all zero, as if they are all zero it is a zero equation. A linear equation is called a nonzero equation if it is not a zero equation.

The linear equation $ax+by+cz=d$, where $a, b, c, d$ are constants and $a, b, c$ are not all zero, represents a plane in the three dimensions space. For example, $z = 0$ (i.e. $0x + 0 + z = 0$) is the $xy$-plane contained inside the $xyz$-space.

**Definition 1.1.4** Given $n$ real numbers $s_1,s_2,\:\dots,s_n,$ we say that $x_1 = s_1, x_2=s_2,\:\dots, x_n = s_n$ is a solution to a linear equation $a_1x_1 + a_2x_2 +\dots+a_nx_n = b$ if the equation is satisfied when we substitute the values into the equation accordingly. The set of all solutions to the equation is called the solution set of the equation and an expression that gives us all these solutions is called a general solution for the equation.

1. Consider the linear equation $4x - 2y = 1$. It has a general solution
$$\Huge\left\{\substack{x & = & t \\ y & = & 2t & - \frac{1}{4}}\right.\;\; \small\textnormal{Where t is an arbitrary parameter.}$$
The equation also has another general solution
$$\Huge\left\{\substack{x & = & \frac{1}{2}s & + \frac{1}{4} \\ y & = & s }\right.\;\; \small\textnormal{Where s is an arbitrary parameter.}$$
Though the two general solutions above look different, they give us the same set of solutions including
$$\Huge\left\{\substack{x & = & 1 \\ y & = & 1.5}\right.\quad \left\{\substack{x & = & 1.5 \\ y & = & 2.5}\right.\quad\left\{\substack{x & = & -1 \\ y & = & -2.5}\right.$$
2. Consider the equation $x_1-4x_2+7x_3=5$. It has the general solution 
$$\Huge\left\{\substack{&x  &= & 5 & + 4s - 7t \\ &y  &= &  s \\ &z  &=&  t }\right.\;\; \small\textnormal{Where t, s are arbitrary parameters.}$$

# 3. (Geometrical Interpretation)
a) In the $xy$-plane, solutions to the equation $x+y=1$ are points
$$(x,y) = (1-s,2)$$
where $s \in \R$. These points forma a line.

b) In the $xyz$-space, solutions to the equation $x+y = 1 (\textnormal{i.e. } x + y + 0z = 1)$ are points 
$$(x,y,z) = (1-s,s,t)$$
where $s,t\in\R$. These points form a plane.

4. Consider the zero equation $0x_1+0x_2+\:\dots+0x_n=0$. Any values of $x_1,x_2,\:\dots,x_n$ give us a solution. Thus the general solution is $x_1=t_1,x_2=t_2,\:\dots,x_n=t_n$ where $t_1,t_2,\:\dots,t_n$ are arbitrary parameters.
5. For an equation $0x_1+0x_2+\:\dots+0x_n=b$, where b is nonzero, any values of $x_1,x_2,\:\dots,x_n$ does not satisfy the equation and hence the equation has no solution.

**Definition 1.1.6** A finite set of linear equations in the variables $x_1,x_2,\:\dots,x_n$ is called a system of linear equations (or a linear system):

$$\Huge\left\{\substack{a_{11}x_1&+&a_{12}x_2 &+&\:\dots &+& a_{1n}x_n &=& b_1 \\ a_{21}x_1&+&a_{22}x_2&+&\:\dots&+&a_{2n}x_n &=& b_2\\&\vdots &&&&&&\vdots&\\a_{m1}x_1&+&a_{m2}x_m &+&\:\dots &+& a_{mn}x_n &=& b_m }\right.$$
where $a_{11},a_{12},\:\dots,a_{mn}$ and $b_{11},b_{12},\:\dots,b_{m}$ are real constants. If all $a_{11},a_{12},\:\dots,a_{mn}$ and $b_{11},b_{12},\:\dots,b_{m}$ are zero, the system is called a _zero system_. A linear system is called a nonzero system if it is not a zero system.
Given $n$ real numbers $s_1,s_2,\:\dots,s_n$, we say that $x_1 = s_1, x_2 = s_2,\:\dots,x_n=s_n$ is a solution to the system if $x_1 = s_1, x_2 = s_2,\:\dots,x_n=s_n$ is a solution to every equation in the system. The set of all solutions to the system is called the solution set of the system and an expression that gives us all these solutions is called a general solution for the system.
**Definition 1.1.9** A system of linear equations that has no solution is said to be inconsistent. A system that has at least one solution is called consistent.

_Remark 1.1.10_ Every system of linear equations has either no solution, only one solution, or infinitely many solutions.

1. In the $xy$-plane, the two equations in the system
$$\Huge\left\{\substack{a_1x+b_1y=c_1\quad(L_1)\\a_2x+b_2y=c_2,\quad(L_2)}\right.$$
Where $a_1,b_1$ are not both zero and $a_2,b_2$ are not both zero, represent two straight lines. A solution to the system is a point of intersection of the two lines.
(a) The system has no solution if and only if $L_1$ and $L_2$ are different but parallel lines.
(b) The system has only one solution if and only if $L_1$ and $L_2$ are not parallel lines.
(c) The system has infinitely many solutions if and only if $L_1$ and $L_2$ are the same line.
Note that the two lines $L_1$ and $L_2$ are parallel if and only if $a_1 = ka_2$ and $b_1=kb_2$ for a nonzero real number $k$.
2. In the $xyz$-space, the two equations in the system

$$\Huge\left\{\substack{a_1x&+b_1y+c_1z&=&d_1\quad(P_1)\\a_2x&+b_2y+c_2z&=&d_2,\quad(P_2)}\right.$$
where $a_1,b_1,c_1$ are not all zero and $a_2,b_2,c_2$ are not all zero, represents two planes. A solution to the system is a point of intersection of the two planes.
(a) The system has no solution if and only if $P_1$ and $P_2$ are different but parallel palnes.
(b) The system cannot have only one solution
(c) The system has infinitely many solutions if and only if either $P_1$ and $P_2$ intersect at a line or $P_1$ and $P_2$ are the same plane.
Note that the two planes $P_1$ and $P_2$ are parallel if and only if $a_1 = ka_2, b_1=kb_2$ and $c_1=kc_2$ for a nonzero real number $k$.

# Elementary Row Operations
$$\Huge\left\{\substack{a_{11}x_1&+&a_{12}x_2 &+&\:\dots &+& a_{1n}x_n &=& b_1 \\ a_{21}x_1&+&a_{22}x_2&+&\:\dots&+&a_{2n}x_n &=& b_2\\&\vdots &&&&&&\vdots&\\a_{m1}x_1&+&a_{m2}x_m &+&\:\dots &+& a_{mn}x_n &=& b_m }\right.\;\; \small\textnormal{Where s is an arbitrary parameter.}$$
