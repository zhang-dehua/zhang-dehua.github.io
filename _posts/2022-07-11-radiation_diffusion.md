---
layout: post
title: 辐射扩散
description: 描述
date: 2022-07-11
tags: 高能量密度物理
---



# 辐射流体力学

## 辐射场的定义和基本概念

### 辐射场的描述

#### 光子

辐射场中的能量由光子携带，频率$\nu$的光子携带的能量为$E=h\nu$，光子是没有质量的粒子，光子在真空中光速为$c$，因此光子的动量$p=\frac{h\nu}{c}$，在于物质碰撞之前，光子都是沿着直线以真空中光速运动，并且频率不发生变化。

#### 光子的分布函数

$$
f=f(\vec{r},\nu,\vec{\Omega},t) \\
dn=f d\vec{r} d\nu d\vec{\Omega}
$$

其中$f(r,\nu,\Omega,t)$为光子在时刻$t$，在相空间的分布，$\vec r$为空间点的位置，$\vec \Omega$为光子的运动方向。$dn$为时刻$t$，在以空间点$\vec r$为中心的体积微元$d \vec r$内的，频率在以$\nu$为中心的频率区间$d\nu$内的，运动方向在以$\Omega$为中心的立体角微元$d \Omega$内的光子的数量。

在直角坐标系下有
$$
d\vec r=dx dy dz \\
\vec \Omega=(\sin\theta \cos\phi,\sin\theta \sin\phi,\cos\theta),\ \theta \in [0,\ \pi],\ \phi \in [0,\ 2\pi]\\
d\vec \Omega = \sin\theta d\theta d\phi=d\mu d\phi,\ \mu=\cos\theta \in =[-1,\ 1]
$$

#### 辐射强度

$$
I(\vec r,\nu,\vec \Omega,t)=ch\nu f(\vec r,\nu, \vec \Omega,t) \\
dE=I(\vec r,\nu,\vec \Omega,t)\cos\theta d\nu d\vec \Omega d\sigma dt
$$

其中$I(\vec r,\nu,\vec \Omega,t)$为辐射强度，$dE$为在时刻$t$，单位时间内，通过以空间点$\vec r$为中心的面积微元的，频率在以$\nu$为中心的频率区间$d\nu$内的，运动方向在以$\Omega$为中心的立体角微元$d \Omega$内的光子的能量，$\theta$为光子运动方向$\vec \Omega$与面积微元法向量$\vec n$的夹角，即$\cos\theta=\vec \Omega\cdot\vec n$，如下图所示。

<img src=".\figure\dE_intepretation_I.png" alt="fig1.1" style="zoom: 50%;" />

若辐射强度$I$与角度$\vec \Omega$无关，则辐射场是各向同性的；若辐射强度$I$与空间位置$\vec r$无关，则辐射场是均匀。当辐射场与物质达到完全的热平衡时，辐射场就是各项同性且均匀的，此时辐射强度由普朗克函数$B(\nu,T)$给出
$$
I=B(\nu,T)=\frac{2h\nu^3}{c^2}(e^{h\nu/kT}-1)^{-1}
$$
其中$h$为普朗克常量。

#### 辐射能量密度

辐射能量密度$U$是辐射强度$I$的0次角矩，表示单位体积内辐射场的能量，如下式
$$
U=\int_{0}^{\infty}d\nu\int_{4\pi}d\vec \Omega h\nu  f=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi}d\vec \Omega I
$$
若辐射强度$I$由普朗克函数$B(\nu,T)$给出，则能量密度$U_p$为
$$
U_p=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi}d\vec \Omega B = \frac{4\pi}{c}\int_{0}^{\infty}d\nu \frac{2h\nu^3}{c^2}(e^{h\nu/kT}-1)^{-1} \\
$$
设$x=h\nu/kT$，则有
$$
U_p=\frac{8\pi k^4 T^4}{h^3c^3}\int_{0}^{\infty}\frac{x^3}{(e^x-1)}dx
$$
其中积分项为
$$
\int_{0}^{\infty}\frac{x^3}{(e^x-1)}dx=\frac{\pi^4}{15}
$$
故
$$
U_p=\frac{8\pi^5 k^4 T^4}{15h^3c^3}=aT^4,\ a=\frac{8\pi^5 k^4}{15h^3c^3}
$$
此时，辐射能量密度也经常写作$U_p=\frac{4\sigma}{c}T^4$，其中$\sigma=ac/4$为斯特藩-玻尔兹曼常数。

#### 辐射通量

辐射通量$\vec F$是辐射强度$I$的1次角矩，表示辐射场的能流，如下式
$$
\vec F=\int_{0}^{\infty}d\nu\int_{4\pi}d\vec \Omega ch\nu  \vec \Omega f=\int_{0}^{\infty}d\nu\int_{4\pi}\vec \Omega I d\vec \Omega
$$
在直角坐标系下，三个方向上的辐射通量分量分别为
$$
F_x==\int_{0}^{\infty}d\nu\int_{4\pi} \Omega_x I d\vec \Omega \\
F_y==\int_{0}^{\infty}d\nu\int_{4\pi} \Omega_y I d\vec \Omega \\
F_z==\int_{0}^{\infty}d\nu\int_{4\pi} \Omega_z I d\vec \Omega \\
$$
对于各向同性的辐射场，辐射通量显然为0，即各个方向上面都没有能量流。

#### 辐射压力张量

