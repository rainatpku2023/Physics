中心力场中粒子运动的一般性质
角动量守恒与径向方程
● 设质量为$\mu$的粒子在中心势$V(r)$中运动，则$\mathrm{Hamilton}$量的表达式为：
$\hat{H} = \frac{\hat{p}^2}{2\mu}+V(r) = -\frac{\hbar^2}{2\mu}\nabla^2 + V(r)$
● 不难证明，角动量$\hat{l} = \hat{r}\times\hat{p}$也是守恒量，即：
$[\hat{l},\hat{H}] = 0$
● 在球坐标下，给出动量平方算符$\hat{p}^2$的几个等价的表达式：
$\hat{p}^2 = -\hbar^2\nabla^2 = -\frac{\hbar^2}{r^2}\frac{\partial}{\partial r}\left(r^2\frac{\partial}{\partial r}\right) + \frac{\hat{l}^2}{r^2}$
$=-\hbar^2 \left[\frac{\partial^2}{\partial r^2} + \frac{2}{r}\frac{\partial}{\partial r}\right]+\frac{\hat{l}^2}{r^2} = -\frac{\hbar^2}{r}\frac{\partial^2}{\partial r^2}r+\frac{\hat{l}^2}{r^2}$
  ○ 其中：
$\hat{l}^2 = -\hbar^2 \left[\frac{1}{\sin\theta} \frac{\partial}{\partial\theta}\left(\sin\theta \frac{\partial}{\partial\theta}\right) + \frac{1}{\sin^2\theta}\frac{\partial^2}{\partial\phi^2}\right]$
$=-\frac{\hbar^2}{\sin\theta}\frac{\partial}{\partial \theta} \left(\sin\theta \frac{\partial}{\partial\theta}\right) + \frac{1}{\sin^2\theta}\hat{l}_z^2$
● 角动量平方算符与$\hat{l}_z$的正交归一完备共同本征函数组为：
$Y_{lm}(\theta,\phi) = (-1)^m \sqrt{\frac{2l+1}{4\pi}\frac{(l-m)!}{(l+m)!}} P_{l}^{m}(\cos\theta)e^{im\phi}$
  ○ $l = 0,1,2,3,...$
  ○ $m = l,l-1,...,-l+1,-l$
● 本征函数满足：
$\hat{l}^2 Y_{lm} = l(l+1)\hbar^2Y_{lm}$
$\hat{l}_z Y_{lm} = m\hbar Y_{lm}$
$\int_{0}^{2\pi} d\phi \int_{0}^{\pi}\sin\theta d\theta Y_{lm}^*(\theta,\phi)Y_{kn}(\theta,\phi) = \delta_{mn}\delta_{kl}$
● 分离变量过程可以参考：
● 对应的定态$\mathrm{Schr\ddot{o}dinger}$方程/能量本征方程可以写为：
$\left[-\frac{\hbar^2}{2\mu}\frac{1}{r}\frac{\partial^2}{\partial r^2}r+\frac{\hat{l}^2}{2\mu r^2}+V(r)\right]\psi = E\psi$
  ○ 第一项称为径向动能算符。
  ○ 第二项称为离心势能。
● 能量本征方程可以选取为$(\hat{H},\hat{l}^2,\hat{l}_z)$的共同本征态，即：
$\boxed{\phi(r,\theta,\phi) = R_l(r)Y_{lm}(\theta,\phi), l = 0,1,2,3,...}$
$m= -l,-l+1,...,l-1,l$
  ○ 此时代入，得：
$\left[-\frac{\hbar^2}{2\mu}\left(\frac{\partial^2}{\partial r^2} + \frac{2}{r}\frac{\partial}{\partial r}\right)+\frac{l(l+1)\hbar^2}{2\mu r^2}+V(r)\right]R_l(r) = ER_l(r)$
  ○ 移项，两边同时乘以$2\mu/\hbar^2$，剩下的径向方程为：
