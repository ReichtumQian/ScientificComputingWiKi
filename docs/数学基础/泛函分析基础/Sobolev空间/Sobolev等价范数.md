
由于有时需要在 Sobolev 空间中研究函数逼近的误差，因此需要研究 Sobolev 空间中范数的等价性。

## 范数与半范的等价性

当区域 $\Omega$ 满足一定的条件时， $H^{m,p}(\Omega)$ 中的范数和半范具有等价性，这也是 Poincare-Friedrich 的意义：

> **定理**(Poincare-Friedrich不等式)
>
> 若 $\Omega$ 是单联通的，且至少在一个方向有界，则对 $\forall m \in \mathbb{Z}_+$ ，存在正常数 $C(m)$ 使得
>
> $$
||v||_{H^m(\Omega)} \leq C(m) |v|_{H^m(\Omega)}, \quad \forall v \in H_0^m(\Omega)
$$

特别地，$m = 1$ 时，适当放缩可以获得以下这个常用的不等式

> **推论**
>
> 对于任意 $u \in H_0^1(\Omega)$ 满足
>
>$$
 ||u||_{H^1(\Omega)} \leq C \left( \left| \int_{\Omega} u\mathrm{d} \mathbf{x} \right|^2 + |u|^2_{H^1(\Omega)} \right)^{1/2}
$$

## 范数等价定理







