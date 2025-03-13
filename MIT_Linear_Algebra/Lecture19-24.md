
## 2.21 Eigenvalues and eigenvectors
$$ 
Ax = \lambda x
$$
- if A is singular , $\lambda = 0$

What are x's and $\lambda$'s for projection matrix?
- any x in plane : $Px = x$, $\lambda = 1$
- any x perpendicular to plane: $Px = 0$, $\lambda = 0$

EXAMPLE: 
$$
A=
\begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}
$$
1. 
$$
x = 
\begin{bmatrix}
1 \\
1
\end{bmatrix},Ax = 
\begin{bmatrix}
1 \\
1
\end{bmatrix},
\lambda = 1$$
2.
$$
x =
\begin{bmatrix}
1 \\
-1
\end{bmatrix},
Ax =
\begin{bmatrix}
-1 \\
1
\end{bmatrix},
\lambda = -1
$$
Fact : sum of eigenvalues = trace of A, product of eigenvalues = det A

How to solve $Ax = \lambda x$?
$$
(A-\lambda I)x = 0
$$
means A - $\lambda I$ is **singular**, and det(A - $\lambda I$) = 0,find $\lambda$ first

EXAMPLE:
$$
A=
\begin{bmatrix}
3 & 1 \\
1 & 3
\end{bmatrix}
$$
$$
det(A-\lambda I) =
\begin{vmatrix}
3-\lambda & 1 \\
1 & 3-\lambda
\end{vmatrix} = (3-\lambda)^2-1 = 0
$$
$$
\lambda_1 = 2, \lambda_2 = 4
$$
$$
x_1 = 
\begin{bmatrix}
1 \\
1
\end{bmatrix},
x_2 =
\begin{bmatrix}
1 \\
-1
\end{bmatrix}
$$

EXAMPLE: Q = 90 degree rotation
$$
Q =
\begin{bmatrix}
0 & -1 \\
1 & 0
\end{bmatrix}
$$
- trace = 0, det = 1 = $\lambda_1\lambda_2$
$$
det(Q-\lambda I) = \lambda^2 + 1 = 0
\lambda_1 =  i, \lambda_2 = -i
$$
- no real eigenvalues, but complex eigenvalues
- conjugate pairs of eigenvalues means the matrix is reversible
> conjugate ， 共轭的

EXAMPLE: A = 2 by 2 matrix
$$
A =
\begin{bmatrix}
3 & 1 \\
0 & 3
\end{bmatrix},det (A-\lambda I) = 
\begin{vmatrix}
3-\lambda & 1 \\
0 & 3-\lambda
\end{vmatrix} = (3-\lambda)^2 = 0
$$
$$
\lambda_1 = 3, \lambda_2 = 3
$$
find eigenvectors:
$$
(A-3I)x = 
\begin{bmatrix}
0 & 1 \\
0 & 0
\end{bmatrix}
\begin{bmatrix}
x \\ 
\end{bmatrix} = [0]
$$
$$
x_1 = 
\begin{bmatrix}
1 \\
0
\end{bmatrix}, x_2 =
\begin{bmatrix}
\textrm{degenerate}
\end{bmatrix}
$$
- degenerate means there is only one eigenvector,a shortedge of basis


## 2.22 Diagonalization of matrices
$$
A x = \lambda x
$$
$$
\star \star \star     S^{-1}AS = \Lambda
$$
1. suppose A has n independent eigenvectors
2. put them in columns of S
$$
AS = A 
\begin{bmatrix}
x_1 & x_2 & ... & x_n
\end{bmatrix} =
\begin{bmatrix}
\lambda_1 x_1 & \lambda_2 x_2 & ... & \lambda_n x_n
\end{bmatrix} 
$$
$$
= 
\begin{bmatrix}
x_1 & x_2 & ... & x_n
\end{bmatrix}
\begin{bmatrix}
\lambda_1 & 0 & ... & 0 \\
0 & \lambda_2 & ... & 0 \\
... & ... & ... & ... \\
0 & 0 & ... & \lambda_n
\end{bmatrix}
$$
$$
= S \Lambda
$$
we need to find the reverse of  $\Lambda$
$$
\Lambda = S^{-1}AS
$$
$$
A = S \Lambda S^{-1}
$$
- a matrix left multiply by S and right multiply by S inverse is a diagonal matrix
- what is the eigenvalue of A ?

