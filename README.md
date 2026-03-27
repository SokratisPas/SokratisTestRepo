# **Name : SokratisTestRepo**
## Example repository for Quantum Information and Analysis course.

### Section 1 

*An example code from Numerical Analysis:*

### Task 1: $LU$ decomposition method
Using the $LU$ method we want to write the given matrix $A$ as the dot product of two matrices (u and l) such as :
$$
A =
\begin{bmatrix}
a_{11} & a_{12} & a_{13} & a_{14} & a_{15} \\
a_{21} & a_{22} & a_{23} & a_{24} & a_{25} \\
a_{31} & a_{32} & a_{33} & a_{34} & a_{35} \\
a_{41} & a_{42} & a_{43} & a_{44} & a_{45} \\
a_{51} & a_{52} & a_{53} & a_{54} & a_{55} 
\end{bmatrix}
=
\begin{bmatrix}
l_{11} & 0 & 0 & 0 & 0 \\
l_{21} & l_{22} & 0 & 0 & 0 \\
l_{31} & l_{32} & l_{33} & 0 & 0 \\
l_{41} & l_{42} & l_{43} & l_{44} & 0 \\
l_{51} & l_{52} & l_{53} & l_{54} & l_{55}
\end{bmatrix}
\cdot
\begin{bmatrix}
1 & u_{12} & u_{13} & u_{14} & u_{15} \\
0 & 1 & u_{23} & u_{24} & u_{25} \\
0 & 0 & 1 & u_{34} & u_{35} \\
0 & 0 & 0 & 1 & u_{45} \\
0 & 0 & 0 & 0 & 1
\end{bmatrix}
$$

In order order to achieve this we first need to calculate the first column of $L$ which is the same as the first column of $A$. Then the first row of $U$ can be calculated by the formula: $$
u_{1i} = \frac{a_{1i}}{l_{11}}
$$
At the end the rest of the values are given by the formulas: 
$$
\text{For } i \ge j: \quad 
l_{ij} = a_{ij} - \sum_{k=1}^{j-1} l_{ik} u_{kj}
$$

$$
\text{For } i < j: \quad 
u_{ij} = \frac{1}{l_{ii}} \left( a_{ij} - \sum_{k=1}^{i-1} l_{ik} u_{kj} \right)
$$

and:
$$
l_{NN} = a_{NN} - \sum_{k=1}^{N-1} l_{Nk} \, u_{kN}
$$
where $N \times N$ are the dimensions of matrix $A$. 

In order to find the $A^{-1}$ we aim to solve 5 linear equations of the form:
$$
A x = b
$$
where the components of the vector $b$ will be specified below.
