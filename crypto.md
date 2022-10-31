# Crypto Cheat Sheet

## Inverse

### problem

$$
\left\\{
  \begin{array}{l}
    b_1 = a_{1,1} x_1 + a_{2,1} x_2 + \cdots + a_{n,1} x_n \\
    b_2 = a_{1,2} x_1 + a_{2,2} x_2 + \cdots + a_{n,2} x_n \\
    \vdots \\
    b_m = a_{1,m} x_1 + a_{2,m} x_2 + \cdots + a_{n,m} x_n \\
  \end{array}
\right.
$$

### answer

$$
\begin{array}{l}
  A &=&
    \begin{bmatrix}
      a_{1,1} & \cdots & a_{1,m} \\
      \vdots & \ddots & \vdots \\
      a_{n,1} & \cdots & a_{n,m} \\
  \end{bmatrix} \\
  \begin{bmatrix}
    b_1 & \cdots & b_m \\
  \end{bmatrix} &=&
  \begin{bmatrix}
    x_1 & \cdots & x_n \\
  \end{bmatrix}
  A \\
  \begin{bmatrix}
    x_1 & \cdots & x_n \\
  \end{bmatrix} &=&
  \begin{bmatrix}
    b_1 & \cdots & b_m \\
  \end{bmatrix}
  A^{-1}
\end{array}
$$

## LLL

### problem

$$
\left\\{
  \begin{array}{l}
    y_1 = a_{1,1} x_1 + a_{2,1} x_2 + \cdots + a_{n,1} x_n \\
    y_2 = a_{1,2} x_1 + a_{2,2} x_2 + \cdots + a_{n,2} x_n \\
    \vdots \\
    y_m = a_{1,m} x_1 + a_{2,m} x_2 + \cdots + a_{n,m} x_n \\
  \end{array}
\right.
$$

### answer

$$
\begin{array}{l}
  A &=&
  \begin{bmatrix}
    a_{1,1} & \cdots & a_{1,m} \\
    \vdots & \ddots & \vdots \\
    a_{n,1} & \cdots & a_{n,m} \\
  \end{bmatrix} \\
  \begin{bmatrix}
    y_1 & \cdots & y_m \\
  \end{bmatrix} &=&
  \begin{bmatrix}
    x_1 & \cdots & x_n \\
  \end{bmatrix}
  A \\
  \begin{bmatrix}
    x_1 & \cdots & x_n & y_1 & \cdots & y_m \\
  \end{bmatrix} &=&
  \begin{bmatrix}
    x_1 & \cdots & x_n \\
  \end{bmatrix}
  \begin{bmatrix}
    1 & \cdots & 0 & \\
    \vdots & \ddots & \vdots & A \\
    0 & \cdots & 1 & \\
  \end{bmatrix} \\
  \begin{bmatrix}
    x_1 & \cdots & x_n & y_1 & \cdots & y_m\\
    \\
    \\
  \end{bmatrix} &=&
  LLL\left(
    \begin{bmatrix}
      1 & \cdots & 0 & \\
      \vdots & \ddots & \vdots & A \\
      0 & \cdots & 1 & \\
    \end{bmatrix}
  \right)
\end{array}
$$

### problem

$$
\left\\{
  \begin{array}{l}
    y_1 = a_{1,1} x_1 + a_{2,1} x_2 + \cdots + a_{n,1} x_n \pmod N \\
    y_2 = a_{1,2} x_1 + a_{2,2} x_2 + \cdots + a_{n,2} x_n \pmod N \\
    \vdots \\
    y_m = a_{1,m} x_1 + a_{2,m} x_2 + \cdots + a_{n,m} x_n \pmod N \\
  \end{array}
\right.
$$

### answer

$$
\begin{array}{l}
  \left\\{
    \begin{array}{l}
      y_1 = a_{1,1} x_1 + a_{2,1} x_2 + \cdots + a_{n,1} x_n + N k_1 \\
      y_2 = a_{1,2} x_1 + a_{2,2} x_2 + \cdots + a_{n,2} x_n + N k_2 \\
      \vdots \\
      y_m = a_{1,m} x_1 + a_{2,m} x_2 + \cdots + a_{n,m} x_n + N k_m \\
    \end{array}
  \right. \\
  A &=&
  \begin{bmatrix}
    a_{1,1} & \cdots & a_{1,m} \\
    \vdots & \ddots & \vdots \\
    a_{n,1} & \cdots & a_{n,m} \\
    N & \cdots & 0 \\
    \vdots & \ddots & \vdots \\
    0 & \cdots & N \\
  \end{bmatrix} \\
  \begin{bmatrix}
    y_1 & \cdots & y_m \\
  \end{bmatrix} &=&
  \begin{bmatrix}
    x_1 & \cdots & x_n & k_1 & \cdots & k_m \\
  \end{bmatrix}
  A \\
  \begin{bmatrix}
    x_1 & \cdots & x_n & y_1 & \cdots & y_m \\
  \end{bmatrix} &=&
  \begin{bmatrix}
    x_1 & \cdots & x_n & k_1 & \cdots & k_m \\
  \end{bmatrix}
  \begin{bmatrix}
    1 & \cdots & 0 & \\
    \vdots & \ddots & \vdots & \\
    0 & \cdots & 1 & A \\
    0 & \cdots & 0 & \\
    \vdots & \ddots & \vdots & \\
    0 & \cdots & 0 & \\
  \end{bmatrix} \\
  \begin{bmatrix}
    x_1 & \cdots & x_n & y_1 & \cdots & y_m\\
    \\
    \\
  \end{bmatrix} &=&
  LLL\left(
    \begin{bmatrix}
      1 & \cdots & 0 & \\
      \vdots & \ddots & \vdots & \\
      0 & \cdots & 1 & A \\
      0 & \cdots & 0 & \\
      \vdots & \ddots & \vdots & \\
      0 & \cdots & 0 & \\
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
x^n + a_{n-1} x^{n-1} + \cdots + a_1 x + a_0 = 0 \pmod N
$$