if 
$$
A x = \lambda x
$$
$$
A^2 x = A(Ax) = A(\lambda x) = \lambda(Ax) = \lambda^2 x
$$
so the eigenvalue of $A^2$ is $\lambda^2$
and the eigenvalue of $A^k$ is $\lambda^k$
$$
A^2 = S \Lambda S^{-1} S \Lambda S^{-1} = S \Lambda^2 S^{-1}
$$
So 
$$
A^k = S \Lambda^k S^{-1}
$$
(only possible if S^-1 exists)

THROREM:
$$
A^k \rightarrow 0 \textrm{ as } k \rightarrow \infty \textrm{ if all } |\lambda_i| < 1
$$

A is sure to have n independent evectors (and be diagonaligable)
if all the $\lambda$'s are different(no repeated eigenvalues)

EXAMPLE:
$$
A =
\begin{bmatrix}
2 & 1 \\
0 & 2
\end{bmatrix}
$$
$$
A - 2I =
\begin{bmatrix}
0 & 1 \\
0 & 0
\end{bmatrix}
$$
$$
det (A-2I) = 0, \lambda_1 = 2, \lambda_2 = 2
$$
so A is not diagonalizable,don't have two independent eigenvectors

Equaton: $u_{k+1} = Au_k$ 
1. given the vector $u_0$
$$
u_1 = Au_0, u_2 = Au_1 = A^2u_0,...,u_k = A^ku_0
$$

To really solve : 
$$
u_0 = c_1 x_1 + c_2 x_2...+c_n x_n
$$
$$
Au_0 = c_1 \lambda_1 x_1 + c_2 \lambda_2 x_2 + ... + c_n \lambda_n x_n
$$
$$
A^ku_0 = c_1 \lambda_1^k x_1 + c_2 \lambda_2^k x_2 + ... + c_n \lambda_n^k x_n
= \Lambda^k S c
$$

Fibonacci example: 
$$
0,1,1,2,3,5,8,13,21,...
$$
$$
F_{100}=?
$$
Fibonacci rule:
$$
F_{k+2} = F_{k+1} + F_k,
F_k = F_k
$$


how to indicate $u_k$?
$$
u_k =
\begin{bmatrix}
F_{k+1} \\
F_k
\end{bmatrix},
u_{k+1} =
\begin{bmatrix}
\\
\end{bmatrix}u_k?
$$

$$
u_{k+1} =
\begin{bmatrix}
1&1 \\
1&0
\end{bmatrix}
\begin{bmatrix}
F_{k+1} \\
F_k
\end{bmatrix}= 
\begin{bmatrix}
F_{k+1}+F_k \\
F_{k+1}
\end{bmatrix}
$$
SO:

$$
A =
\begin{bmatrix}
1&1 \\
1&0
\end{bmatrix}
$$
$$
|A-\lambda I| =
\begin{bmatrix}
1-\lambda & 1 \\
1 & -\lambda
\end{bmatrix}= \lambda^2 - \lambda - 1 = 0
$$
solve it:
$$
\lambda_1 = \frac{1+\sqrt{5}}{2}, \lambda_2 = \frac{1-\sqrt{5}}{2}
$$
> what it means?

> eigenvalues rules the growth of the Fibonacci sequence

$$
F_{100} \approx \lambda_1^{100} = c_1 \frac{1+\sqrt{5}}{2}^{100}
$$
$$
(A-\lambda I )x=
\begin{bmatrix}
1-\lambda & 1 \\
1 & -\lambda
\end{bmatrix}
\begin{bmatrix}
\lambda \\
1
\end{bmatrix} = 0
$$