辐射压力张量$\Bbb{P}$是辐射强度$I$的2次角矩。根据气体动理学理论，压力是由通过单位时间通过单位面积的粒子的动量定义的，将此定义应用于辐射场，可得到辐射压力张量，如下式
$$
\Bbb{P}=\int_{0}^{\infty}d\nu\int_{4\pi}d\vec \Omega c \frac{h\nu}{c}  \vec \Omega \vec \Omega f=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi}\vec \Omega \vec \Omega I d\vec \Omega
$$
在直角坐标系下，辐射压力的九个分量分别为
$$
\begin{cases}
\Bbb{P}_{xx}=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi} \Omega_x \Omega_x I d\vec \Omega,\ 
\Bbb{P}_{xy}=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi} \Omega_x \Omega_y I d\vec \Omega,\ 
\Bbb{P}_{xz}=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi} \Omega_x \Omega_z I d\vec \Omega\\ 
\Bbb{P}_{yx}=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi} \Omega_y \Omega_x I d\vec \Omega,\ 
\Bbb{P}_{yy}=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi} \Omega_y \Omega_y I d\vec \Omega,\ 
\Bbb{P}_{yz}=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi} \Omega_y \Omega_z I d\vec \Omega\\ 
\Bbb{P}_{zx}=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi} \Omega_z \Omega_x I d\vec \Omega,\ 
\Bbb{P}_{zy}=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi} \Omega_z \Omega_y I d\vec \Omega,\ 
\Bbb{P}_{zz}=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi} \Omega_z \Omega_z I d\vec \Omega
\end{cases}
$$
可以看出辐射压力张量是对称的，即$\Bbb{P}_{ij}=\Bbb{P}_{ji}$。另外，由于$\Omega_x^2+\Omega_y^2+\Omega_z^2=1$，对任意辐射场，则有
$$
\Bbb{P}_{xx}+\Bbb{P}_{yy}+\Bbb{P}_{zz}=\frac{1}{c}\int_{0}^{\infty}d\nu\int_{4\pi}d\vec \Omega I=U
$$
平均压力为
$$
\bar{\Bbb{P}}=\frac{1}{3}(\Bbb{P}_{xx}+\Bbb{P}_{yy}+\Bbb{P}_{zz})=\frac{1}{3}U
$$
对于各向同性的辐射场，辐射压力张量的非对角元素为0，且对角元素等于平均压力$\bar{\Bbb{P}}$，即
$$
\begin{cases}
\Bbb{P}_{ij}=\frac{1}{3}U,\ i=j\\
\Bbb{P}_{ij}=0,\ i\ne j
\end{cases}
$$
对于普朗克分布的辐射强度，则有
$$
\Bbb{P}_{xx}=\Bbb{P}_{yy}=\Bbb{P}_{zz}=\frac{1}{3}aT^4
$$
对于与各向同性相反的一个极端情况，如果某时刻某空间点上的所有光子的运动方向均指向x方向，即辐射强度$I$在方向上的分布为在x方向上的Drac函数，则有
$$
\begin{cases}
\Bbb{P}_{xx}=U\\
\Bbb{P}_{ij}=0,\ i\ne x,\ j\ne x
\end{cases}
$$

### 辐射场与物质的相互作用

辐射场（光子）与物质的相互作用有三种方式：吸收，散射，发射。

#### 吸收过程

当光子穿过物质的时候，有一定的概率被物质吸收而消失。可以用宏观吸收系数$\sigma_a(\vec r,\nu,t)$来描述光子被物质吸收的过程，当光子在物质中运动距离为$ds$时，则光子被吸收的概率为
$$
\sigma_a(\vec r,\nu,t)ds
$$
其中吸收系数$\sigma_a$只依赖与光子的频率$\nu$以及物质的状态参数，而物质的状态参数又与空间位置$\vec r$和时间$t$有关，而通常假设光子被物质吸收的概率与其运动方向无关，表示光子被吸收前平均经过的距离。宏观吸收系数也经常被表$\sigma_a$示成为
$$
\sigma_a(\nu)=\rho\chi_a(\nu) \\
\sigma_a(\nu)=n\mu_a(\nu)
$$
其中，$\rho$是物质的质量密度，$\chi_a(\nu)$被称为质量吸收系数，$n$是物质的粒子数密度，$\mu_a(\nu)$被称为微观吸收系数。

#### 散射过程