$\boxed{R''_l(r) +\frac{2}{r}R'_l(r) + \left[\frac{2\mu}{\hbar^2}\left(E-V(r)\right)-\frac{l(l+1)}{r^2}\right]R_l(r)=0}$
  ○ 推导过程中需要注意分子分母以及正负号的转换。
束缚态下径向方程的求解
● 前文得到径向方程，在束缚态下，能量$E$的本征值和角动量量子数$l$以及节点数$n_r$都有关。
  ○ 而且$l$一定，$n_r$增大，能量$E_{n_r l}$也增大。
  ○ 人们根据$l$的大小进行编号，根据原子光谱学的习惯：
$l = 0,1,2,3,4,5,6,...$
  ○ 对应的态分别为：
$s,p,d,f,g,h,i,...$
【空白】渐进行为
两体问题转化为单体问题
● 中心力场问题往往是两体问题，这个时候相对运动对应的$\mathrm{Schr\ddot{o}dinger}$方程是求解的重点。
● 我们考虑能量本征方程：
$\left[-\frac{\hbar^2}{2m_1}\nabla_1^2-\frac{\hbar^2}{2m_2}\nabla_1^2 +V(|\vec{r}_1-\vec{r}_2|)\right]\Psi(\vec{r}_1,\vec{r}_2) = E_{\text{(total)}}\Psi(\vec{r}_1,\vec{r}_2)$
● 此时引入质心坐标$\vec{R}$和相对坐标$\vec{r}$：
$\vec{R} = \frac{m_1 \vec{r}_1+m_2 \vec{r}_2}{m_1+m_2}$
$\vec{r} = \vec{r}_1-\vec{r}_2$
● 可以证明：
$\frac{1}{m_1}\nabla_1^2 + \frac{1}{m_2} \nabla_2^2=\frac{1}{M}\nabla_R^2 + \frac{1}{\mu} \nabla^2$
  ○ 其中：
$M = m_1+m_2$
$\mu = \frac{m_1 m_2}{m_1+m_2}$
$\nabla_R^2 = \frac{\partial^2}{\partial X^2}+\frac{\partial^2}{\partial Y^2}+\frac{\partial^2}{\partial Z^2}$
$\nabla^2 = \frac{\partial^2}{\partial x^2}+\frac{\partial^2}{\partial y^2}+\frac{\partial^2}{\partial z^2}$
● 此时，原来的方程可以改为：
$\left[-\frac{\hbar^2}{2M}\nabla_R^2  -\frac{\hbar^2}{2\mu}\nabla^2+V(r)\right]\Psi =E_T \Psi$
  ○ 这个方程可以变量分离：
$\Psi = \phi(\vec{R})\psi(\vec{r})$
● 分离变量得：
$-\frac{\hbar^2}{2M}\nabla_R^2 \phi(\vec{R}) = E_C \phi(\vec{R})$
$\left[ -\frac{\hbar^2}{2\mu}\nabla^2+V(r)\right]\psi =E \psi$
  ○ 其中：
$E = E_T - E_C$
● 这个式子就是相对运动的$\mathrm{Schr\ddot{o}dinger}$方程：
$\left[ -\frac{\hbar^2}{2\mu}\nabla^2+V(r)\right]\psi =E \psi$
$\mu = \frac{m_1 m_2}{m_1+m_2}$
无限深球方势阱
【空白】求解过程
【空白】求解结果
【空白】能级简并度与对称性
三维各向同性谐振子
求解过程
● 求解径向波函数$R(r)$的主要步骤就是：
  ○ 先考虑极限行为：在趋于零时是$r^l$的行为，趋于无穷时是$e^{-r^2/2}$的行为。
  ○ 将上面两个部分分离出来$R(r) = r^l e^{-r^2/2} u(r)$。
  ○ 然后列出$u(r)$满足的方程，并令$\xi = r^2$，写出$U(\xi)$满足的方程，进行求解。
  ○ 最终给出径向波函数$R(r) = r^l e^{-r^2/2} U(\xi(r)) = r^l e^{-r^2/2} u(r)$

求解结果
● 三维各向同性谐振子的能量本征值为：
$E = (2n_r + l + \frac{3}{2})\hbar \omega$
$n_r,l = 0,1,2,3,...$
  ○ 令$N = 2n_r+l$，那么有：
$E = (N+\frac{3}{2})\hbar \omega$
$N = 0,1,2,3,...$
● 归一化径向波函数为：
$R_{n_rl}(r) = N_{n_rl} \cdot (\alpha r)^l e^{-\alpha^2 r^2 / 2} F(-n_r, l + 3/2, \alpha^2 r^2)$
  ○ 其中：
    ■ $n_r$：径向量子数($n_r = 0, 1, 2, \dots$)。
    ■ $l$：角量子数。
    ■ $\alpha$：长度参数的倒数，定义为 $\alpha = \sqrt{\mu\omega/\hbar}$。
    ■ $F(-n_r, l + 3/2, \alpha^2 r^2)$：合流超几何多项式（当第一个参数为负整数 $-n_r$ 时，它退化为次数为 $n_r$ 的多项式，与广义拉盖尔多项式相关）。
    ■ 归一化系数：
$N_{n_rl} = \alpha^{3/2} \left[ \frac{2^{l+2-n_r} (2l + 2n_r + 1)!!}{\sqrt{\pi} n_r! [(2l + 1)!!]^2} \right]^{1/2}$
  ○ 整体可以明显写为：
$R_{n_rl}(r) =  \alpha^{3/2} \left[ \frac{2^{l+2-n_r} (2l + 2n_r + 1)!!}{\sqrt{\pi} n_r! [(2l + 1)!!]^2} \right]^{1/2} (\alpha r)^l e^{-\alpha^2 r^2 / 2} F(-n_r, l + 3/2, \alpha^2 r^2)$
  ○ 或者：
$R_{N, l}(r) = \sqrt{\frac{2^{ \frac{N-l}{2} + l + 2 } (\frac{N+l+1}{2})!! \alpha^3}{\sqrt{\pi} (\frac{N-l}{2})! [(2l+1)!!]^2}} \cdot (\alpha r)^l e^{-\frac{1}{2}\alpha^2 r^2} F\left(-\frac{N-l}{2}, l + \frac{3}{2}, \alpha^2 r^2\right)$
$R_{N, l}(r) = \sqrt{\frac{2^{n_r+l+2} n_r! \alpha^3}{\sqrt{\pi} (2n_r+2l+1)!!}} (\alpha r)^l e^{-\frac{1}{2}\alpha^2 r^2} L_{n_r}^{l+1/2}(\alpha^2 r^2)$

能级简并度与对称性
● 能级简并度为：
$f_N = \sum_{l=0,2,...,N}(2l+1) = \frac{1}{2}(N+1)(N+2)$


Cartesian坐标系中求解
● 其实就是把波函数分离变量到$x,y,z$三个方向上，比较简单，直接放书上的结果：

● 能级有简并的情形，能量本征函数组的是不唯一的。
  ○ 选取不同的对易守恒量完全集，对应的时共同本征态就不同。

氢原子
求解过程
https://dengbaiyu2023.yuque.com/org-wiki-dengbaiyu2023-vsgo6q/nsycge/kbkfkqf6uvb1x73w
求解结果
● 氢原子的能量本征值为：
$\boxed{E = E_n = -\frac{\mu e^4}{2\hbar^2} \frac{1}{n^2} = -\frac{e^2}{2a}\frac{1}{n^2}}$
$n = 1,2,3,...$
  ○ 其中玻尔半径$a$表达式为：
$a = \frac{\hbar^2}{\mu e^2}$
● 相应地，归一化径向波函数的表达式为：
$R_{nl}(r) = N_{nl} e^{-\xi/2}\mathrm{F}(-n+l+1,2l+2,\xi)$
$l  = 0,1,2,...,n-1$
  ○ 其中：
$\xi = \frac{2r}{na}$
$N_{nl} = \frac{2}{a^{3/2}n^2(2l+1)!}\sqrt{\frac{(n+l)!}{(n-l-1)!}}$
$\mathrm{F}(\alpha,\gamma,z) = 1+\frac{\alpha}{\gamma}z+\frac{\alpha(\alpha+1)}{\gamma(\gamma+1)}z^2+\cdots = \sum_{k=0}^{\infin} \frac{(\alpha)_k}{(\gamma)_k}\frac{z^k}{k!}$
  ○ 其中：
$(\alpha)_k := \alpha(\alpha+1)\cdots(\alpha+k-1)$
    ■ 的表示方法被称为$\mathrm{Pochhammer}$符号。
● 综上，归一化径向波函数可以明显地写为：
$\boxed{
R_{nl}(r) =\frac{2}{a^{3/2}n^2(2l+1)!}\sqrt{\frac{(n+l)!}{(n-l-1)!}} e^{-r/na}\mathrm{F}(-n+l+1,2l+2,\frac{2r}{na})}$
$l  = 0,1,2,...,n-1$
能级简并度与对称性
● 主量子数$n$，角量子数$l$，径向节点数$n_r$的关系为：
$n = n_r +l +1$
  ○ 因此，对于一个$n$总共有$n$个$l$的取值。
● 回顾拉普拉斯方程在球坐标系下的变量分离，对于磁量子数$m$有：
$m = -l,-l+1,...,l-1,l$
  ○ 可知对于每一个$l$，总共有$2l+1$个$m$的取值。
● 综上，属于能量$E_n$能级的量子态数目为：
$f_m = \sum_{l=0}^{n-1} (2l+1) = n^2$


径向位置概率分布
● 径向概率为：
$r^2dr \int d\Omega |\phi_{nlm}(r,\theta,\phi)|^2 = R_{nl}^2(r)r^2dr$
● 画图结果如下：

● 对于$1s,2p,3d,...$等等状态：
  ○ $1s:n=1,l=0,n_r=0$
  ○ $2p:n=2,l=1,n_r=0$
  ○ $3d:n=3,l=2,n_r=0$
  ○ 等等，$n_r = 0$径向波函数均不存在节点。
角度位置概率分布
● 在$\psi_{nlm}(r,\theta,\phi)$下，在立体角$d\Omega$中找到电子的概率为：
$|Y_{lm}(\theta,\phi)|^2d\Omega \propto |P_{l}^m(\theta,\phi)|^2d\Omega$

【空白】电流分布与磁矩
类氢离子
● 类氢离子的能级为：
$E_n = -\frac{\mu Z^2e^4}{2\hbar^2} \frac{1}{n^2} = -\frac{Z^2e^2}{2a}\frac{1}{n^2}$
$n = 1,2,3,...$$a = \frac{\hbar^2}{\mu e^2}$
【空白】合流超几何函数
