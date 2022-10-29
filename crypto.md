# Crypto Cheat Sheet

## Extended Euclidean algorithm

### problem

$$
\gcd(a,b) = ax+by
$$

## Chinese remainder theorem

### problem

$$
\begin{array}{l}
    y = x_1 \pmod {M_1} \\
    y = x_2 \pmod {M_2} \\
    \vdots \\
    y = x_i \pmod {M_i} \\
\end{array}
$$

## Inverse

### problem

$$
\begin{array}{l}
		params &=&
		\begin{bmatrix}
		a_{1,1} & \cdots & a_{1,m} \\
		\vdots & \ddots & \vdots \\
		a_{n,1} & \cdots & a_{n, m}
		\end{bmatrix} \\
		\begin{bmatrix}
		    y_1 & \cdots & y_n \\
		\end{bmatrix} &=&
		\begin{bmatrix}
		    x_1 & \cdots & x_n \\
		\end{bmatrix}
		params \\
\end{array}
$$

### solve

$$
\begin{bmatrix}
    x_1 & \cdots & x_n \\
\end{bmatrix} =
\begin{bmatrix}
    y_1 & \cdots & y_n \\
\end{bmatrix}
params^{-1}
$$

## LLL

### problem

$$
\begin{array}{l}
		params &=&
		\begin{bmatrix}
		a_{1,1} & \cdots & a_{1,m} \\
		\vdots & \ddots & \vdots \\
		a_{n,1} & \cdots & a_{n, m}
		\end{bmatrix} \\
		\begin{bmatrix}
		    y_1 & \cdots & y_n \\
		\end{bmatrix} &=&
		\begin{bmatrix}
		    x_1 & \cdots & x_n \\
		\end{bmatrix}
		params \\
\end{array}
$$

### solve

$$
\begin{array}{l}
		\begin{bmatrix}
		    x_1 & \cdots & x_n & y_1 & \cdots & y_n \\
		\end{bmatrix} &=&
		\begin{bmatrix}
		    x_1 & \cdots & x_n \\
		\end{bmatrix}
		\begin{bmatrix}
		    1 & \cdots & 0 & \\
		    \vdots & \ddots & \vdots & params \\
		    0 & \cdots & 1 & \\
		\end{bmatrix} \\
		\begin{bmatrix}
		    x_1 & \cdots & x_n & y_1 & \cdots & y_n\\
		    \\
		    \\
		\end{bmatrix} &=&
		LLL\left(
		\begin{bmatrix}
		    1 & \cdots & 0 & \\
		    \vdots & \ddots & \vdots & params \\
		    0 & \cdots & 1 & \\
		\end{bmatrix}
		\right)
\end{array}
$$

## Newton's method

### problem

$$
a_n x^n + a_{n-1} x^{n-1} + \cdots + a_1 x + a_0 = 0
$$

## Coppersmith method

### problem

$$
x^n + a_{n-1} x^{n-1} + \cdots + a_1 x + a_0 \pmod M = 0
$$
