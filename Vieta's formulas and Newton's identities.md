Vieta's Formulas 揭示了多项式方程的根与其系数的关系。

[参考](https://en.wikipedia.org/wiki/Newton%27s_identities)

考虑一个 $n$ 次多项式 $F(z_1,z_2,\dots,z_n)=\sum_{i=0}^na_iz^i$，如果他的根为 $z_1,z_2,\dots,z_n$，则我们有 $a_n\prod_{i=1}^n(z-z_i)=\sum_{i=0}^na_iz^i$。

于是我们有 $\forall 1\le k\le n,$
$$
\sum_{1\le i_1<i_2<\dots<i_k\le n}\prod_{j=1}^kz_{i_j}=(-1)^k\frac{a_{n-k}}{a_n}
$$

为了简单起见，下面我们认为 $a_n=1$。

记上面的等式左边为 $z_1,z_2,\dots,z_n$ 的 $k$ 阶初等对称函数 $e_k(z_1,z_2,\dots,z_n)$。特别地，$e_1=1$。我们有 $e_k=(-1)^ka_{n-k}$

列出一些简单的例子是有用的：
$$
\begin{aligned}
e_0&=1\\
e_1&=\sum_{i=1}^n z_i=p_1\\
e_2&=\sum_{1\le i<j\le n}z_iz_j\\
e_n&=\prod_{i=1}^nz_i\\
\end{aligned}
$$

记 $z_1,z_2,\dots,z_n$ 的 $k$ 阶幂和 $p_k(z_1,z_2,\dots,z_n)=\sum_{i=1}^n z_i^k$。

显然，我们可以注意到 $p_2+2e_2=p_1^2$。

熟悉生成函数的同学应该能够看出其中的相似性，我们不妨设 $E(t)=\prod_{j=1}^n(1+z_jt)$，则展开之后 $E(t)=\sum_{k}e_kt^k$

我们不妨对其应用对数求导法。

> 对于不熟悉对数求导法的人：对数求导法是一种利用对数简化函数求导的方法。（通常是像这里一样的 $\prod$ 型函数）。
>
> 一般的，对于 $y=f(x)$。我们对两边取绝对值后取对数得到 $\ln|y|=\ln|f(x)|$ 再求导。
> 
> 对于左边，我们利用链式求导法则，得到 $\frac{\mathrm{d}}{\mathrm{d}x}\ln|y|=\frac{y'}{y}$。于是我们得到 $y'=y\cdot \frac{\mathrm d}{\mathrm dx}\ln|f(x)|$

两边取对数得到 $\ln E(t)=\sum_{j=1}^n\ln(1+z_jt)$，于是
$$
E'(t)=E(t)\sum_{j=1}^n\frac{z_j}{1+z_jt}
$$

对于右边，展开得到

$$
\frac{z_j}{1+z_jt}=\sum_{m\ge 0}(-1)^mz_j^{m+1}t^m=\sum_{m\ge 0}(-1)^mp_{m+1}t^m
$$

故左边的系数 $[z^{k-1}]E'(t)=ke_k$，而右边正是 $\sum_{i=0}^{k-1}(-1)^ip_{i+1}e_{k-1-i}$，整理我们就得到牛顿多项式的一般表示。

$$
ke_k=\sum_{i=1}^k(-1)^{i-1}e_{k-i}p_i
$$

取 $k=2$ 即得到 $2e_2=e_1p_1-e_0p_2$。

对他做一个反演（实际上把一项隔离出来）可以得到
$$
p_k=(-1)^{k-1}ke_k+\sum_{i=1}^{k-1}(-1)^{k-1+i}e_{k-i}p_i,\forall n\ge k\ge 1
$$

以及
$$
p_k=\sum_{i=k-n}^{k-1}(-1)^{k-1+i}e_{k-i}p_i,\forall k>n\ge 1
$$