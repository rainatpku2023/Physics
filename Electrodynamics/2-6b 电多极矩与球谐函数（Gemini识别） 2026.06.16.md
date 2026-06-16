[2.6b多级展开补充-球坐标.pdf](https://dengbaiyu2023.yuque.com/attachments/yuque/0/2026/pdf/2371504/1775636369541-6826a5c3-f210-4ae3-bba6-66a9870cf571.pdf)

# 2.6b 多极展开补充-球坐标
> **Note**  
MinerU 识别宋慧超老师手稿生成，经过助教初步检查。  
纠错：2401110153@stu.pku.edu.cn  
最后更新时间：Mar. 24 2026
>

## （一） 电势在球坐标下的通用级数展开
对于远离局部电荷分布源（特征尺度为 $ a $）的场点（满足 $ r \gg a $），拉普拉斯方程的通解包含了沿径向向外衰减的多极展开项。电势可以写为球谐函数 $ Y_{lm}(\theta,\varphi) $ 构成的完备基底的线性叠加：

$ \phi(r,\theta,\varphi) = \sum_{l=0}^{\\infty}\sum_{m=-l}^{l} \frac{B_{lm}}{r^{l+1}} Y_{lm}(\theta,\varphi) \tag{1} $

根据静电场的积分表达式，真空中源分布 $ \rho(\vec{r}^{\prime}) $ 在外部空间激发的电势为：

$ \phi(\vec{r}) = \frac{1}{4\pi\epsilon_{0}}\int \frac{\rho(\vec{r}^{\prime})dV^{\prime}}{|\vec{r} - \vec{r}^{\prime}|} \tag{2} $

---

## （二） 球谐函数的加法原理与格林函数展开
为了将分母中的距离倒数分解到坐标分量上，我们引用**球谐函数的加法原理**。设场点 $ \vec{r}=(r,\theta,\varphi) $ 和源点 $ \vec{r}^{\prime}=(r^{\prime},\theta^{\prime},\varphi^{\prime}) $ 之间的夹角为 $ \gamma $，则有：

$ P_{l}(\cos\gamma) = \frac{4\pi}{2l+1}\sum_{m=-l}^{l} Y_{lm}^{*}(\theta^{\prime},\varphi^{\prime})Y_{lm}(\theta,\varphi) \tag{3} $

由于勒让德多项式 $ P_{l}(\cos\gamma) $ 具有正交完备性，三维空间的标量距离倒数（即自由空间格林函数）可以沿两点的夹角展开为：

$ \frac{1}{|\vec{r} - \vec{r}^{\prime}|} = \sum_{l=0}^{\infty} \frac{r^{\prime l}}{r^{l+1}} P_{l}(\cos\gamma) \quad (\text{当 } r > r^{\prime}) \tag{4} $

将加法原理公式 (3) 代入展开式 (4) 中，即可实现源点和场点坐标的**完全代数变量分离**：

$ \frac{1}{|\vec{r} - \vec{r}^{\prime}|} = 4\pi\sum_{l=0}^{\infty}\sum_{m=-l}^{l} \frac{1}{2l+1} \frac{r^{\prime l}}{r^{l+1}} Y_{lm}^{*}(\theta^{\prime},\varphi^{\prime})Y_{lm}(\theta,\varphi) \tag{5} $

---

## （三） 球坐标下的多极矩定义
将变量分离后的表达式 (5) 带回到静电势积分公式 (2) 中，并提取关于场点的项：

$ \phi(\vec{r}) = \frac{1}{4\pi\epsilon_{0}}\sum_{l=0}^{\infty}\sum_{m=-l}^{l} \frac{4\pi}{2l+1} \left[ \int Y_{lm}^{*}(\theta^{\prime},\varphi^{\prime})r^{\prime l}\rho(\vec{r}^{\prime})dV^{\prime} \right] \frac{Y_{lm}(\theta,\varphi)}{r^{l+1}} \tag{6} $

由此，我们可以定义球坐标系下的**球多极矩 (Spherical Multipole Moments)** $ q_{lm} $ 为：

$ q_{lm} = \int Y_{lm}^{*}(\theta^{\prime},\varphi^{\prime})r^{\prime l}\rho(\vec{r}^{\prime})dV^{\prime} \tag{7} $

### 常用低阶多极矩在直角坐标下的物理映射
我们可以将前几阶球多极矩的积分在直角坐标系中写出，以确定其明确的物理意义：

+ **单极矩 (**$ l=0, m=0 $**)**：  
由于 $ Y_{00} = \frac{1}{\sqrt{4\pi}} $，代入式 (7)：

$ q_{00} = \int \frac{1}{\sqrt{4\pi}}\rho(\vec{r}^{\prime})dV^{\prime} = \frac{1}{\sqrt{4\pi}}Q \quad (\text{其中 } Q \text{ 为体系的总电荷}) \tag{8} $

+ **偶极矩 (**$ l=1 $**)**：  
对应 $ m=-1,0,1 $，分别对应直角坐标系下电偶极矩矢量 $ \vec{p}=\int \vec{r}^{\prime}\rho(\vec{r}^{\prime})dV^{\prime} $ 的各分量组合。例如，对于 $ m=0 $：

$ Y_{10} = \sqrt{\frac{3}{4\pi}}\cos\theta^{\prime} \implies q_{10} = \sqrt{\frac{3}{4\pi}}\int r^{\prime}\cos\theta^{\prime}\rho(\vec{r}^{\prime})dV^{\prime} = \sqrt{\frac{3}{4\pi}}p_{z} \tag{9} $

这一套球多极展开理论在数学结构上极其优美，它将复杂的空间电荷分布通过一族离散的复本征系数 $ q_{lm} $ 完全精确表征。
