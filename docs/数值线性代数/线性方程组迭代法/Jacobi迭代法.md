

## Jacobi 迭代的概念

下面假设我们要求解线性方程组 $A_{n\times n}x = b_{n \times 1}$，将矩阵 $A$ 拆分如下：

$$
\left[
  \begin{array}{cccc}
    a_{11}&a_{12}&\cdots&a_{1n}\\
    a_{21}&a_{22}&\cdots&a_{2n}\\
    \vdots&\vdots&\ddots&\vdots\\
    a_{n1}&a_{n2}&\cdots&a_{nn}
  \end{array}
\right]
=
\left[
  \begin{array}{cccc}
    a_{11}&0&\cdots&0 \\
          0&a_{22}&\cdots&0 \\
          \vdots&\vdots&\ddots&\vdots \\
          0&0&0&a_{nn}
  \end{array}
\right]
- 
\left[
  \begin{array}{cccc}
    0&0&\cdots&0\\
    -a_{21}&0&\cdots&0\\
    \vdots&\vdots&\ddots&\vdots\\
    -a_{n1}&-a_{n2}&\cdots&0
  \end{array}
\right]
- 
\left[
  \begin{array}{cccc}
    0&-a_{12}&\cdots&-a_{1n}\\
    0&0&\cdots&-a_{2n}\\
    \vdots&\vdots&\ddots&\vdots\\
    0&0&\cdots&0
  \end{array}
\right]
$$

令上面的等式对应记号 $A = D - L - U$，则 Jacobi 迭代格式如下。

> **定义**(Jacobi迭代)
>
> 线性方程组 $Ax = b$ 的系数矩阵分解为 $A = D - L - U$，其中 $D$ 是 $A$ 的对角线组成的矩阵，$L,U$ 是 $A$ 下、上三角取负形成的矩阵，则 Jacobi 迭代定义为：
>
> $$ x_k = D^{-1}(L+U)x_{k-1} + D^{-1}b $$
>
> 其中 $x_k$ 是 $n \times 1$ 的向量，用于逼近真实解 $x$。

显然如果 Jacobi 迭代收敛，则 $x_k$ 是收敛到 $Ax = b$ 的解的，原因在于设 $\lim \limits _{k \rightarrow \infty}x_k = y$，则 $x_k = D^{-1}(L+U)x_{k-1} + D^{-1}b$ 两侧同时对 $k$ 取极限，则得到

$$
y = D^{-1}(L+U)y + D^{-1}b \Rightarrow Ay = b
$$

因此 $y$ 也满足 $Ay = b$，根据线性方程组解的唯一性可知 $y = x$。

上面是 Jacobi 迭代的矩阵形式，而在实际计算中往往不会使用矩阵形式，因为无效的计算量过大，一般会使用下面的分量形式。

> **命题**(Jacobi 迭代分量形式)
>
> 设 $x_k = (x_k^{(1)},\cdots,x_k^{(n)})$ ，$A = (a_{ij})_{n \times n}$ ，则 Jacobi 迭代分量形式为：
>
> $$
x_k^{(i)} = -\frac{1}{a_{ii}}\sum\limits_{j = 1, j \neq i}^n a_{ij}x_{k-1}^{(j)} + \frac{b_i}{a_{ii}}
$$

> 证明：将矩阵形式展开即可：
>
> $$
\left[
  \begin{array}{c}
    x_k^{(1)}\\
    x_k^{(2)}\\
    \vdots\\
    x_k^{(n)}
  \end{array}
\right]
=
\left[
  \begin{array}{cccc}
    a_{11}^{-1}&&& \\
               &a_{22}^{-1}&& \\
               &&\ddots&\\
               &&&a_{nn}^{-1}
  \end{array}
\right]
\left[
  \begin{array}{cccc}
    0&-a_{12}&\cdots&-a_{1n} \\
     -a_{21}&0&\cdots&-a_{2n} \\
    \vdots&\vdots&\ddots&\vdots \\
     -a_{n1}&-a_{n2}&\cdots&0
  \end{array}
\right]
\left[
  \begin{array}{c}
    x_{k-1}^{(1)}\\
    x_{k-1}^{(2)}\\
    \vdots\\
    x_{k-1}^{(n)}
  \end{array}
\right]
+
D^{-1}
\left[
  \begin{array}{c}
    b_1\\
    b_2\\
    \vdots\\
    b_n
  \end{array}
\right] 
$$


## 加权 Jacobi 迭代

有时候 Jacobi 迭代并不能保证收敛，或者收敛速度不足，因此往往可以引入一个参数进行调整。参数的引入思路如下：不妨假设原向量序列迭代格式为 $x_k = Mx_{k-1} + g$ ，在这种假设下构造一个近似 $x_k$ 的新序列 $y_k$ 满足

$$
y_k =  (1-w)y_{k-1} + w(My_{k-1}+g)
$$

显然如果上述式子两侧同时对 $k$ 取极限，设 $\lim \limits _{k \rightarrow \infty}y_k = A$ ，则可以得到 $A = MA + g$，这与满足迭代格式 $x_k = Mx_{k-1} + g$ 的 $x_k$ 有着相同的极限（如果 $x_k$ 收敛）。而两者的区别在于整个迭代过程是不同的，因此收敛性和收敛速度都互不相同。

> **定义**(加权 Jacobi 迭代)
>
> 线性方程组 $Ax = b$ ，系数矩阵 $A = D - L - U$，则权重 $w \in \mathbb{R}$ 对应的加权 Jacobi 迭代为：
>
> $$
x_k = (1 - w)x_{k-1} + w \left( D^{-1}(L+U)x_{k-1} + D^{-1}b \right)
$$

一般实际计算时加权 Jacobi 迭代也不使用矩阵形式，矩阵形式只是方便记忆和分析，具体的分量形式为：

> **命题**(加权 Jacobi 迭代分量形式)
>
> 线性方程组 $Ax = b$ ，系数矩阵 $A = D - L - U$，$x_k = (x_k^{(1)},\cdots,x_k^{(n)})$，则权重 $w \in \mathbb{R}$ 对应的加权 Jacobi 迭代的分量形式为：
>
> $$
x_k^{(i)} = (1-w)x_{k-1}^{(i)}  - \frac{w}{a_{ii}} \sum\limits_{j = 1, j \neq i}^n a_{ij}x_{k-1}^{(j)} + \frac{w}{a_{ii}}b_i
$$
>
> 证明：写为矩阵形式即可看出
>
> $$
\left[
  \begin{array}{c}
    x_k^{(1)}\\
    x_k^{(2)}\\
    \vdots\\
    x_k^{(n)}
  \end{array}
\right] = (1-w) \left[
  \begin{array}{c}
    x_{k-1}^{(1)}\\
    x_{k-1}^{(2)}\\
    \vdots\\
    x_{k-1}^{(n)}
  \end{array}
\right]
+ w \left[
  \begin{array}{cccc}
    a^{-1}_{11}&&& \\
          &a^{-1}_{22}&& \\
          &&\ddots& \\
          &&&a^{-1}_{nn}
  \end{array}
\right]
\left[
  \begin{array}{cccc}
    0&-a_{12}&\cdots&-a_{1n} \\
     -a_{21}&0&\cdots&-a_{2n} \\
    \vdots&\vdots&\ddots&\vdots \\
     -a_{n1}&-a_{n2}&\cdots&0
  \end{array}
\right] + wD^{-1}b
$$






