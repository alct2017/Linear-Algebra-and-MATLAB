# Vectors and Matrices

## Vectors

### Column Vectors and Row Vectors

**Column vector** is, in the simplest way, components written in a cloumn.

$$\text{Column Vector }\vec{v}=
\begin{bmatrix}
a_1\\a_2\\\vdots\\a_n
\end{bmatrix}$$

In order to save space, column vector is also written as
$\vec{v}=\begin{pmatrix}
    a_1,a_2,\dots,a_n
\end{pmatrix}$.

**Row vector** is similar as column vector, that is, components in row.

$$\text{Row Vector }\vec{v}=
\begin{bmatrix}
    a_1&a_2&\dots&a_n
\end{bmatrix}$$

or written as $\vec{v}=\begin{pmatrix}
    a_1&a_2&\dots&a_n
\end{pmatrix}$ ,the only difference with column vector is there no commas between components.

### Linear Combination

There are two basic operations in vectors:

$$\text{Vector Addition }
\vec{v}+\vec{w}=
\begin{bmatrix}
    v_1\\v_2
\end{bmatrix}+
\begin{bmatrix}
    w_1\\w_2
\end{bmatrix}=
\begin{bmatrix}
    v_1+w_1\\v_2+w_2
\end{bmatrix}$$

$$\text{Scalar Multiplication }
t\times\vec{v}=
t\times\begin{bmatrix}
    v_1\\v_2
\end{bmatrix}=
\begin{bmatrix}
    tv_1\\tv_2
\end{bmatrix}$$

And one of the most important concept in linear algebra, **linear combination** is based on that.

$$\text{Linear Combination of }\vec{v}\text{ and }\vec{w}\text{ is all }c\vec{v}+d\vec{w}\\\text{ for any combination of }c\text{ and }d$$

The definition of linear combination can be expanded to more than 2 vectors.

## Matrices

The matrix comes from linear equations. Suppose we have linear equation
$$\begin{gathered}
    a_{11}x_1+a_{12}x_2+a_{13}x_3=b_1\\
    a_{21}x_1+a_{22}x_2+a_{23}x_3=b_2\\
    a_{31}x_1+a_{32}x_2+a_{33}x_3=b_3
    \tag*{$(*)$}
\end{gathered}  $$
for saving space, the equation can be written as a vector equation
$$x_1\begin{pmatrix}
    a_{11}\\a_{21}\\a_{31}
\end{pmatrix}+
x_2\begin{pmatrix}
    a_{12}\\a_{22}\\a_{32}
\end{pmatrix}+
x_3\begin{pmatrix}
    a_{13}\\a_{23}\\a_{33}
\end{pmatrix}=
\begin{pmatrix}
    b_1\\b_2\\b_3
\end{pmatrix}
$$
we can even write as
$$\begin{pmatrix}
    a_{11}&a_{12}&a_{13}\\
    a_{21}&a_{22}&a_{23}\\
    a_{31}&a_{32}&a_{33}\\
\end{pmatrix}
\begin{pmatrix}
    x_1\\x_2\\x_3
\end{pmatrix}=
\begin{pmatrix}
    b_1\\b_2\\b_3
\end{pmatrix}$$
$A=\begin{pmatrix}
    a_{11}&a_{12}&a_{13}\\
    a_{21}&a_{22}&a_{23}\\
    a_{31}&a_{32}&a_{33}\\
\end{pmatrix}$ is a matrix, you can see it as the combination of three column vector

So the equation $(*)$ can be abbreviated as
$$A\vec{x}=\vec{b}$$
This is one of the most important equation in linear algebra. Whether the equation has a solution and how to solve it is a major topic in linear algebra.

### Matrix Operation

Matrices can add and multipled by scalar as vectors. It can also be multipled by vector as before. But the most important operation is multipled by matrix.

Let's say we have equations:

$$
    A\begin{pmatrix}b_{11}\\b_{21}\\b_{31}\end{pmatrix}
    =\begin{pmatrix}c_{11}\\c_{21}\\c_{31}\end{pmatrix}\quad
    A\begin{pmatrix}b_{12}\\b_{22}\\b_{32}\end{pmatrix}
    =\begin{pmatrix}c_{12}\\c_{22}\\c_{32}\end{pmatrix}$$

