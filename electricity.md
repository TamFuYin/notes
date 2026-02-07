# ELECTRICITY

由于听课跳过了所有的电学内容有一部分还是不太懂的，既然如此就去学一些麦克斯韦电磁理论吧！

## Maxwell

偏微分：对于一个多元函数，比如三元函数 $f(x,y,z)$，$\frac{\partial f}{\partial x}$ 仍然得到一个三元函数，相当于对于每个 $y,z$，把 $f$ 视作一元函数 $f_{y,z}(x)$ 求导后的结果再放上去。

场函数：场函数是一个四元函数，参数为 $(x,y,z,t)$，分为标量场函数和矢量场函数。不过前面部分我们可能把它当成一个三元函数。

$\nabla$：latex 管他叫 nabla，是一个向量微分算子，大概可以相当于 $\frac{\partial}{\partial x}\bm i+\frac{\partial}{\partial y}\bm j+\frac{\partial}{\partial z}\bm k=(\frac{\partial}{\partial x},\frac{\partial}{\partial y},\frac{\partial}{\partial z})$ 的简写，在三维情况下。

梯度：对于一个场函数 $f$，其梯度定义为 $\nabla \otimes f$（张量积），如果 $f$ 是标量场，则可以写作 $\nabla f$。直观地看，如果 $f$ 为标量场，则得到一个矢量场，每个点指向更“高”的位置。比如我们有 $\bm E=-\nabla \varphi$，其中 $\varphi$ 表示电势场，$\bm E$ 表示电场强度场（即电场）。

如果对一个矢量场进行操作，将得到一个张量场（每个函数值为一个 $3\times 3$ 矩阵）。但我们不对其进行讨论。

通量：对于一个矢量场 $\bm f$，其通量定义为 $\Phi=\iint_{S} \bm f\cdot \mathrm d \bm S$，其中面元 $\bm S$ 的方向即为其法向量，大小即为其有向面积。

散度：散度是通量的微观形式。对于矢量场 $\bm f$，其在一点 $\bm x_0$ 上的散度定义为

$$
\mathrm{div}\bm f=\nabla \cdot \bm f=\frac{\partial f_x}{\partial x}+\frac{\partial f_y}{\partial y}+\frac{\partial f_z}{\partial z}
$$

其中 $f_x$ 表示我们只提取矢量在 $x$ 维上的分量（因此得到一个标量）。

直观地看，某一点中 $\mathrm{div}\bm f>0$ 意味着整体来说该点的场是向外扩散的，反之如果 $<0$ 则是向内收缩的。

另外一种定义是取一个体积收敛到 $0$ 的体，用表面上的通量与体积之比得到。

比如我们学过库仑力的公式 $F=kq_1q_2/r^2$，稍微变形可以得到 $E=kq/r^2$。实际上这个的本质即为 $\nabla \cdot \bm E=\rho/\epsilon_0$，其中 $\epsilon_0$ 即为在电容一章中出现过的真空介电常数，有 $k=\frac{1}{4\pi \epsilon_0}$。$\rho$ 表示电荷密度。

只要我们对它做一个体积分

$$
\iiint_V(\nabla\cdot\bm E)\mathrm d V=\iiint _V\rho/\epsilon_0\mathrm dV
$$

左边即为穿过 $V$ 的表面的通量，而右边即为体积内的电荷量 $q$，于是

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

当然你可能好奇为什么总位移是 $0$ 而做功不是 $0$。这涉及到*保守力*与*非保守力*之分。保守力，比如重力和静电场力，总是可以用一个势能来描述它，质点受到的力只与其空间位置无关。对于非保守力，可能还与其运动状态有关，比如摩擦力。

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

大概是这样的东西……它等于一个包含该点的面积收敛到无穷小的面的环量与面积之比。

例子有 $\nabla \times\bm E=-\dfrac{\partial\bm B}{\partial t}$，以及 $\bm \omega=\nabla\times \bm v$ 之类。

至此我们有能力写出所有的麦克斯韦方程组。

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

其中电流密度 $\bm J=\frac{\mathrm d I}{\mathrm dS}\bm n=\rho \bm v$。$\mu_0$ 是真空磁导率，满足 $c=(\epsilon_0\mu_0)^{-1/2}$

## 光

先证一个引理 $\bm A\times(\bm B\times\bm C)=\bm B(\bm A\cdot\bm C)-\bm C(\bm A\cdot\bm B)$。即所谓 BAC-CAB 规则。貌似只能暴力展开

对 Faraday's law 两边取 $\nabla\times$ 得

$$
\nabla\times(\nabla \times\bm E)=\nabla\times \left(-\frac{\partial \bm B}{\partial t}\right)
$$

左边 $\nabla\times(\nabla \times \bm E)=\nabla(\nabla \cdot \bm E)-\nabla^2\bm E$，在真空中没有电荷的时候 $\rho=0$，此时 $\nabla\times \bm E=0$，于是左边等于 $-\nabla^2 \bm E$。

右边交换时空导数顺序得 $-\dfrac{\partial}{\partial t}(\nabla\times \bm B)=-\mu_0\epsilon_0\dfrac{\partial^2\bm E}{\partial t^2}$。

这就是所谓的光的波动方程：

$$
\frac{\partial^2 \bm E}{\partial t^2}=c^2\nabla^2 \bm E
$$

于是我们知道，变化的电场和变化的磁场产生光，光的传播方向与电场方向和磁场方向三者互相垂直。$\bm S=\frac{1}{\mu_0}(\bm E\times \bm B)$

我们在高中学习的机械波可以看作一维波动方程，其分析涉及 something horrible，暂不展开。

在介质中，我们有 $n=\sqrt{\epsilon_r\mu_r}$，其中 $\epsilon_r$ 表示物质的相对介电常数 $\epsilon_r=\epsilon/\epsilon_0$，$\epsilon$ 表示物质的绝对介电常数，磁导率 $\mu$ 同理。