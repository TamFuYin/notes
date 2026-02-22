如何从万有引力公式推导开普勒三定律？

万有引力公式

$$
\bm F=-\frac{GMm}{r^2}\hat{\bm r}
$$

在此之前我们先来看看角动量是什么。角动量 $\bm L$ 是物体的**位置**矢量与动量的叉积
$$
\bm L=\bm r\times \bm p=\bm r\times(m\bm v)=r\times(\bm \omega\times(m\bm r))=mr^2\bm \omega =I\bm \omega
$$

物体的力矩 $\tau=\bm r\times \bm F$ 等于角动量的时变率 $\bm \tau=\dot {\bm L}$，这个不难用 $\bm F=m\bm a=m\dot{\bm v}$ 看出。

## 第二定律

单位时间内扫过的面积相等。

首先万有引力是一个径向力（即始终指向原点），也就是 $\tau =\bm r\times \bm F=0$，于是角动量 $\bm L$ 守恒。

（由于所有与角度有关的量都是正交平面的，所以就不写粗体了）

因此无穷小时间内扫过的面积

$$
\frac{\mathrm dA}{\mathrm dt}=\frac{1}{2}r^2\dot\theta=\frac{1}{2}r^2\omega=\frac{L}{2m}
$$

是定值。证毕。

## 第一定律

行星的运动轨迹为椭圆，且太阳处于其中一个焦点上。

我们需要知道椭圆的极坐标方程

$$
r=\frac{p}{1\pm e\cos\theta}
$$

然后需要对万有引力公式做一个偏微分方程，算出来刚好有这个通解，但是我没看懂。

## 第三定律

$T^2\propto A^3$。

由椭圆面积公式 $A=\pi ab$。

刚才我们得到 $T=\frac{A}{\mathrm dA/\mathrm dt}=\frac{2\pi abm}{L}$

椭圆的半通径 $p=$