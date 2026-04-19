[lecture_17.pdf](https://dengbaiyu2023.yuque.com/attachments/yuque/0/2025/pdf/2371504/1747040490460-0f401eee-8dd3-49aa-aea3-9d2d9cb17916.pdf)

### Delta函数的定义
+ $ \mathrm{Delta} $函数的$ \mathrm{Dirac} $定义为：
    - 当$ x\neq0 $时：

$ \delta (x) =0 $

    - 对于任意的$ a<0<b $都有：

$ \int_{-\infin}^{+\infin}\delta (x)dx = 1 $

+ 定义$ n $维$ \mathrm{Delta} $函数定义为：

$ \delta^{(n)}(\vec{x}) =\delta(x_1)\delta(x_2)\cdots\delta(x_n) $

    - 其中$ x_1,x_2 \dots x_n $为$ \vec{x} $的所有分量。



### Delta函数的举例
#### 高斯脉冲
$ G_n(x) = \sqrt{\frac{n^2}{\pi}}\exp(-n^2x^2) $

#### 洛伦兹脉冲
$ L_n(x) = \frac{n}{\pi}\frac{1}{1+n^2 x^2} $

#### 正弦脉冲
$ S_n(x) = \frac{\sin(nx)}{\pi x} $

### Delta函数的性质
#### 量纲意义
+ $ \delta^{(n)}(\vec{x}) $的量纲为$ x $对应量纲的$ -n $次方。
+ $ \nabla^{n} $的量纲为作用对象对应量纲的$ -n $次方。

#### 对称性
$ \delta(x) = \delta(-x) $

+ 在高维上体现为旋转对称性

#### 与Heaviside阶跃函数的关系
$ \delta(x) = \frac{d}{dx}H(x) $

+ 其中$ H(x) $为$ \mathrm{Heaviside} $阶跃函数。

#### 伸缩性质
$ \delta(ax) = \frac{1}{|a|}\delta(x) $

#### 复合性质（由伸缩性质而来）
+ 若$ g(x) $在$ (a,b) $内由一个实单根（即一阶零点），则：

$ \int_{a}^{b} f(x)\delta(g(x))dx = \frac{f(x_0)}{|g'(x)|};g(x_0) = 0 $



#### 导数性质
$ \int_{a}^{b} f(x)\delta'(x)dx = -f'(0) $

#### Delta函数的高阶形式
+ 二维带哑变量（极坐标分解）：

$ \delta^{(2)}(\vec{r}-\vec{r}') = \delta(x-x')\delta(y-y') = \frac{1}{r'}\delta(r-r')\delta(\theta-\theta') $

+ 三维带哑变量（球坐标分解）：

$ \delta^{(3)}(\vec{r}-\vec{r}') = \delta(x-x')\delta(y-y')\delta(z-z') = \frac{1}{r'^2\sin\theta'}\delta(r-r')\delta(\theta-\theta')\delta(\phi-\phi') $

+ 二维不带哑变量，仅保留径向部分（极坐标分解）：

$ \delta^{(2)}(\vec{r}-\vec{r}') = \frac{\delta(r)}{2\pi r} $

+ 三维不带哑变量，仅保留径向部分（球坐标分解）：

$ \delta^{(3)}(\vec{r}-\vec{r}') = \frac{\delta(r)}{4\pi r^2} $
