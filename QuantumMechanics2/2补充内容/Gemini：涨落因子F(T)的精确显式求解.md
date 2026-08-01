#### 【续】分离经典部分：涨落因子 $ F(T) $ 的精确显式求解
前面我们得到了传播子写为经典项与涨落项的乘积形式：

$ K(x'',t'';x',t') = e^{i S_{c}/\hbar} \int \mathcal{D}[q(t)] \exp \left\{ \frac{i}{2\hbar} \int_{t'}^{t''} dt \, q(t) \hat{A}(t) q(t) \right\} $

其中算子 $ \hat{A}(t) = -m\frac{d^2}{dt^2} - V''(x_c(t)) $。注意到泛函积分只涉及边界条件为 $ q(t') = q(t'') = 0 $ 的涨落路径 $ q(t) $，因此该涨落积分不依赖于始末位置 $ x', x'' $，而仅是时间间隔 $ T = t'' - t' $ 的函数，记为涨落因子 $ F(T) $。

为了求出 $ F(T) $ 的**绝对精确值**（而非仅停留在比例关系），我们先用**本征函数展开法**将其表示为算子本征值的无限乘积，再通过 **Gelfand-Yaglom 定理** 与**自由粒子归一化**完成精确求值。

---

##### 步骤一：基于本征函数展开法表达 $ F(T) $
考虑微分算子 $ \hat{A}(t) $ 在定义域边界条件 $ q(t') = q(t'') = 0 $ 下的本征值方程：

$ \hat{A}(t) \phi_n(t) = \lambda_n \phi_n(t), \quad \phi_n(t') = \phi_n(t'') = 0 $

由于 $ \hat{A} $ 为自恰算子，其本征函数构成正交归一完备基矢，满足 $ \int_{t'}^{t''} \phi_n(t) \phi_m(t) dt = \delta_{nm} $。我们将任意涨落路径 $ q(t) $ 按本征函数展开：

$ q(t) = \sum_{n=1}^{\infty} c_n \phi_n(t) $

代入涨落作用量 $ S_{\text{QM-F}} $：

$ S_{\text{QM-F}} = \frac{1}{2} \int_{t'}^{t''} dt \sum_{n,m} c_n c_m \phi_n(t) \hat{A}(t) \phi_m(t) = \frac{1}{2} \sum_{n=1}^{\infty} \lambda_n c_n^2 $

此时，对路径 $ q(t) $ 的泛函积分转化为对无穷多个展开系数 $ c_n $ 的独立高斯积分乘积：

$ F(T) = J \prod_{n=1}^{\infty} \int_{-\infty}^{+\infty} d c_n \exp \left( \frac{i}{2\hbar} \lambda_n c_n^2 \right) = J \prod_{n=1}^{\infty} \sqrt{\frac{2\pi i \hbar}{\lambda_n}} = C \cdot \frac{1}{\sqrt{\prod_{n=1}^{\infty} \lambda_n}} = C \cdot \frac{1}{\sqrt{\det \hat{A}}} $

其中 $ J $ 为坐标变换的雅可比行列式，$ C $ 为由路径积分测度决定的常数。

---

##### 步骤二：利用 Gelfand-Yaglom 定理计算本征值无限乘积之比
直接计算抽象的无穷维行列式 $ \det \hat{A} = \prod_{n=1}^{\infty} \lambda_n $ 和未知常数 $ C $ 是非常困难的。我们引入**自由粒子**（$ V=0 $）作为参考基准，其对应的算子为 $ \hat{A}_0(t) = -m \frac{d^2}{dt^2} $。

考虑目标系统与自由粒子行列式的比值：

$ \frac{F(T)}{F_0(T)} = \sqrt{\frac{\det \hat{A}_0}{\det \hat{A}}} $

> **Gelfand-Yaglom 定理**：  
对于定义在 $ t \in [t', t''] $（为简单起见，设 $ t'=0, t''=T $）且作用于满足齐次 Dirichlet 边界条件 $ q(0)=q(T)=0 $ 空间的微分算子 $ \hat{A} $，其算子行列式的比值等于各自初值问题辅助解在终点 $ T $ 处的值之比：
>
> $ \frac{\det \hat{A}}{\det \hat{A}_0} = \frac{y(T)}{y_0(T)} $
>
> 其中辅助函数 $ y(t) $ 与 $ y_0(t) $ 分别满足各自的齐次常微分方程及相同的初始条件：
>
> $ \hat{A} y(t) = 0, \quad y(0) = 0, \quad \dot{y}(0) = 1 $
>
> $ \hat{A}_0 y_0(t) = 0, \quad y_0(0) = 0, \quad \dot{y}_0(0) = 1 $
>
> _(注：辅助解 _$ y(t) $_ 仅固定初始点 _$ y(0)=0 $_，在终点一般满足 _$ y(T) \neq 0 $_。若 _$ y(T)=0 $_，则说明算子存在零本征值，系统处于焦散点。)_
>

+ **求解自由粒子初值解 **$ y_0(t) $**：**

$ \hat{A}_0 y_0(t) = -m \ddot{y}_0(t) = 0 \implies \ddot{y}_0(t) = 0 $

+ 结合初始条件 $ y_0(0) = 0, \, \dot{y}_0(0) = 1 $，直接解得：

$ y_0(t) = t \implies y_0(T) = T $

+ **代入行列式比值：**

$ \frac{\det \hat{A}}{\det \hat{A}_0} = \frac{y(T)}{T} \implies F(T) = F_0(T) \cdot \sqrt{\frac{T}{y(T)}} $

---

##### 步骤三：结合自由粒子已知核求绝对系数 $ F_0(T) $
对于自由粒子（$ V(x) = 0 $），其传播子可以通过连续高斯积分直接精确算得：

$ K_0(x'',T; x',0) = \sqrt{\frac{m}{2\pi i \hbar T}} \exp\left( \frac{i m (x'' - x')^2}{2\hbar T} \right) $

对比二次型公式 $ K_0 = F_0(T) \exp\left(\frac{i}{\hbar} S_{\text{cl}}^{(0)}\right) $，由于自由粒子的经典作用量为 $ S_{\text{cl}}^{(0)} = \frac{m(x''-x')^2}{2T} $，我们可以**精确提取出自由粒子的涨落因子**：

$ \boxed{F_0(T) = \sqrt{\frac{m}{2\pi i \hbar T}}} $

将 $ F_0(T) $ 代入步骤二的比例式中，$ T $ 被精确消去：

$ F(T) = \sqrt{\frac{m}{2\pi i \hbar T}} \cdot \sqrt{\frac{T}{y(T)}} = \boxed{\sqrt{\frac{m}{2\pi i \hbar y(T)}}} $

---

##### 步骤四：将 $ y(T) $ 关联至经典作用量的二阶偏导数
初值问题方程 $ m \ddot{y}(t) + V''(x_c(t)) y(t) = 0 $ 实际上代表了经典轨道关于端点变化的**雅可比场（Jacobi Field）**。

经典路径 $ x_c(t) $ 是方程 $ m \ddot{x}_c + V'(x_c) = 0 $ 的解，满足边界 $ x_c(0) = x', \, x_c(T) = x'' $。  
对经典轨迹方程关于初速度 $ v' = \dot{x}_c(0) $ 求变分，设 $ \eta(t) = \frac{\partial x_c(t)}{\partial v'} $，容易证明 $ \eta(t) $ 正好满足：

$ m \ddot{\eta}(t) + V''(x_c(t)) \eta(t) = 0, \quad \eta(0) = 0, \quad \dot{\eta}(0) = 1 $

这说明 $ y(t) \equiv \eta(t) = \frac{\partial x_c(t)}{\partial v'} $，即 $ y(T) = \frac{\partial x''}{\partial v'} $。

根据经典力学哈密顿-雅可比理论，经典动量与作用量的关系为：

$ p' = m v' = -\frac{\partial S_{\text{cl}}}{\partial x'} \implies v' = -\frac{1}{m} \frac{\partial S_{\text{cl}}}{\partial x'} $

两侧对末位置 $ x'' $ 求偏导：

$ \frac{1}{y(T)} = \frac{\partial v'}{\partial x''} = -\frac{1}{m} \frac{\partial^2 S_{\text{cl}}}{\partial x'' \partial x'} $

即：

$ \boxed{\frac{m}{y(T)} = -\frac{\partial^2 S_{\text{cl}}}{\partial x'' \partial x'}} $

---

##### 最终结论（Van Vleck-Pauli-Morette 公式）
将上述经典作用量的二阶偏导关系代回 $ F(T) $：

$ \boxed{F(T) = \sqrt{\frac{1}{2\pi i \hbar} \left( -\frac{\partial^2 S_{\text{cl}}}{\partial x'' \partial x'} \right)}} $

这就是二次型拉格朗日系统中**涨落因子 **$ F(T) $** 的绝对精确表达**！

+ **实例验证（谐振子）：**
    - 谐振子经典作用量：$ S_{\text{cl}} = \frac{m\omega}{2\sin(\omega T)} \left[ (x'^2 + x''^2)\cos(\omega T) - 2x'x'' \right] $
    - 计算交叉二阶偏导：$ -\frac{\partial^2 S_{\text{cl}}}{\partial x'' \partial x'} = \frac{m\omega}{\sin(\omega T)} $
    - 代入公式直接得到显式解：$ F(T) = \sqrt{\frac{m\omega}{2\pi i \hbar \sin(\omega T)}} $，与离散化方法求出的结果完全吻合。
