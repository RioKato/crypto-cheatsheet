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

## GCD

### problem

$$
\left\\{
  \begin{array}{l}
    N_1 = P_1 P_2 \\
    N_2 = P_1 P_3 \\
  \end{array}
\right.
$$

### answer

$$
P_1 = gcd(N_1, N_2)
$$

### problem

$$
\left\\{
  \begin{array}{l}
    c_1 = f_1(m_1) \\
    c_2 = f_2(m_2) \\
    m_2 = f_3(m_1) \\
  \end{array}
\right.
$$

### answer

$$
\begin{array}{l}
  \left\\{
    \begin{array}{l}
      g_1(x) = x - m_1 \\
      g_2(x) = c_1 - f_1(x) = g_1(x) h_1(x) \\
      g_3(x) = c_2 - f_2(f_3(x)) = g_1(x) h_2(x) \\
    \end{array}
  \right. \\
  g_1 = gcd(g_2, g_3)
\end{array}
$$

## Chinese remainder theorem

### problem
$$
\left\\{
  \begin{array}{l}
    a_0 = x \pmod {p_0} \\
    \vdots \\
    a_n = x \pmod {p_n} \\
  \end{array}
\right.
$$

### answer

$$
x = crt(a_0, \cdots, a_n, p_0, \cdots, p_n)
$$

### problem

$$
\left\\{
  \begin{array}{l}
    Q = x P \\
    a P = G \\
    a = \prod p_i \\
  \end{array}
\right.
$$

### answer

$$
\begin{array}{l}
  \left\\{
    \begin{array}{l}
      P_0 = (n / p_0) P \\
      \vdots \\
      P_n = (n / p_n) P \\
    \end{array}
  \right. \\
  \left\\{
    \begin{array}{l}
      p_0 P_0 = G \\
      \vdots \\
      p_n P_n = G \\
    \end{array}
  \right. \\
  \left\\{
    \begin{array}{l}
      b_0 P_0 = Q \\
      \vdots \\
      b_n P_n = Q \\
    \end{array}
  \right. \\
  \left\\{
    \begin{array}{l}
      b_0 = x \pmod {p_0} \\
      \vdots \\
      b_n = x \pmod {p_n} \\
    \end{array}
  \right. \\
  x = crt(b_0, \cdots, b_n, p_0, \cdots, p_n)
\end{array}
$$

## Fermat's factorization method

### problem

$$
N = p q
$$

### answer

$$
\begin{array}{l}
  \left\\{
    \begin{array}{l}
      p = (a - b) \\
      q = (a + b) \\
    \end{array}
  \right. \\
    N = (a - b) (a + b) = a^2 - b^2 \\
  \left\\{
    \begin{array}{l}
      c_1 = \sqrt {(\sqrt{N} + 1)^2 - N} \\
      c_2 = \sqrt {(\sqrt{N} + 2)^2 - N} \\
      \vdots \\
      c_i = \sqrt {(\sqrt{N} + i)^2 - N} \\
    \end{array}
  \right.
\end{array}
$$