与吸收过程类似，可以定义出光子的散射系数$\sigma_s(\vec r,\nu,t)$来描述光子被物质吸收的过程，当光子在物质中运动距离为$ds$时，则光子被散射的概率为
$$
\sigma_s(\vec r,\nu,t)ds
$$
并且常假设光子被物质散射的概率与其运动方向无关。光子被物质散射之后其频率与运动方向均发生改变，即$(\nu' \rightarrow \nu,\vec \Omega' \rightarrow \vec\Omega)$，可以定义微分散射系数$\sigma_s(\nu'\rightarrow\nu,\vec\Omega'\rightarrow\vec\Omega)$来描述散射过程的概率，若假设散射过程的概率仅与散射角有关而与散射前后的光子运动方向有关，则微分散射系数可以表示成$\sigma_s(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)$。光子在物质中运动距离为$ds$，频率被从$\nu'$散射到以$\nu$为中心的频率区间$d\nu$，方向被从$\Omega'$散射到以$\Omega$为中心的立体角微元$d\vec \Omega$的概率为
$$
\sigma_s(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)d\nu d\vec\Omega ds
$$
对微分散射系数$\sigma_s(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)$在频率和立体角上积分可以得到散射系数$\sigma_s(\nu')$，即
$$
\sigma_s(\nu')=\int_{0}^{\infty}d\nu \int_{4\pi}d\vec\Omega\sigma_s(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)
$$
若选择发生散射前的角度$\vec \Omega'$为$z$轴，散射角度用$\mu_0=\vec\Omega'\cdot\vec\Omega=\cos\theta$表示，则上式可表示成
$$
\sigma_s(\nu')=2\pi\int_{0}^{\infty}d\nu \int_{-1}^{1}d\mu_0\sigma_s(\nu'\rightarrow\nu,\mu_0)
$$
微分散射系数$\sigma_s(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)$可以被表示成为以下的形式
$$
\sigma_s(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)=\sigma_s(\nu')K(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)
$$
其中$K(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)$为散射核,表示状态为$(\nu',\vec \Omega')$光子已经被散射的前提下，散射后状态变为$(\nu,\vec \Omega)$的条件概率，散射核对频率$\nu$和空间角$\vec \Omega$的积分为1，即
$$
\int_{0}^{\infty}d\nu \int_{4\pi}d\vec\Omega K(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)=1
$$
若散射后，光子频率不发生改变，即散射是相干的，则散射核可以表示成包含一个Drac函数的形式，如下
$$
K(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)=K(\vec\Omega'\cdot\vec\Omega)\delta(\nu'-\nu)
$$
此时$K(\vec\Omega'\cdot\vec\Omega)$对空间角$\vec \Omega$的积分为1，即
$$
\int_{4\pi}d\vec\Omega K(\vec\Omega'\cdot\vec\Omega)=2\pi\int_{-1}^{1}d\mu_0 K(\mu_0)=1
$$
若散射核$K(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)$与散射角无关，光子被散射到任意方向的概率都相等，即散射是各向同性的，则散射核可以表示成
$$
K(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)=\frac{1}{4\pi}K(\nu'\rightarrow\nu)
$$
此时$K(\nu'\rightarrow\nu)$对的对频率$\nu$积分为1，即
$$
\int_{0}^{\infty}d\nu  K(\nu'\rightarrow\nu)=1
$$
若散射既是相干的，也是各项同性的，则散射核可以表示成最简单形式，如下
$$
K(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)=\frac{1}{4\pi}\delta(\nu'-\nu)
$$
对于很多问题，上式是对散射核的一种合理的近似。

综合考虑吸收与散射的过程，可以得到光子与物质的总相互作用系数$\sigma(\vec r,\nu,t)$如下
$$
\sigma(\nu)=\sigma_a(\nu)+\sigma_s(\nu)
$$
通过相互作用系数$\sigma(\nu)$可以得到光子与物质相互作用的平均自由程$\lambda$。若有一束总数为$N_0$光子，经过$ds$距离后，与物质相互作用（吸收和散射）的光子的数量为
$$
dN=-N\sigma ds
$$
即
$$
\frac{dN}{ds}=-N\sigma 
$$
若$\sigma$与$s$无关，光子总数$N$关于运动距离$s$的解为
$$
N(s)=N_0e^{-\sigma s}
$$
可以得到这束光子的平均自由程如下
$$
\lambda(\nu)=\bar{s}(\nu)=\frac{\int_{0}^{\infty}sN(s)\sigma ds}{N_0}=\frac{1}{\sigma(\nu)}
$$
于此类似，可以得到吸收平均自由程$\lambda_a=1/\sigma_a$和散射平均自由程$\lambda_s=1/\sigma_s$，并且由$\sigma=\sigma_a+\sigma_s$可知
$$
\lambda^{-1}=\lambda_a^{-1}+\lambda_s^{-1}
$$

#### 发射过程

物质除可吸收光子，或者是光子的频率和角度发生改变之外，还可自发的发射光子。物质自发发射光子的过程可以由函数$q(\vec r,\nu,t)$描述，位于空间点$\vec r$的物质在单位时间单位体积内发射出的，在以$\nu$为中心的频率区间$d\nu$内的，在以$\vec \Omega$为中心的立体角微元$d\vec \Omega$内的光子数为
$$
q(\vec r,\nu,t)d\nu d\vec\Omega
$$
这里假设物质发射光子过程与角度无关，即向各个方向发射光子的概率相同。

## 辐射输运方程

### 辐射输运方程的原始形式

#### 光子分布函数方程

类比于玻尔兹曼方程，可得到的光子分布函数方程如下
$$
\frac{\partial f(\nu,\vec \Omega)}{\partial t}+c\vec\Omega\cdot\nabla f(\nu,\vec\Omega)=q(v)-c\sigma_a(\nu) f(\nu,\vec\Omega) \\
+c\int_{0}^{\infty}d\nu'\int_{4\pi}d\vec\Omega'[\sigma_s(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)f(\nu',\vec\Omega')-\sigma_s(\nu\rightarrow\nu',\vec\Omega\cdot\vec\Omega')f(\nu,\vec\Omega)]
$$
#### 辐射强度方程

对光子分布函数方程等号两端乘光子的能量$h\nu$可得到辐射强度方程如下
$$
\frac{1}{c}\frac{\partial I(\nu,\vec \Omega)}{\partial t}+\vec\Omega\cdot\nabla I(\nu,\vec\Omega)=j(v)-\sigma_a(\nu) I(\nu,\vec\Omega) \\
+\int_{0}^{\infty}d\nu'\int_{4\pi}d\vec\Omega'\frac{\nu}{\nu'}\sigma_s(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)I(\nu',\vec\Omega')\\
-\int_{0}^{\infty}d\nu'\int_{4\pi}d\vec\Omega'\sigma_s(\nu\rightarrow\nu',\vec\Omega\cdot\vec\Omega')I(\nu,\vec\Omega)
$$
其中$j(\vec r,\nu,t)=h\nu q(\vec r,\nu,t)$为单位体积内电子发射功率。考虑受激辐射，电子发射和散射将受到已经位于反应终态的光子数的影响而增强，增强因子大小为$1+\frac{c^2I}{2h\nu^3}$，则辐射强度方程为
$$
\frac{1}{c}\frac{\partial I(\nu,\vec \Omega)}{\partial t}+\vec\Omega\cdot\nabla I(\nu,\vec\Omega)=j(v)[1+\frac{c^2I(\nu,\vec \Omega)}{2h\nu^3}]-\sigma_a(\nu) I(\nu,\vec\Omega) \\
+\int_{0}^{\infty}d\nu'\int_{4\pi}d\vec\Omega'\frac{\nu}{\nu'}\sigma_s(\nu'\rightarrow\nu,\vec\Omega'\cdot\vec\Omega)I(\nu',\vec\Omega')[1+\frac{c^2I(\nu,\vec \Omega)}{2h\nu^3}]\\
-\int_{0}^{\infty}d\nu'\int_{4\pi}d\vec\Omega' \sigma_s(\nu\rightarrow\nu',\vec\Omega\cdot\vec\Omega')I(\nu,\vec\Omega)[1+\frac{c^2I(\nu',\vec \Omega')}{2h\nu^{'3}}]
$$

### 输运方程的定解条件

#### 边界条件

$$
I(\vec r^s,\nu,\vec\Omega,t)=\Gamma(\vec r^s,\nu,\vec\Omega,t),\quad \vec n\cdot\vec \Omega<0
$$
若边界无辐射能流，则为真空边界条件
$$
I(\vec r^s,\nu,\vec\Omega,t)=0,\quad \vec n\cdot\vec \Omega<0
$$
#### 初始条件

$$
I(\vec r,\nu,\vec\Omega,0)=\Lambda(\vec r,\nu,\vec\Omega)
$$
## 局域热平衡下的辐射输运方程

### 基尔霍夫定律

辐射输运方程的源项在局域热平衡的条件下可以大大简化。当系统处于完全热力学平衡时，散射项相互抵消，吸收项相互抵消，吸收项目等于发射项，这时辐射的强度是普朗克分布，由系统的温度决定，即
$$
j(v)[1+\frac{c^2B(\nu,T)}{2h\nu^3}]=\sigma_a(\nu) B(\nu,T)
$$
整理可以得到
$$
j(v)=\frac{\sigma_a(\nu) B(\nu,T)}{1+\frac{c^2}{2h\nu^3}B(\nu,T)}
$$
这就是所为的基尔霍夫定律。

### 局域热平衡带来的简化

这就得到了物质的发射率，这对于辐射场与物质没有完全热力学平衡的情况仍然是成立的，进一步忽略掉散射过程，则可以得到局域热零平衡下的辐射输运方程为
$$
\frac{1}{c}\frac{\partial I(\nu,\vec \Omega)}{\partial t}+\vec\Omega\cdot\nabla I(\nu,\vec\Omega)=\frac{\sigma_a(\nu) B(\nu,T)}{1+\frac{c^2}{2h\nu^3}B(\nu,T)}[1+\frac{c^2I(\nu,\vec \Omega)}{2h\nu^3}]-\sigma_a(\nu) I(\nu,\vec\Omega)
$$
化简可得
$$
\frac{1}{c}\frac{\partial I(\nu,\vec \Omega)}{\partial t}+\vec\Omega\cdot\nabla I(\nu,\vec\Omega)=\sigma'_a(\nu) B(\nu,T)-\sigma'_a(\nu) I(\nu,\vec\Omega)
$$
其中
$$
\sigma'_a(\nu)=\frac{\sigma_a(\nu)}{1+\frac{c^2}{2h\nu^3}B(\nu,T)}=(1-e^{-\frac{h\nu}{kT}})\sigma_a(\nu)
$$
人们更喜欢使用$\rho\chi'_a$的形式，即
$$
\frac{1}{c}\frac{\partial I(\nu,\vec \Omega)}{\partial t}+\vec\Omega\cdot\nabla I(\nu,\vec\Omega)=\rho\chi'_a(\nu) B(\nu,T)-\rho\chi'_a(\nu) I(\nu,\vec\Omega)
$$
后面讨论的各种近似描述就是建立在这个简化版本的辐射输运方程的基础之上的。

## 辐射输运方程的扩散近似

### 扩散近似

辐射强度在几乎是各向同性的情况下，可以将辐射强度近似表示成为
$$
I(\vec r,\nu,\vec \Omega,t)=\frac{1}{4\pi}I_0(\vec r,\nu,t)+\frac{3}{4\pi}\vec\Omega\cdot\vec I_1(\vec r,\nu,t)
$$
根据数学关系式
$$
\int d\vec\Omega=4\pi,\ \int\vec \Omega d \vec \Omega=0, \int \vec \Omega \vec \Omega\cdot\vec A d\vec \Omega=\frac{4\pi}{3}\vec A
$$
可得到
$$
I_0(\vec r,\nu,t)=\int_{4\pi} d\vec\Omega I(\vec r,\nu,\vec \Omega,t)=cU(\vec r,\nu,t)\\
\vec I_1(\vec r,\nu,t)=\int_{4\pi}\vec\Omega d\vec\Omega I(\vec r,\nu,\vec \Omega,t)=\vec F
$$
即$I_o/c$和$\vec I_1$分别代表频率$\nu$上辐射场的能量密度和能流。将上述表达式代入
$$
\frac{1}{c}\frac{\partial I(\nu,\vec \Omega)}{\partial t}+\vec\Omega\cdot\nabla I(\nu,\vec\Omega)=\rho\chi'_a(\nu) B(\nu,T)-\rho\chi'_a(\nu) I(\nu,\vec\Omega)
$$
对立体角积分可得
$$
\frac{1}{c}\frac{\partial I_0}{\partial t}+\nabla\cdot\vec I_1(\nu)=\rho\chi'_a(\nu) [4\pi B(\nu,T)-I_0(\nu)]
$$
乘以$\vec\Omega$对立体角积分可得
$$
\frac{1}{c}\frac{\partial \vec I_1(\nu)}{\partial t}+\frac{1}{3}\nabla I_0(\nu)=-\rho\chi'_a(\nu) \vec I_1(\nu)
$$
将上式中$\frac{1}{c}\frac{\partial \vec I_1(\nu)}{\partial t}$忽略，即可得到
$$
\vec I_1(\nu)=-\frac{1}{3\rho\chi'_a(\nu)}\nabla I_0(\nu)
$$
在将此式带入$I_0$的方程得
$$
\frac{1}{c}\frac{\partial I_0}{\partial t}-\nabla\cdot[\frac{1}{3\rho\chi'_a(\nu)}\nabla I_0(\nu)]=\rho\chi'_a(\nu) [4\pi B(\nu,T)-I_0(\nu)]
$$

### 平衡扩散近似

当辐射场与电子达到完全得局域热平衡后，电子温度与辐射场温度相等，电子与辐射扩散方程得右端项为0，即
$$
I_0(\nu)=4\pi B(\nu,T)=\frac{8\pi h\nu^3}{c^2}(e^{h\nu/kT}-1)^{-1}
$$
将其带入扩散近似方程则有
$$
\frac{4\pi}{c}\frac{\partial B(\nu,T)}{\partial t}-\nabla\cdot[\frac{4\pi}{3\rho\chi'_a(\nu)}\nabla B(\nu,T)]=0
$$
此时我们可以得到辐射场能量密度
$$
E_r=U_p=\frac{4\pi}{c}\int_0^\infty B(\nu,T)d\nu=aT^4 \\
$$
辐射场能流
$$
\vec F=-\frac{4\pi}{3}\int_0^\infty \frac{1}{\rho\chi'_a(\nu)}\frac{\partial B(\nu,T)}{\partial T}d\nu\nabla T\\
=-\frac{4\pi}{3}\nabla T\frac{\int_0^\infty \frac{1}{\rho\chi'_a(\nu)}\frac{\partial B(\nu,T)}{\partial T}d\nu}{\int_0^\infty \frac{\partial B(\nu,T)}{\partial T}d\nu}
\int_0^\infty \frac{\partial B(\nu,T)}{\partial T}d\nu \\
=-\frac{4}{3}acl_RT^3\nabla T
=\frac{1}{3}l_Rc\nabla E_r\\
E_r=aT^4\\
$$
其中$l_R$为Rosseland平均自由程如下
$$
l_R=\frac{\int_0^\infty \frac{1}{\rho\chi'_a(\nu)}\frac{\partial B(\nu,T)}{\partial T}d\nu}{\int_0^\infty \frac{\partial B(\nu,T)}{\partial T}d\nu}
$$
则辐射扩散方程为
$$
\frac{\partial E_r}{\partial t}=\nabla\cdot(\frac{1}{3}l_Rc\nabla E_r)\\
$$
或
$$
\frac{\partial aT^4}{\partial t}=\nabla\cdot(\kappa_r\nabla T)\\
\kappa_r=\frac{4}{3}acl_RT^3
$$

### 非平衡扩散近似

若辐射场达到局域热平衡，但与电子为达到平衡，即$T_r\ne T_e$，则有
$$
I_0(\nu)=4\pi B(\nu,T_r)=\frac{8\pi h\nu^3}{c^2}(e^{h\nu/kT}-1)^{-1}
$$
将其带入辐射扩散方程，可得
$$
\frac{4\pi}{c}\frac{\partial B(\nu,Tr)}{\partial t}-\nabla\cdot[\frac{4\pi}{3\rho\chi'_a(\nu,T_e)}\nabla B(\nu,T_r)]=4\pi\rho[\chi’_a (\nu,T_e)B(\nu,T_e)-\chi’_a(\nu,T_e) B(\nu,T_r)]
$$
对其关于$\nu$进行积分，

其中辐射能量密度为
$$
E_r(T_r)=U_p(T_r)=\frac{4\pi}{c}\int_0^\infty B(\nu,T_r)d\nu=aT_r^4 \\
$$
辐射能流为
$$
\vec F=-\frac{4\pi}{3}\int_0^\infty \frac{1}{\rho\chi'_a(\nu，T_e)}\frac{\partial B(\nu,T_r)}{\partial T_r}d\nu\nabla T_r\\
=-\frac{4\pi}{3}\nabla T_r\frac{\int_0^\infty \frac{1}{\rho\chi'_a(\nu,T_e)}\frac{\partial B(\nu,T_r)}{\partial T_r}d\nu}{\int_0^\infty \frac{\partial B(\nu,T_r)}{\partial T_r}d\nu}
\int_0^\infty \frac{\partial B(\nu,T_r)}{\partial T_r}d\nu \\
=-\frac{4}{3}acl_R^{}T_r^3\nabla T_r\\
=\frac{1}{3}l_Rc\nabla E_r\\
E_r=aT_r^4\\
$$
其中$l_R(T_e,T_r)$为Rosseland平均自由程如下
$$
l_R(T_e,T_r)=\frac{\int_0^\infty \frac{1}{\rho\chi'_a(\nu,T_e)}\frac{\partial B(\nu,T_r)}{\partial T_r}d\nu}{\int_0^\infty \frac{\partial B(\nu,T_r)}{\partial T_r}d\nu}
$$
电子和辐射场能量交换
$$
4\pi\rho\int_0^\infty[\chi’_a(\nu,T_e) B(\nu,T_e)-\chi’_a (\nu,T_e)B(\nu,T_r)]d\nu\\
=4\pi\rho\frac{\int_0^\infty\chi’_a(\nu,T_e) B(\nu,T_e)d\nu}{\int_0^\infty B(\nu,T_e)d\nu}\int_0^\infty B(\nu,T_e)d\nu-
4\pi\rho\frac{\int_0^\infty\chi’_a(\nu,T_e) B(\nu,T_r)d\nu}{\int_0^\infty B(\nu,T_r)d\nu}\int_0^\infty B(\nu,T_r)d\nu\\
=c\frac{\int_0^\infty\rho\chi’_a(\nu,T_e) B(\nu,T_e)d\nu}{\int_0^\infty B(\nu,T_e)d\nu}aT_e^4-
c\frac{\int_0^\infty\rho\chi’_a(\nu,T_e) B(\nu,T_r)d\nu}{\int_0^\infty B(\nu,T_r)d\nu}aT_r^4\\
=cl_P^{-1}(T_e)aT_e^4-cl_P^{-1}(T_e,T_r)aT_r^4
$$
其中
$$
l_P^{-1}(T_e)=\frac{\int_0^\infty\rho\chi’_a(\nu,T_e) B(\nu,T_e)d\nu}{\int_0^\infty B(\nu,T_e)d\nu}\\
l_P^{-1}(T_e,T_r)=\frac{\int_0^\infty\rho\chi’_a(\nu,T_e) B(\nu,T_r)d\nu}{\int_0^\infty B(\nu,T_r)d\nu}
$$
为Planck平均自由程。

因此扩散方程如下
$$
\frac{\partial E_r}{\partial t}-\nabla\cdot[\frac{cl_R(T_e,T_r)}{3}\nabla E_r]=
cl_P^{-1}(T_e)aT_e^4-cl_P^{-1}(T_e,T_r)E_r
$$
Rosseland平均自由程$l_R(T_e,T_r)$和Planck平均自由程$l_P^{-1}(T_e,T_r)$都是$T_e$和$T_r$的函数，通常取如下近似
$$
l_R(T_e,T_r)\approx l_R(T_e)=\frac{\int_0^\infty \frac{1}{\rho\chi'_a(\nu,T_e)}\frac{\partial B(\nu,T_e)}{\partial T_e}d\nu}{\int_0^\infty \frac{\partial B(\nu,T_e)}{\partial T_e}d\nu}\\
l_P^{-1}(T_e,T_r)\approx l_P^{-1}(T_e)=\frac{\int_0^\infty\rho\chi’_a(\nu,T_e) B(\nu,T_e)d\nu}{\int_0^\infty B(\nu,T_e)d\nu}\\
$$
因此扩散方程可以写成
$$
\frac{\partial E_r}{\partial t}-\nabla\cdot(D_r\nabla E_r)=
\tau_{er}^{-1}(aT_e^4-E_r)\\
D_r=\frac{cl_R(T_e)}{3}\\
\tau_{er}^{-1}=cl_P^{-1}(T_e)
$$

### 多群扩散近似

考虑辐射输运方程
$$
\frac{1}{c}\frac{\partial I(\nu,\vec \Omega)}{\partial t}+\vec\Omega\cdot\nabla I(\nu,\vec\Omega)=\rho\chi'_a(\nu) B(\nu,T)-\rho\chi'_a(\nu) I(\nu,\vec\Omega)
$$
将频率范围$[0,\infty]$按照$0=\nu_0<\nu_1<\nu_2<...<\nu_{n-1}<\nu_g=\infty$分成n个群，其中第$g$个群区间为$[\nu_{g-1},\nu_g]$。

定义第$g$群的辐射强度定义为
$$
I_g(\vec \Omega)=\int_{\nu_{g-1}}^{\nu_g}I(\nu,\vec \Omega)d\nu,\ \ 1\le g\le n
$$
将辐射输运方程对第g群积分，可得
$$
\frac{1}{c}\frac{\partial I_g(\vec \Omega)}{\partial t}+\vec\Omega\cdot\nabla I_g(\vec\Omega)=\rho\chi'_{ag}[ B_g(T)-I_g(\vec\Omega)]
$$
其中
$$
\rho\chi'_{ag}=\frac{\int_0^\infty \rho\chi'_{ag}[B(\nu,T)-I(\nu,\vec\Omega)]d\nu}{\int_0^\infty[B(\nu,T)-I(\nu,\vec\Omega)]d\nu}
$$
对第$g$个群的辐射输运方程进行扩散近似
$$
I_g(\vec \Omega)=\frac{1}{4\pi}I_{0g}+\frac{3}{4\pi}\vec\Omega\cdot\vec I_{1g}
$$
假设$\rho\chi'_{ag}$与$\vec \Omega$无关，在对第$g$群关于立体角进行积分，可得
$$
\frac{1}{c}\frac{\partial I_{0g}}{\partial t}+\nabla\cdot\vec I_{1g}=\rho\chi'_a(\nu) [4\pi B_g(T)-I_{0g}]
$$
对第$g$群乘以$\vec \Omega$关于立体角进行积分
$$
\frac{1}{c}\frac{\partial \vec I_{1g}}{\partial t}+\frac{1}{3}\nabla I_{0g}=-\rho\chi'_a(\nu) \vec I_{1g}
$$
将上式中$\frac{1}{c}\frac{\partial \vec I_{1g}}{\partial t}$忽略，即可得到
$$
\vec I_{1g}=-\frac{1}{3\rho\chi'_{ag}}\nabla I_{0g}
$$
将其带入$I_{0g}$方程
$$
\frac{1}{c}\frac{\partial I_{0g}}{\partial t}-\nabla\cdot[\frac{1}{3\rho\chi'_{ag}}\nabla I_{0g}]=\rho\chi'_{ag} [4\pi B_g(T)-I_{0g}]
$$
根据定义$I_{0g}=cE_g$，上述方程应为
$$
\frac{\partial E_{g}}{\partial t}-\nabla\cdot[\frac{c}{3\rho\chi'_{ag}}\nabla E_{g}]=\rho\chi'_{ag}c [\frac{4\pi}{c} B_g(T)-E_{g}]
$$
其中
$$
\frac{4\pi}{c} B_g(T)=\int_{\nu_{g-1}}^{\nu_g} \frac{8\pi h\nu^3}{c^3}(e^{\frac{h\nu}{kT}}-1)^{-1} d\nu
$$
设$x=\frac{h \nu}{kT}$，则有
$$
\frac{4\pi}{c} B_g(T)=\frac{15}{\pi^4}aT^4\int_{x_{g-1}}^{x_g}\frac{x^3}{e^x-1}dx\\
=\frac{15}{\pi^4}b_gaT^4\\
$$
其中$b_g$为
$$
b_g=\int_{x_{g-1}}^{x_g}\frac{x^3}{e^x-1}dx,\ \  x_{g-1}=\frac{hv_{g-1}}{kT},\  x_{g}=\frac{hv_{g}}{kT}
$$
对于方程中的两处$\rho\chi'_{ag}$通常分别Rosseland平均和Planck平均，即
$$
l_{Rg}=\frac{\int_{\nu_{g-1}}^{\nu_g} \frac{1}{\rho\chi'_a(\nu)}\frac{\partial B(\nu,T)}{\partial T}d\nu}{\int_{\nu_{g-1}}^{\nu_g} \frac{\partial B(\nu,T)}{\partial T}d\nu}\\
l_{Pg}^{-1}=\frac{\int_{\nu_{g-1}}^{\nu_g}\rho\chi’_a(\nu) B(\nu,T)d\nu}{\int_{\nu_{g-1}}^{\nu_g} B(\nu,T)d\nu}
$$
则多群辐射方程为
$$
\frac{\partial E_{g}}{\partial t}-\nabla\cdot[\frac{l_{Rg}c}{3}\nabla E_{g}]=\frac{c}{l_{Pg}} [\frac{15}{\pi^4}b_gaT^4-E_{g}]\\
$$
进一步化简可得
$$
\frac{\partial E_{g}}{\partial t}-\nabla\cdot[D_{rg}\nabla E_{g}]=\tau_{erg}^{-1}[\frac{15}{\pi^4}b_gaT^4-E_{g}]\\
D_{rg}=\frac{l_{Rg}c}{3}\\
\tau_{erg}^{-1}=\frac{c}{l_{Pg}}
$$

## 不透明度

$$
\rho\chi_v^{'ff}=\frac{4\sqrt{2\pi}e^6}{3\sqrt{3}hcm_e^{{3/2}}}g_{ff}n_i n_e Z^2T_e^{-\frac{1}{2}}\nu^{-3}(1-e^{-\frac{h\nu}{kt}})
$$



其中$g_{ff}$为Gaunt因子，表示量子力学的修正。考虑完全电离的等离子体，$n_i=\rho/(Am_p)$，$n_e=Z\rho/(Am_p)$，$A$为离子的质量数，$Z$为荷电荷数，则有
$$
\rho\chi_v^{'ff}=\frac{4\sqrt{2\pi}e^6}{3\sqrt{3}hcm_e^{3/2}m_p^2}g_{ff}\frac{\rho^2Z^3}{A^2}(kT_e)^{-\frac{1}{2}}\nu^{-3}(1-e^{-\frac{h\nu}{kt}})
$$
已知
$$
B(\nu,T)=\frac{2h\nu^3}{c^2}(e^{h\nu/kT}-1)^{-1}\\
\frac{\partial B(\nu,T)}{\partial T}=\frac{2h^2\nu^4}{c^2kT^2}\frac{e^{h\nu/kT}}{(e^{h\nu/kT}-1)^2}
$$

### Rosseland不透明度

则Rosseland平均自由程为
$$
l_R(T)=\frac{\int_0^\infty \frac{1}{\rho\chi'_a(\nu,T)}\frac{\partial B(\nu,T)}{\partial T}d\nu}{\int_0^\infty \frac{\partial B(\nu,T)}{\partial T}d\nu}\\
=\frac{3\sqrt{3}hcm_e^{3/2}m_p^2}{4\sqrt{2\pi}e^6g_{ff}}
\frac{A^2}{\rho^2Z^3}\frac{\int_0^\infty
(kT)^{\frac{1}{2}}\nu^{3}
\frac{e^{h\nu/kT}}{(e^{h\nu/kT}-1)}
\frac{2h^2\nu^4}{c^2kT^2}\frac{e^{h\nu/kT}}{(e^{h\nu/kT}-1)^2}d\nu}
{\int_0^\infty \frac{2h^2\nu^4}{c^2kT^2}
\frac{e^{h\nu/kT}}{(e^{h\nu/kT}-1)^2}d\nu}\\
=\frac{3\sqrt{3}hcm_e^{3/2}m_p^2}{4\sqrt{2\pi}e^6g_{ff}}
\frac{A^2}{\rho^2Z^3}\frac{\int_0^\infty
(kT)^{\frac{1}{2}}\nu^{3}
\frac{e^{h\nu/kT}}{(e^{h\nu/kT}-1)}
\frac{2h^2\nu^4}{c^2kT^2}\frac{e^{h\nu/kT}}{(e^{h\nu/kT}-1)^2}d\nu}
{\frac{8k^4\pi^4T^3}{15c^2h^3}}\\
=\frac{3\sqrt{3}hcm_e^{3/2}m_p^2}{4\sqrt{2\pi}e^6g_{ff}}
\frac{15h^5}{4\pi^4(kT)^{9/2}}
\frac{A^2}{\rho^2Z^3}
\int_0^\infty
\frac{\nu^7e^{2h\nu/kT}}{(e^{h\nu/kT}-1)^3}d\nu
$$
若设$x=\frac{h\nu}{kT}$，则有
$$
l_R(T)=\frac{3\sqrt{3}hcm_e^{3/2}m_p^2}{4\sqrt{2\pi}e^6g_{ff}}
\frac{15h^5}{4\pi^4(kT)^{9/2}}
(\frac{kT}{h})^8
\frac{A^2}{\rho^2Z^3}
\int_0^\infty
\frac{x^7e^{2x}}{(e^{x}-1)^3}dx\\
=\frac{45\sqrt{3}cm_e^{3/2}m_p^2}{16\sqrt{2}\pi^{9/2}h^2e^6g_{ff}}
\frac{A^2(kT)^{7/2}}{\rho^2Z^3}
\int_0^\infty
\frac{x^7e^{2x}}{(e^{x}-1)^3}dx
$$
其中积分项
$$
\int_0^\infty
\frac{x^7e^{2x}}{(e^{x}-1)^3}dx=\frac{8}{3}[\pi^6+945\zeta(7)]
$$
可得
$$
l_R(T)
=\frac{15\sqrt{3}[\pi^6+945\zeta(7)]cm_e^{3/2}m_p^2}{2\sqrt{2}\pi^{9/2}h^2e^6g_{ff}}
\frac{A^2(kT)^{7/2}}{\rho^2Z^3}
$$
取$g_{ff}=1.0$，带入物理常量，可得
$$
l_R\approx71.71\frac{A^2(kT)^{7/2}}{\rho^2Z^3}
$$
其中$l_R$单位是$cm$，$kT$单位是$keV$，$\rho$单位是$g/cm^3$。

### Planck不透明度

Planck平均自由程
$$
l_P^{-1}(T)=\frac{\int_0^\infty\rho\chi’_a(\nu,T) B(\nu,T)d\nu}{\int_0^\infty B(\nu,T)d\nu}\\
=\frac{4\sqrt{2\pi}e^6g_{ff}}{3\sqrt{3}hcm_e^{3/2}m_p^2}\frac{\rho^2Z^3}{A^2}
\frac{\int_0^\infty (kT_e)^{-\frac{1}{2}}\nu^{-3}(1-e^{-\frac{h\nu}{kt}}) \frac{2h\nu^3}{c^2}(e^{h\nu/kT}-1)^{-1}d\nu}
{\int_0^\infty \frac{2h\nu^3}{c^2}(e^{h\nu/kT}-1)^{-1} d\nu}\\
=\frac{4\sqrt{2\pi}e^6g_{ff}}{3\sqrt{3}hcm_e^{3/2}m_p^2}
\frac{15 h^4}{\pi^4}(kT)^{-9/2}
\frac{\rho^2Z^3}{A^2}
\int_0^\infty e^{-\frac{h\nu}{kT}}d\nu\\
=\frac{4\sqrt{2\pi}e^6g_{ff}}{3\sqrt{3}hcm_e^{3/2}m_p^2}
\frac{15 h^3}{\pi^4}(kT)^{-7/2}
\frac{\rho^2Z^3}{A^2}
\int_0^\infty e^{-x}dx\\
=\frac{20\sqrt{2\pi}h^2e^6g_{ff}}{\sqrt{3}\pi^4cm_e^{3/2}m_p^2}
\frac{\rho^2Z^3}{A^2(kT)^{7/2}}
$$
取$g_{ff}=1.0$，带入物理常量，可得
$$
l_P^{-1}=0.422\frac{\rho^2Z^3}{A^2(kT)^{7/2}}
$$
其中$l_R$单位是$cm$，$kT$单位是$keV$，$\rho$单位是$g/cm^3$。

### 多群扩散中的不透明度

则Rosseland平均自由程为
$$
l_{Rg}
=\frac{45\sqrt{3}cm_e^{3/2}m_p^2}{16\sqrt{2}\pi^{9/2}h^2e^6g_{ff}}
\frac{A^2(kT)^{7/2}}{\rho^2Z^3}
\int_{x_{g-1}}^{x_g}
\frac{x^7e^{2x}}{(e^{x}-1)^3}dx
$$
Planck平均自由程
$$
l_{Pg}^{-1}
=\frac{4\sqrt{2\pi}e^6g_{ff}}{3\sqrt{3}hcm_e^{3/2}m_p^2}
\frac{15 h^3}{\pi^4}
\frac{\rho^2Z^3}{A^2(kT)^{7/2}}
\int_{x_{g-1}}^{x_g} e^{-x}dx\\
=\frac{4\sqrt{2\pi}e^6g_{ff}}{3\sqrt{3}hcm_e^{3/2}m_p^2}
\frac{15 h^3}{\pi^4}
\frac{\rho^2Z^3}{A^2(kT)^{7/2}}
(e^{-x_{g-1}}-e^{-x_{g}})
$$
