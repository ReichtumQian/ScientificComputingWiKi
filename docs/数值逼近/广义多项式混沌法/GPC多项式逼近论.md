
前一节中我们介绍了平方可积空间和 GPC 多项式，本节中我们讨论通过 GPC 多项式的线性组合去逼近以随机变量为变量的函数。总共介绍强逼近以及弱逼近两种收敛情况。

## GPC 正交投影(强逼近)

将正交多项式的理论用到 GPC 多项式中即可获得对随机变量函数的逼近，也就是下面强逼近的原理

> **定义**(GPC 投影)
>
> 设一元随机变量 $Z$ 服从 $I_z$ 中概率分布函数 $F_Z(z) = P(Z \leq z)$，$f \in L_{dF_z}^2(I_z)$，GPC 正交基为 $\phi_n(z)$ ，则 $f$ 在 $\{\phi_n\}$ 下的多项式投影为：
>
> $$ P_Nf = \sum\limits_{k = 0}^N \hat{f}_k \phi_k(z),\quad \hat{f}_k = \frac{1}{\gamma_k} E(f\phi_k) $$

这种通过多项式投影得到的收敛在 GPC 理论中称为「强收敛」

> 定义(强逼近)
>
> $f(Z)$ 是随机变量 $Z$ 的函数，$Z$ 的分布函数为 $F_Z(z) = P(Z \leq z)$。若 $f_N(z) \in \mathbb{P}_N(z)$ 满足
>
> $$\lim \limits _{N \rightarrow \infty}||f_N - f||_{L_{F_z}^2} = 0$$
>
> 则称 $f_N(z)$ 为 $f$ 在 $||\cdot||_{F_z^2}$ 意义下的强逼近。


根据传统经典的多项式逼近理论，即可得到 GPC 正交投影的存在性和唯一性，在此处不再具体展开。


## 弱逼近

有时我们不知道随机变量的函数 $f(Z)$ 的显式表达，只知道 $Z$ 的概率分布，则无法构造强收敛的 GPC 展开，此时可构造弱收敛意义下的逼近。

> 定义(弱逼近)
>
> 设随机变量 $Y$ 是关于 $Z$ 的不知具体表达式的函数，已知其概率分布函数 $F_Y(y) = P(Y \leq y)$，若 GPC 基函数 $Y_N \in \mathbb{P}_N$ 满足
>
> $$ Y_N \stackrel{P}{\longrightarrow} Y $$
>
> 则称 $Y_N$ 是 $Y$ 的 GPC 弱逼近

注意弱逼近不一定唯一

> 例子(弱逼近不唯一的例子)
>
> 若 $Y \sim N(\mu,\sigma^2)$ ，$Z \sim N(0,1)$，以 Hermite 多项式作为基函数，则构造一次 GPC Hermite 展开有两个：
>
> $$
\begin{cases}
  Y_1(Z) = \mu H_0 + \sigma H_1(Z) = \mu + \sigma Z \sim N(\mu, \sigma^2)\\
  Y_2(Z) = \mu H_0 - \sigma H_1(Z) = \mu - \sigma Z \sim N(\mu,\sigma^2)
\end{cases}
$$






