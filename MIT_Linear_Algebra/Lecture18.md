## 2.18 determinants
- det(A)  is for square matrices
- det(A) = 0 means A is singular, i.e. not invertible

1. det(I) = 1
2. exchange matrix,det= 1 or -1,depends on number of exchanges
   1. $$\begin{bmatrix} 0&1 \\ 1&0 \end{bmatrix}=-1$$
   2. $$\begin{bmatrix} 0&1 \\ 1&1 \end{bmatrix}=1$$ 
   3. $$\begin{bmatrix} a&b \\ c&d \end{bmatrix}=ad-bc$$
3.  
    1. $$\begin{bmatrix} ta&tb \\ c&d \end{bmatrix}=t \begin{bmatrix}a&b \\ c&d \end{bmatrix}   $$
    2. $$\begin{bmatrix} a+a'&b+b' \\ c&d \end{bmatrix}=\begin{bmatrix}a&b \\ c&d \end{bmatrix}+ \begin{bmatrix}a'&b' \\ c&d \end{bmatrix}$$
4. if two rows are equal, det=0
5. Subtracting a multiple of one row from another **does not** change the determinant
6. row of zeros, det=0
7. triangular matrix, det=product of diagonal elements,product of pivots
$$
\begin{bmatrix} d_1&*&* \\ 0&d_2&* \\0&0&d_3 \end{bmatrix}=d_1d_2d_3
$$ 

8. det A = 0 when A is singular,det A not zero when A is invertible

9. det AB = det A det B,det $A^{-1}$ = $\frac{1}{detA}$, if $AA^{-1}=I$,$detA det A^{-1}=1$
10. $det A = det A^T$
   PROVE:  

## 2.19 Formula for the determinant
1. det I = 1
2. $$\begin{bmatrix} 0&1 \\ 1&0 \end{bmatrix}=-1$$
SO:
$$
\begin{bmatrix} a&b \\ c&d \end{bmatrix}= 
\begin{bmatrix} a&0 \\ c&d \end{bmatrix}+
\begin{bmatrix} 0&b \\ c&d \end{bmatrix}=
$$
$$
\begin{bmatrix} a&0 \\ c&0 \end{bmatrix}+
\begin{bmatrix} a&0 \\ 0&d \end{bmatrix}+
\begin{bmatrix} 0&b \\ c&0 \end{bmatrix}+   
\begin{bmatrix} 0&b \\ 0&d \end{bmatrix}= ad-bc
$$
FOr 3x3 matrix:
$$
\begin{vmatrix} 
a_{11}&a_{12}&a_{13} \\
a_{21}&a_{22}&a_{23} \\
a_{31}&a_{32}&a_{33}
\end{vmatrix}=
$$
$$
\begin{vmatrix}
a_{11}&0&0 \\
0&a_{22}&0 \\
0&0&a_{33}
\end{vmatrix}+
\begin{vmatrix}
a_{11}&0&0 \\
0& 0& a_{23} \\
0&a_{32}&0
\end{vmatrix} +
\begin{vmatrix}
0&a_{12}&0 \\
a_{21}&0&0 \\
0&0&a_{33}
\end{vmatrix}+...
$$

$=a_{11}a_{22}a_{33}-a_{12}a_{23}a_{32}$
(minus means exchange)
$- a_{12}a_{21}a_{33}$.....

SO:
$$
detA = \sum_{n!terms}\pm a_{1\alpha}a_{2\beta}a_{3\gamma}...a_{n\omega}
$$
$
(\alpha ,\beta,\gamma,...,\omega)$ = perm of (1,2,3,...,n)

EXAMPLE:
$$
\begin{vmatrix}
0 & 0 & 1 & 1 \\ 
0 & 1 & 1 & 0 \\
1 & 1 & 0 & 0 \\
1 & 0 & 0 & 1
\end{vmatrix}=
$$
$$
(4,3,2,1)\rightarrow +1,(3,2,1,4)\rightarrow -1
$$
so det = 0,the matrix is singular

### Cofactor expansion(代数余子式展开)
$$
det = a_{11}(a_{22}a_{33}+ a_{23}+a_{32})+a_{12}(...) + a_{13}(...) +...
$$
$$
\begin{vmatrix}
a_{11}&O&O \\
O&a_{22}&a_{23} \\
O&a_{32}&a_{33}
\end{vmatrix}+ 
\begin{vmatrix}
O&a_{12}&O \\
a_{21}&O&a_{23} \\
a_{31}&O&a_{33}
\end{vmatrix}+
\begin{vmatrix}
O&O&a_{13} \\
a_{21}&a_{22}&O \\
a_{31}&a_{32}&O
\end{vmatrix}
$$
Cofactor of $a_{ij}$ is $C_{ij}$ = $(-1)^{i+j}M_{ij}$

$M_{ij}$ is the minor of $a_{ij}$,which is the determinant of the matrix obtained by deleting the i-th row and j-th column of A

## 2.20 Applications of determinants
$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}^{-1}= 
\frac{1}{ad-bc}
\begin{bmatrix}
d & -b \\
-c & a
\end{bmatrix}
$$
d is the Cofactor of a , -b is the Cofactor of B,

SO:
$$
A^{-1} = \frac{1}{detA}C^T
$$
> C: Cofactor matrix

Prove: 
$$
AC^T = (detA)  I
$$
$$
\begin{bmatrix}
a_{11} & ... & a_{1n} \\
... & ... & ... \\
a_{n1} & ... & a_{nn}
\end{bmatrix}
\begin{bmatrix}
c_{11} & ... & c_{n1} \\
... & ... & ... \\
c_{1n} & ... & c_{nn}
\end{bmatrix}= 
\begin{bmatrix}
detA & 0 & 0 \\
0 & detA & 0 \\
0 & 0 & detA
\end{bmatrix}
$$
Qustion: Why is the Cofactor from row two plus row one equal to zero?
- 
$$
Ax=b
$$
$$
x = A^{-1}b = \frac{1}{detA}C^Tb
$$
### Cramer's rule
$$
x_1 = \frac{detB_1}{detA},
x_j = \frac{detB_j}{detA}
$$
$$
B_1 = \begin{bmatrix}
b & (\text{n-1 columns of A})
\end{bmatrix}
$$
expand the determinant along the first column
$$
det B_1 = b_{11}C_{11}+ b_{21}C_{21}+...+b_{n1}C_{n1}
$$
$B_j$ = A with the j-th column replaced by b

EXAMPLE:

det A = volumn of a box
build a 3 by 3 box with sides $a_1,a_2,a_3$
- if A is I , the box is a cube with volume 1,det A = 1
- if A is Q ,a (orthogomal )orthogonal matrix, the box is a cube with volumn $|a_1||a_2||a_3|$,det A = $|a_1||a_2||a_3|$,$Q^TQ=I$
- and other futures of det could be found in this way
- and for 2 by 2 matrix, det is the area of the parallelogram

