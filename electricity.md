# ELECTRICITY

由于听课跳过了所有的电学内容有一部分还是不太懂的，既然如此就去学一些麦克斯韦电磁理论吧！

## Ohm

电流密度 $\bm J$ 可以简单地看作是通过单位面积的电流的大小 $J=\lim_{A\to 0}\frac{I(A)}{A}$。更本质地，电流密度是该点的电荷密度再乘以电荷移动的平均速度 $\bm J=\rho\bm v$。而电流可以看作电流密度的面积分（通量）。

局域形式的欧姆定律表现为 $\bm J=\sigma \bm E$，其中 $\sigma$ 为该点的电导率（即电阻率 $\rho$ 的倒数）。

考虑两边同时做一个面积分，由于导体一个横截面上的 $E$ 我们看作是相同的，于是有 $I=\bm E\cdot S/\rho$，然后再做一个线积分，我们认为电流不变，于是有 $I\cdot l\rho/S=U$，也就是我们熟悉的 $U=IR$。

## Maxwell

偏微分：对于一个多元函数，比如三元函数 $f(x,y,z)$，$\frac{\partial f}{\partial x}$ 仍然得到一个三元函数，相当于对于每个 $y,z$，把 $f$ 视作一元函数 $f_{y,z}(x)$ 求导后的结果再放上去。

场函数：场函数是一个四元函数，参数为 $(x,y,z,t)$，分为标量场函数和矢量场函数。不过前面部分我们可能把它当成一个三元函数。

$\nabla$：latex 管他叫 nabla，是一个向量微分算子，大概可以相当于 $\frac{\partial}{\partial x}\bm i+\frac{\partial}{\partial y}\bm j+\frac{\partial}{\partial z}\bm k=(\frac{\partial}{\partial x},\frac{\partial}{\partial y},\frac{\partial}{\partial z})$ 的简写，在三维情况下。

梯度：对于一个场函数 $f$，其梯度定义为 $\nabla \otimes f$（张量积），如果 $f$ 是标量场，则可以写作 $\nabla f$。直观地看，如果 $f$ 为标量场，则得到一个矢量场，每个点指向更“高”的位置。比如我们有 $\bm E=-\nabla \varphi$，其中 $\varphi$ 表示电势场，$\bm E$ 表示电场强度场（即电场）。

如果对一个矢量场进行操作，将得到一个张量场（每个函数值为一个 $3\times 3$ 矩阵）。但我们不对其进行讨论。

通量：对于一个矢量场 $\bm f$，其通量定义为 $\Phi=\iint_{S} \bm f\cdot \mathrm d \bm S$，其中面元 $\bm S$ 的方向即为其法向量，大小即为其有向面积。

散度：散度是通量的微观形式，即某一点的散度定义为在该点处取一个体积收敛到 $0$ 的闭合曲面，其通量与体积之比。对于矢量场 $\bm f$，其在一点 $\bm x_0$ 上的散度定义为

$$
\mathrm{div}\bm f=\nabla \cdot \bm f=\frac{\partial f_x}{\partial x}+\frac{\partial f_y}{\partial y}+\frac{\partial f_z}{\partial z}
$$

其中 $f_x$ 表示我们只提取矢量在 $x$ 维上的分量（因此得到一个标量）。

直观地看，散度可以看作某一点处的无穷小的小球的表面的通量。某一点中 $\mathrm{div}\bm f>0$ 意味着整体来说该点的场是向外扩散的，反之如果 $<0$ 则是向内收缩的。

比如我们学过点电荷的电场公式 $E=kq/r^2$。实际上这个的一般情况即为高斯定律 $\nabla \cdot \bm E=\rho/\epsilon_0$，即真空中的电场散度等于该点的电荷密度除以真空介电常数。其中 $\epsilon_0$ 即为在电容一章中出现过的真空介电常数，有 $k=\frac{1}{4\pi \epsilon_0}$。$\rho$ 表示电荷密度。

只要我们对它做一个体积分

$$
\iiint_V(\nabla\cdot\bm E)\mathrm d V=\iiint _V\rho/\epsilon_0\mathrm dV
$$

发挥一下想象，左边等于穿过 $V$ 的表面的通量。而右边即为体积内的电荷量 $q$，于是

$$
\oiint_S \bm E\cdot \mathrm d\bm a=q/\epsilon_0
$$

在点电荷的电场中，半径相同的点 $E$ 处处相等且与球面垂直，于是可以把 $E$ 提出来，然后根据球的表面积公式 $\oiint_S |d\bm a|=4\pi r^2$，我们最终得到 $E\cdot 4\pi r^2=q/\epsilon_0$。

再比如 $\nabla \cdot \bm B=0$。也就是说任取一个闭合曲面其磁通量都为 $0$，因为磁感线都是闭合曲线。

环量：环量是一个矢量场沿一条闭合曲线的线积分

$$
\Gamma=\oint_C \bm f\cdot \mathrm d \bm l
$$

比如说，在一个力场中（每个点描述某个粒子如果在这个地方将受到什么力），环量表示该粒子沿这个曲线绕一圈做的总功。