## 2.23 exponential $e^{At}$ of a matrix
EXAMPLE:
$$
\frac{du_1}{dt} = -u_1 + 2u_2
\frac{du_2}{dt} = u_1 - 2u_2
$$
$$
\rightarrow
A = 
\begin{bmatrix}
-1 & 2 \\
1 & -2
\end{bmatrix}
$$
1. find eigenvalues and eigenvector
 
observe,and find it is singular
$$
A - \lambda I =
\begin{bmatrix}
-1-\lambda & 2 \\
1 & -2-\lambda
\end{bmatrix}
$$

$\lambda$ = 0,-3,so one part of the solution is $e^{0t}$,the other part is $e^{-3t}$
$$
A + 3I =
\begin{bmatrix}
2 & 2 \\
1 & 1
\end{bmatrix}
$$
it is singular,so we need to find the eigenvector
$$
x_2 = 
\begin{bmatrix}
1 \\
-1
\end{bmatrix},Ax_2 = -3x_2
$$

SO:
solution is two pure exponentials
$$
u(t) = c_1 e^{\lambda_1t}x_1 + c_2 e^{\lambda_2t}x_2
\approx c_1 \lambda^{k}x_1 + c_2 \lambda^{k}x_2
$$
find c1 and c2 by initial conditions:
$$
u(0) =
\begin{bmatrix}
1 \\
0
\end{bmatrix}
$$

at t = 0:
$$
c_1 
\begin{bmatrix}
2 \\
1
\end{bmatrix}+ 
c_2
\begin{bmatrix}
1 \\
-1
\end{bmatrix} =
\begin{bmatrix}
1 \\
0
\end{bmatrix}
$$

$$
\begin{bmatrix}
  2&1 \\
   1&-1 
\end{bmatrix}
$$
is the **eigenvector matrix**, every column is an eigenvector
so actually is 
$$
Sc=u(0)
$$
so c1 = 1/3, c2 = 1/3

so the steady state is
$$
u_{\infty} = \frac{1}{3}
\begin{bmatrix}
2 \\
1
\end{bmatrix}
$$
1. Stability: $u(t) \rightarrow u_{\infty}$ as t $\rightarrow \infty$
, we need $e^{\lambda t} \rightarrow 0$ as t $\rightarrow \infty$,means $\lambda < 0$
2. steady state: $\lambda_1 = 0$ means steady state and other $\lambda<0 $ 
3. blow up: any $\lambda > 0$ means blow up

example: 2 by 2 matrix
$$
A =
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$
trace = a+d = $\lambda_1 + \lambda_2$<0
> but it could not be sure that the matrix is stable, as an example:,it could have one stable part and another blows up

det > 0($\lambda_1 \lambda_2$)

$$
\frac{du}{dt} = Au
$$
goal : uncouple the equations,means diagonalize A
$$
 \frac{dv}{dt} = S^{-1} A S v = \Lambda v
$$
GOAL: find $e^{At}$
$$
v(t) = e^{\Lambda t}v(0)
$$
$$
u(t) = S e^{\Lambda t}S^{-1}u(0) = e^{At}u(0)
$$
> A is a matrix~

#### Matrix exponential:
- identity : expand it 
$$
e^{At} = S e^{\Lambda t} S^{-1}
$$
it means 
$$
e^{At} =
I + At + \frac{A^2t^2}{2!} + \frac{A^3t^3}{3!} + ...
$$
> talyor series

for matrix:
$$
(I-At)^{-1} = I + At + A^2t^2 + A^3t^3 + ...
$$
> if t is small, we could use the first two terms to approximate the result

Prove:
$$
u(t) = S e^{\Lambda t}S^{-1}u(0) = e^{At}u(0)
$$
> hope to compute $e^{At}$ from S and $\Lambda$

