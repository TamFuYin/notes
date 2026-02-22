[参考文献](https://zhuanlan.zhihu.com/p/156760739)。朋友们，微分算子写个罗马正体很难吗？

## O 序言

牛顿以相对性原理和伽利略变换为框架，提出了牛顿运动定律，发展出一门基础物理学科——牛顿力学，这是经典物理学史上最高的丰碑之一。

严格地说，牛顿力学是经典力学中的一部分。在牛顿之后，拉格朗日和哈密顿相继发展了新的经典力学体系，即拉格朗日力学和哈密顿力学。

牛顿力学着眼于力、动量等矢量，牛顿运动定律也是矢量形式，故牛顿力学又称为*矢量力学*。

拉格朗日力学和哈密顿力学则看重系统的能量等标量，通过变分原理建立系统的动力学方程，所以拉格朗日力学和哈密顿力学合称为*分析力学*。

## I 牛顿力学与笛卡尔坐标

一个运动物体的*坐标*可以看作是一个关于时间的函数。

牛顿力学中，我们通过所谓牛顿运动定律确定物体的运动状态，其中牛一可以看作是牛二的特例，而牛三可以看作动量守恒的推论，因此实际上经典力学中最核心的是牛二：$\bm F(\bm r)=m\ddot{\bm r}$[^1]，当然这个实际上在相对论中是不成立的，因为 $m$ 实际上会随 $\bm v$ 变化。

[^1]: 混沌邪恶的物理学记号，上加多少个点表示对时间求多少次导。

## II 为什么我们需要分析力学

考虑一个经典的单摆问题。

![](https://pica.zhimg.com/v2-b132e048c6c431aa8da865c8eec067ba_1440w.jpg)

建立平面直角坐标系，并列出分量形式的牛顿第二定律

$$
\left\{\begin{array}{l}-T \frac{x}{\sqrt{x^{2}+y^{2}}}=m \ddot{x} \\ m g-T \frac{y}{\sqrt{x^{2}+y^{2}}}=m \ddot{y}\end{array}\right.
$$

这两个方程列出来我们立马就发现，由于不知道绳子的张力 $T$，导致这两个方程有三个未知量 $T,x,y$，所以我们解不了这个方程组。

我们自然而然能够想到，我们肯定把某个方程给漏了，才导致这个方程组不可解。

先来看看单摆问题和一般质点运动的不同之处。可以发现，物体的摆动受到绳子*约束*。所谓<ruby>约束<rt>constraint</rt></ruby>指的是物体运动需要遵循的条件，如绳子的摆长为定值，水流沿着管道流动，小球在地面上滚动等等。一般而言，对于一个完整系统，其所有约束为完整约束，即可以写成一个关于坐标和时间的方程式
$$
f(r_1,r_2,\dots,r_N,t)=0
$$

这里的约束是一个定常约束（即不包含 $t$ 的约束）：$x^2+y^2=l^2$。

这样三个方程三个变元，理论上是能够解出来的~~，然而人类恐怕难以做到。~~

为了研究有约束情况下的运动体系而不至于列出约束方程，我们引入分析力学。

## III 广义坐标

数学好的同学大概早就发现上面的做法很蠢，因为实际上可以用所谓三角换元的做法，或者说使用*极坐标*，只用一个 $\theta$ 就能表示 $(x,y)$ 的坐标，因为 $r$ 总是不变的。

然后我们直接沿着绳子的切线方向列牛二，即有 $-mg\sin \theta=ml\ddot{\theta}$。

由于 $\lim_{\theta\to 0}\frac{\sin\theta}{\theta}=1$，有 $\ddot{\theta}+\frac{g}{l}\theta=0$。

这是一个二阶常系数线性齐次微分方程，特征方程 $r^2+g/l=0$ 存在两个纯虚数根 $r=\pm \mathrm i\sqrt{g/l}$，因此通解为 $\theta=C_1\cos(\omega t+C_2)$，其中 $\omega=\sqrt{g/l}$。可以看出确实是简谐运动，且周期 $T=2\pi/\omega=2\pi\sqrt{\frac{l}{g}}$。

不仅极坐标，我们在三维空间中还有球坐标、柱坐标等等，像这样的所有坐标系我们称之为*广义坐标*。上述约束的定义中的坐标正是广义坐标。

## IV 约束力和虚位移

为了进一步地描述约束，考虑引入*虚位移*的概念。

所谓虚位移，指的是**符合约束条件**的**任意**的无穷小位移，用 $\delta \bm r$ 表示。

同理可以定义*虚功*等等。这样，我们称不做虚功的约束为*理想约束*，比如上面的绳子的约束就是理想约束，此文我们只研究理想约束。非理想约束不一定不做虚功，比方说绳子其实是具有弹性的，如果把它看作可拉伸的，则会做虚功。

注意我们所说的虚功为零不是之于单个物体而言，而是之于整个系统而言。

## V 达朗贝尔原理

考虑物体所受的主动力 $\bm F$（在上面的例子中，即为重力）与约束力 $\bm N$，则有 $\bm F+\bm N=m\ddot{\bm r}$。

考虑等式两边同点乘以虚位移，则由于 $\bm N\cdot\delta\bm r=0$，我们有 $(\bm F-m\ddot{\bm r})\cdot\delta\bm r=0$，其中 $-m\ddot{\bm r}$ 即为所谓惯性力。

对于多质点的系统，我们有 $\sum\bm N_i\cdot\delta\bm r_i=0$，于是有 $\sum(\bm F_i-m_i\ddot{\bm r}_i)\cdot\delta\bm r_i=0$，此即所谓达朗贝尔原理，他是拉格朗日力学的第二基本原理，容易发现可以反推牛二。

在无约束的情况下，质点间无相互影响，达朗贝尔原理中的 $\delta\bm r_i$ 实质上是相互独立且不为零，故各 $\delta\bm r_i$ 前的乘数必全为零，即 $F_i-m_i\ddot{\bm r}_i=0$，这也就是牛顿第二定律。

## VI 拉格朗日方程

考虑描述一个三维笛卡尔空间中由 $n$ 个质点组成的力学系统，且存在 $q$ 个约束，则我们认为这个系统的坐标的<ruby>自由度<rt>秩</rt></ruby>为 $s=3n-q$，我们的目标是用一种类似消元的方法把这些坐标换成恰好 $s$ 个互相独立的坐标，然后我们就可以得到很好的 $F_i-m_i\ddot{\bm r}_i=0$，也就是我们上面举的例子在干的事情。

考虑设这 $s$ 个独立坐标为 $q_1,q_2,\dots,q_s$。

我们有

$$
\delta \bm{r}_{i}=\sum_{j=1}^s\frac{\partial \bm{r}_{i}}{\partial q_{j}} \delta q_{j}+\frac{\partial \bm{r}_{i}}{\partial t} \delta t
$$

由于虚位移仅仅是位置上的一个无穷小变化，我们认为 $\delta t=0$，所以

$$
\delta \bm{r}_{i}=\sum_{j=1}^s\frac{\partial \bm{r}_{i}}{\partial q_{j}} \delta q_{j}
$$

带入达朗贝尔原理，得

$$
\sum_{i=1}^n(\bm F_i-m_i\ddot{\bm r}_i)\cdot\sum_{j=1}^s\frac{\partial \bm{r}_{i}}{\partial q_{j}} \delta q_{j}=0
$$

交换求和顺序

$$
\sum_{j=1}^s\delta q_{j}\sum_{i=1}^n\frac{\partial \bm{r}_{i}}{\partial q_{j}}\cdot(\bm F_i-m_i\ddot{\bm r}_i)
$$

根据假设，$\delta q_j$ 互相独立，因此我们得到，对于每个 $j$，
$$
\sum_{i=1}^n\frac{\partial \bm{r}_{i}}{\partial q_{j}}\cdot(\bm F_i-m_i\ddot{\bm r}_i)=0
$$

即

$$
\sum_{i=1}^n\frac{\partial \bm{r}_{i}}{\partial q_{j}}\cdot\bm F_i=
\sum_{i=1}^n\frac{\partial \bm{r}_{i}}{\partial q_{j}}\cdot m_i\ddot{\bm r}_i
$$

我们定义左边的部分为*广义力* $Q_j$。$Q_j$ 与 $q_j$ 相乘的量纲始终为功的量纲。

对于右边部分，考虑应用分部积分消去二阶导，得到

$$
\sum_{i=1}^n\frac{\partial \bm{r}_{i}}{\partial q_{j}}\cdot m_i\ddot{\bm r}_i=\frac{\mathrm d}{\mathrm d t}\left(\sum_{i=1}^nm_i\dot{\bm r}_i\cdot \frac{\partial \bm{r}_{i}}{\partial q_{j}}\right)-\sum_{i=1}^nm_i\dot{\bm r}_i\cdot \frac{\partial \dot{\bm{r}}_{i}}{\partial q_{j}}
$$

把 $\frac{\partial \bm{r}_{i}}{\partial q_{j}}$ 换成 $\frac{\partial \dot{\bm{r}}_{i}}{\partial \dot q_{j}}$，我们得到

$$
$$