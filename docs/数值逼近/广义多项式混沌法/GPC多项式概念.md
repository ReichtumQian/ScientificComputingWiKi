
广义多项式混沌法(GPC方法)，即通过期望定义平方可积空间和正交多项式，并用这种正交多项式去逼近以随机变量为自变量的函数。

## GPC 平方可积空间

类似于正交多项式逼近， GPC 平方可积空间即存放待逼近函数的空间。

> **定义**(GPC 平方可积空间)
>
> 设一元随机变量 $Z$ 服从概率分布函数 $F_Z(z) = P(Z \leq z)$，且满足
>
>$$E[|Z|^{2m}] = \int_{I_Z} |z|^{2m} \mathrm{d} F_Z < \infty,\quad m \in \mathbb{N} $$
>
> 则定义以其期望为内积的平方可积空间为：
>
> $$ L^2_{\mathrm{d}F_Z} (I_z) = \{f: I_z \rightarrow \mathbb{R}, E[f^2] < \infty\}  $$

该空间上定义的范数以及内积：

- 内积：${\displaystyle \langle f,g \rangle := E(fg)}$
- 范数：${\displaystyle ||f|| := E(f^2)}$


## GPC 基多项式

> 定义(GPC 基多项式)
>
> 设一元随机变量 $Z$ 服从概率分布函数 $F_Z(z) = P(Z \leq z)$，且满足
>
>$$E[|Z|^{2m}] = \int_{I_Z} |z|^{2m} \mathrm{d} F_Z < \infty,\quad m \in \mathbb{N} $$
>
> 则定义 GPC 基函数 $\phi_n$ 为满足下面条件的正交多项式：
> $$E[\phi_m \phi_n] = \gamma_n \delta_{m,n}, \quad \gamma_n = E[\phi_n^2]$$

特别地，根据 $Z$ 的分布类型，可具体表示为：

- 若 $Z$ 连续，记其概率分布函数为 $\rho(z)$ ， $Z$ 的取值范围为 $I_z$ ，则基函数正交性表示为

$$
E[\phi_n\phi_m] = \int_{I_z} \phi_m(z)\phi_n(z)\rho(z)\mathrm{d} z = \gamma_n\delta_{m,n}
$$

- 若 $Z$ 离散，$P(Z = z_i) = \rho_i$ ，则正交性表示为

$$
E[\phi_m\phi_n] = \sum\limits_i \phi_m(z_i)\phi_n(z_i)\rho_i = \gamma_n\delta_{m,n}
$$

> 例子(Hermite 多项式)
>
> 若 $Z \sim N(0,1)$ ，则概论分布函数为 $\rho(z) = \frac{1}{\sqrt{2\pi}} e^{- z^2/2}$，则 其 GPC 基函数即 Hermite 多项式

> 例子(Legendre 多项式)
>
> 若 $Z \sim U[-1,1]$ ，则 $\rho(z) = \frac{1}{2}$ ，其 GPC 基函数即 Legendre 多项式