SO
$$
e^{At} = I + At + \frac{A^2t^2}{2!} + \frac{A^3t^3}{3!} + ...
= I + S \Lambda S^{-1}t + \frac{S \Lambda^2 S^{-1}t^2}{2!} + \frac{S \Lambda^3 S^{-1}t^3}{3!} + ...
$$

$$
= S (e^{\Lambda t}) S^{-1}
$$
> assumption: A could be diagonalized

$$
e^{\Lambda t} = =
\begin{bmatrix}
e^{\lambda_1 t} & 0 & ... & 0 \\
0 & e^{\lambda_2 t} & ... & 0 \\
... & ... & ... & ... \\
0 & 0 & ... & e^{\lambda_n t}
\end{bmatrix}
$$
if it is steady state, means $\lambda$ is real and **negative**


#### EXAMPLE:


$$
y'' +by' + ky = 0
$$
how to turn it into a 2 by 2 first order system?
$$
u = 
\begin{bmatrix}
y' \\
y
\end{bmatrix}
$$

$$
u' =
\begin{bmatrix}
y'' \\
y'
\end{bmatrix}=
\begin{bmatrix}
-b & -k \\
1 & 0
\end{bmatrix}
\begin{bmatrix}
y' \\
y
\end{bmatrix}
$$

## 2.24 Markov matrices
- What is a Markov matrix?
   1.  all entries are non-negative
   2.  each column adds up to 1
$$
A = 
\begin{bmatrix}
0.1 & 0.01 & 0.3 \\
0.2 & 0.99 & 0.3 \\
0.7 & 0.0 & 0.4
\end{bmatrix}
$$
- What is the meaning of a Markov matrix?
   1. $\lambda = 1 $is an eigenvalue 
   2.  All other eigenvalues are less than 1, $ |\lambda_i |$
   $$
   u_k = A^k u_0= c_1 \lambda_1^k x_1 + c_2 \lambda_2^k x_2(\text{goes to zero}) + ... + c_n \lambda_n^k x_n(\text{goes to zero})
   $$
   so $x_1$ part is the steady state
Prove:
$$
A - 1I =
\begin{bmatrix}
-0.9 & 0.01 & 0.3 \\
0.2 & -0.01 & 0.3 \\
0.7 & 0.0 & -0.6
\end{bmatrix}
$$
it needs to be singular, so we can calculate the det, another way is to add up the rows, it should be **zero**
prove the second part:
because $(1,1,1)$ is in the left n(A^T)， the rows are dependent, so the det is zero

Feature:
1. A and $A^T$ have the same eigenvectors
Prove:
$$
det(A-\lambda I) = 0\Rightarrow det(A^T-\lambda I) = 0
$$
2. $u_{k+1} = Au_k$ 
$$
u_k =c_1 \lambda_1^k x_1 + c_2 \lambda_2^k x_2 + ... + c_n \lambda_n^k x_n
$$

Projection with orthogonal basis:
$q_1,q_2,...,q_n$
$$
v = x_1 q_1 + x_2 q_2 + ... + x_n q_n
$$
take inner product with $q_1$
$$
q_1^Tv = x_1 q_1^Tq_1 + x_2 q_1^Tq_2 + ... + x_n q_1^Tq_n = x_1 + 0 = x_1
$$
SO 
$$
\begin{bmatrix}
q_1 & q_2 & ... & q_n
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2 \\
... \\
x_n
\end{bmatrix} = 
v
$$
$$
Qx = v, x = Q^{-1}v
$$

Fourier series:
$$
f(x) = a_0 + a_1 \cos x + b_1 \sin x + a_2 \cos 2x + b_2 \sin 2x + ...
$$
basis: $1,\cos x, \sin x, \cos 2x, \sin 2x, ...$,and they are orthogonal
> dot product: 
> for vectors: $V^Tw= v_1w_1...  $
> for functions: $f^Tg = \int f(x)g(x)dx$


## 2.25 Review
