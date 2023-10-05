## Solution Sets


Example: Consider $A\vec{x} = \vec{b}$, when 

$$A=\begin{bmatrix}1 & -3 \\ 2 & -6 \end{bmatrix}, \quad \vec{x}=\begin{bmatrix} x_1 \\ x_2\end{bmatrix}, \quad \vec{b}=\begin{bmatrix}-3 \\ -6 \end{bmatrix}$$
 The general solution of $A\vec{x} = \vec{b}$ is given by 
 $$\vec{x}=\begin{bmatrix} x_1 \\ x_2\end{bmatrix} = \begin{bmatrix} -3 \\ 0\end{bmatrix} + x_2\begin{bmatrix} 3 \\ 1\end{bmatrix}$$

 Since the first term is a solution of $A\vec{x} = \vec{b}$, and the second term is  the solution of $A\vec{x} = 0.$

 The solution set of $A\vec{x} = 0$ is given by vectors who originate from the origin and lie on the line $y=x/3$. Since there is only one variable ($x_2$), the solution set is a line. If there were two variables, it would be a plane.

 ## Linear Independence
 #### Def. A set of vectors ${\vec{v_1}, \vec{v_2}, ..., \vec{v_k}}$ in $\mathbb{R}^n$ is linearaly independent if the vector equation ${x_1\vec{v_1}+x_2\vec{v_2}+...+x_k\vec{v_k}=\vec{0}}$ only has a single trivial solution (when every coefficient x is 0). If a non-trivial solution exists, we say that the set of vectors is linearly dependent.

In other words, in order for the vector equation to be true, all coefficients MUST be zero.

Note that any set that contains the zero vector is clearly linearly dependent, since its coefficient can be nonzero while every other coefficient is zero.

\
__Example:__ consider the set $${\vec{v_1}=\begin{bmatrix} 1 \\ 2 \\ 1\end{bmatrix}}, \vec{v_2}=\begin{bmatrix} -1 \\ -2 \\ -1\end{bmatrix}, \vec{v_3}=\begin{bmatrix} 0 \\ 1 \\ 3\end{bmatrix}, \vec{v_4}=\begin{bmatrix} -2 \\ 0 \\ 1\end{bmatrix}$$
We can see that it is linearly dependent because $\vec{v_1} + \vec{v_2} = 0$.

Note that ${\vec{v_1}, \vec{v_2}, ..., \vec{v_k}}$ in $\mathbb{R}^n$ is linearaly dependent if and only if the following homogenous system $\begin{bmatrix}\vec{v_1} & \vec{v_2} & ... & \vec{v_k}\end{bmatrix}\begin{bmatrix} x_1 \\ ... \\ x_k\end{bmatrix} = \vec{0}$ has non-trivial solutions. (Thus the system has infinitely many solutions).

\
__Example:__ determine when the set of vectors ${\vec{v_1}, \vec{v_2},\vec{v_3}}$ is linearly independent, where 

$${\vec{v_1}=\begin{bmatrix} 2\\ 1 \\ 2 \\ 3\end{bmatrix}}, \vec{v_2}=\begin{bmatrix} 1 \\ 0 \\ 4 \\ a\end{bmatrix}, \vec{v_3}=\begin{bmatrix} 1 \\ b \\ 0 \\ 0 \end{bmatrix}$$

where $a$, $b$ are constants.

<u> Solution</u> Let $A = \begin{bmatrix} \vec{v_1} & \vec{v_2} & \vec{v_3}\end{bmatrix}$. 

$$A = \begin{bmatrix} 2 & 1 & 1 \end{bmatrix}$$