> 当然你可能好奇为什么总位移是 $0$ 而做功不是 $0$。这涉及到*保守力*与*非保守力*之分。保守力，比如重力和静电场力，总是可以用一个势能来描述它，质点受到的力只与其空间位置无关。对于非保守力，可能还与其运动状态有关，比如摩擦力。我们中学物理所说的位移为零则做功为零是对保守力所说的，显然，对于保守力而言，做的功只与势能的变化量有关，所以回到同一个位置不会做功。

比如电场沿导体闭合回路的环量即为所谓感应电动势，根据法拉第定律，它等于负的磁通量变化率。

$$
\oint_L\bm E\cdot \mathrm d\bm l=E=-\frac{\mathrm d\Phi}{\mathrm dt}
$$

比如安培环路定理表明，感应电流与磁场环量有关。

$$
\oint_L \bm B\cdot \mathrm d\bm l=\mu_0 I_{encl}
$$

旋度：旋度是环量的微观形式。定义为

$$
\nabla \times\bm f=
\begin{vmatrix}
    \bm i& \dfrac{\partial}{\partial x}&f_x\\
    \bm j &\dfrac{\partial}{\partial y}&f_y\\
    \bm k &\dfrac{\partial}{\partial z}&f_z\\
\end{vmatrix}
$$

它等于一个包含该点的面积无穷小的闭合曲线的环量与面积之比。直观上，它等于某个矢量场在某一点上的旋转程度。

例子有 $\nabla \times\bm E=-\dfrac{\partial\bm B}{\partial t}$（Faraday's law），另外还有一个来自流体力学的直观的例子 $\bm \omega=\nabla\times \bm v$，当然我们一般认知的 $\bm v=\bm \omega\times \bm r$。

比如那个安培定则，实际上是错的。因为旋转的磁场除了会在导体中产生电流以外，还会产生一个等效于电流的变化的电场。也就是

$$
\oint_L \bm B\cdot \mathrm d\bm l=\mu_0 (I_{encl}+\epsilon_0\frac{\partial \Phi_E}{\partial t})
$$

$\epsilon_0$ 的数量级是 $10^{-12}$ 所以被忽略掉了。

其中 $\Phi_E$ 是电通量。放到微观角度就是 Ampere-Maxwell Law。

至此我们有能力写出所有的 Maxwell 方程组。

$$
\begin{aligned}
&\nabla \cdot \bm E=\rho/\epsilon_0&\text{(Gauss's law)}
\\
&\nabla \cdot \bm B=0&\text{(Gauss's law for magnetism)}
\\
&\nabla\times \bm E=-\dfrac{\partial\bm B}{\partial t}&\text{(Faraday's law)}
\\
&\nabla \times \bm B=\mu_0 (\bm J+\epsilon_0\frac{\partial \bm E}{\partial t})
&\text{(Ampère-Maxwell law)}
\end{aligned}
$$

其中 $\mu_0$ 是真空磁导率，满足 $c=(\epsilon_0\mu_0)^{-1/2}$

用这一套方程组就能描述整个电磁学的内容。

比如我们想要计算一条通电长直导线产生的磁场大小，只需要考虑一个半径为 $r$ 的圆，然后应用 Ampere 环路定则，得到 $2\pi r B=\mu_0 I$

## 光

先证一个数学上的引理 $\bm A\times(\bm B\times\bm C)=\bm B(\bm A\cdot\bm C)-\bm C(\bm A\cdot\bm B)$。即所谓 BAC-CAB 规则。貌似只能暴力展开

对 Faraday's law 两边取 $\nabla\times$ 得

$$
\nabla\times(\nabla \times\bm E)=\nabla\times \left(-\frac{\partial \bm B}{\partial t}\right)
$$

左边 $\nabla\times(\nabla \times \bm E)=\nabla(\nabla \cdot \bm E)-\nabla^2\bm E$，在真空中没有电荷的时候 $\rho=0$，此时 $\nabla\times \bm E=0$，于是左边等于 $-\nabla^2 \bm E$。

右边交换时空导数顺序得 $-\dfrac{\partial}{\partial t}(\nabla\times \bm B)=-\mu_0\epsilon_0\dfrac{\partial^2\bm E}{\partial t^2}$（同样由于是真空，我们认为不产生电流）。

这就是所谓的光的波动方程：

$$
\frac{\partial^2 \bm E}{\partial t^2}=c^2\nabla^2 \bm E
$$

于是我们知道，变化的电场和变化的磁场产生光，光的传播方向与电场方向和磁场方向三者互相垂直。$\bm S=\frac{1}{\mu_0}(\bm E\times \bm B)$

我们在高中学习的机械波可以看作一维波动方程，其分析我没看懂，暂不展开。

在介质中，我们有 $n=\sqrt{\epsilon_r\mu_r}$，其中 $\epsilon_r$ 表示物质的相对介电常数 $\epsilon_r=\epsilon/\epsilon_0$，$\epsilon$ 表示物质的绝对介电常数，磁导率 $\mu$ 同理。