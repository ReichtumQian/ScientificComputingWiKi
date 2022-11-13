
## Sobolev 空间定义

下面我们引入 Sobolev 空间的概念

> **定义**(Sobolev空间)
>
> 给定 $\Omega \subset \mathbb{R}^n$ $m \in \mathbb{Z}^+$，$1 \leq p < \infty$，则 Sobolev 空间 $H^{m,p}$ 定义为
>
> $$ H^{m,p} := \{v : D^{\alpha} v \in L^p(\Omega), \forall |\alpha| \leq m\}  $$
>
> 这里 $D$ 表示广义导数， $m$ 用于指定广义导数阶， $p$ 用于指定 $L^p$ 可积类型

## Sobolev 空间范数与半范数

不难验证 Sobolev 空间是线性空间(此处不证)，根据指定的 $p$ 可以给 Sobolev 空间指定范数

> **定义**(Sobolev 空间范数)
>
> 给定 $\Omega \subset \mathbb{R}^n$， $m \in \mathbb{Z}^+$，若 $1 \leq p < \infty$，则 $H^{m,p}$ 空间的范数定义为
>
> $$ ||u||_{m,p} := \left( \sum\limits_{|\alpha| \leq m} ||D^{\alpha} u ||_{L^p}^p \right)^{1/p}$$
>
> 若 $p = \infty$ 则 $H^{m,\infty}$ 空间范数定义为
>
> $$ ||u||_{m,\infty} := \sup \limits_{|\alpha| \leq m} ||D^{\alpha}u||_{L^\infty}$$
>
> 其中 ${\displaystyle ||u||_{L^p} := \left( \int_{\Omega} |u|^p\mathrm{d} x \right)^{1/p}}$ ， ${\displaystyle ||u||_{L^{\infty}} = \inf \limits_{\Omega_0, m(\Omega_0) = 0} \{\sup \limits_{x \in \Omega - \Omega_0} |u(x)|\} }$

同时验证 Sobolev 空间关于上述范数是 Banach 空间(此处不证)。Sobolev 空间除了范数外，还可以通过限制广义导数的阶数定义半范数

> **定义**(Sobolev 空间半范数)
>
> 当 $1 \leq p < \infty$ 时可以定义 Sobolev 空间 $H^{m,p}$ 的半范数：
>
> $$ |u|_{m,p} := \left( \sum\limits_{|\alpha| = m} ||D^{\alpha}u||_{L^p} \right)^{1/p} $$
>
> 当 $p = \infty$ 时 Sobolev 空间 $H^{m,\infty}$ 的半范数定义为：
>
> $$ |u|_{m,\infty} := \sup \limits_{|\alpha| = m} ||D^{\alpha}u|| _{L^{\infty}}$$

## Sobolev 空间内积

类似于 $L^p$ 空间，绝大多数情况下 $H^{m,p}$ 空间并非内积空间，只有 $p = 2$ 时 $H^{m,2}$ 才为 Hilbert 空间。因此 $p = 2$ 时，我们将 $H^{m,2}$ 简记为 $H^m$ ，并引入下面的内积。

> **定义**(Sobolev 空间内积)
>
> 若 $\Omega \subset \mathbb{R}^n$，对 $\forall u,v \in H^m(\Omega)$ ，它们的内积定义为
>
> $$ \langle u, v \rangle_m := \sum\limits_{|\alpha| \leq m} \int_{\Omega} D^{\alpha} u \cdot D^{\alpha} v \mathrm{d} x$$