as before we can write it like

$$A
\begin{pmatrix}
    b_{11}&b_{21}\\
    b_{21}&b_{22}\\
    b_{31}&b_{32}
\end{pmatrix}=
\begin{pmatrix}
    c_{11}&c_{21}\\
    c_{21}&c_{22}\\
    c_{31}&c_{32}
\end{pmatrix}$$

that is

$$\begin{pmatrix}
    a_{11}&a_{12}&a_{13}\\
    a_{21}&a_{22}&a_{23}\\
    a_{31}&a_{32}&a_{33}\\
\end{pmatrix}
\begin{pmatrix}
    b_{11}&b_{21}\\
    b_{21}&b_{22}\\
    b_{31}&b_{32}
\end{pmatrix}=
\begin{pmatrix}
    c_{11}&c_{21}\\
    c_{21}&c_{22}\\
    c_{31}&c_{32}
\end{pmatrix}$$

Since the abbreviated formula must have the same meaning as origional one, we can conclude the princple of matrix multiplication. There are 4 ways to understand it:

$\text{1.the }(i,j)\text{ entry of }C\text{ is (} i\text{th row of }A\text{)}\cdot\text{(}j\text{th column of }B)$

Since the origional formula is
$$\begin{gathered}
    a_{11}b_{11}+a_{12}b_{21}+a_{13}b_{31}=c_{11}\\
    a_{21}b_{11}+a_{22}b_{21}+a_{23}b_{31}=c_{21}\\
    \dots
\end{gathered}$$
we got
$$\begin{aligned}
    c_{ij}&=\sum_{k=1}^{n}a_{ik}b_{kj}\\
    &=\text{(} i\text{th row of }A\text{)}\cdot\text{(}j\text{th column of }B)
\end{aligned}
$$

$\text{2.the }i\text{th row of }C\text{ is (} i\text{th row of }A\text{)}\cdot B$

$\text{3.the }j\text{th column of }C\text{ is }A\cdot\text{(}j\text{th column of }B)$

$\text{4.}C\text{ is the sum of all (} i\text{th column of }A\text{)}\cdot\text{(}j\text{th row of }B)$

### The Laws of Matrix Operations

$$\begin{aligned}
    A+B&=B+A&\text{(commutative law)}\\
    c(A+B)&=cA+cB&\text{(distributive law)}\\
    A+(B+C)&=(A+B)+C&\text{(associative law)}\\
    \\
    AB&\not =BA&\text{(no commutative law)}\\
    A(B+C)&=AB+AC&\text{(distributive law from the left)}\\
    (A+B)C&=AC+BC&\text{(distributive law from the right)}\\
    A(BC)&=(AB)C&\text{(associative law)}\\
    \\
    (A^p)(A^q)&=A^{p+q}\\
    (A^p)^q&=A^{pq}
\end{aligned}$$

### Block Matrix and Block Multiplication

The entry of a matrix can be other matrices, for exmple, let's say
$$A=
\begin{pmatrix}
    a_{11}&a_{12}&a_{13}\\
    a_{21}&a_{22}&a_{23}\\
    a_{31}&a_{32}&a_{33}
\end{pmatrix}\quad
B=\begin{pmatrix}
    b_1&b_2&b_3
\end{pmatrix}\quad
C=c$$
then we can say
$$S=
\begin{pmatrix}
    a_{11}&a_{12}&a_{13}&b_{1}\\
    a_{21}&a_{22}&a_{23}&b_{2}\\
    a_{31}&a_{32}&a_{33}&b_{3}\\
    b_1&b_2&b_3&c
\end{pmatrix}
=\begin{pmatrix}
    A&B^T\\
    B&C
\end{pmatrix}$$

If the block's size agree, block matrix can multiple
$$\begin{pmatrix}
    A_{11}&A_{12}\\A_{21}&A_{22}
\end{pmatrix}
\begin{pmatrix}
    B_{11}\\B_{21}
\end{pmatrix}
=\begin{pmatrix}
    A_{11}B_{11}+A_{12}B_{21}\\
    A_{21}B_{11}+A_{22}B_{21}
\end{pmatrix}$$
