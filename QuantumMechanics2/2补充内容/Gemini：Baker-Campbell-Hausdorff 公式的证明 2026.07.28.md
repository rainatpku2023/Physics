### **提示词**
<font style="color:rgb(31, 31, 31);background-color:rgb(242, 240, 240);">请给出BCH等式的证明。</font>

**Baker-Campbell-Hausdorff (BCH) 公式**在量子力学与矩阵指数变换中占有极其核心的地位。其核心任务是解决**非对易算符**的指数乘积问题。

通常用到的 BCH 公式形式可分为**简易形式（常见于量子力学推导）**与**一般形式（微分方程法推导）**。以下为你详细呈现这两种形式的严格证明。

---

## 一、 量子力学常用形式（单重对易子形式）的证明
### 1. 定理内容
若算符 $ \hat{A} $ 和 $ \hat{B} $ 的对易子 $ [\hat{A}, \hat{B}] $ 与 $ \hat{A} $ 及 $ \hat{B} $ 均对易（即 $ [\hat{A}, [\hat{A}, \hat{B}]] = 0 $ 且 $ [\hat{B}, [\hat{A}, \hat{B}]] = 0 $），则有：

$ e^{\hat{A}} e^{\hat{B}} = e^{\hat{A} + \hat{B} + \frac{1}{2}[\hat{A}, \hat{B}]} $

或等价地写为：

$ \boxed{e^{\hat{A} + \hat{B}} = e^{\hat{A}} e^{\hat{B}} e^{-\frac{1}{2}[\hat{A}, \hat{B}]}} $

---

### 2. 证明过程（引入参数参数化法）
定义一个含实参数 $ x $ 的算符函数 $ \hat{F}(x) $：

$ \hat{F}(x) = e^{x\hat{A}} e^{x\hat{B}} $

**Step 1: 对参数 **$ x $** 求微商**

对 $ \hat{F}(x) $ 关于 $ x $ 求导（注意算符次序不能颠倒）：

$ \frac{d\hat{F}}{dx} = \left(\frac{d}{dx} e^{x\hat{A}}\right) e^{x\hat{B}} + e^{x\hat{A}} \left(\frac{d}{dx} e^{x\hat{B}}\right) = \hat{A} e^{x\hat{A}} e^{x\hat{B}} + e^{x\hat{A}} \hat{B} e^{x\hat{B}} $

利用 $ \hat{F}(x) $ 的定义，第一项为 $ \hat{A}\hat{F}(x) $。为了把第二项也用 $ \hat{F}(x) $ 表示，我们在第二项中间插入单位算符 $ \hat{I} = e^{-x\hat{A}} e^{x\hat{A}} $：

$ \frac{d\hat{F}}{dx} = \hat{A}\hat{F}(x) + e^{x\hat{A}} \hat{B} e^{-x\hat{A}} \cdot e^{x\hat{A}} e^{x\hat{B}} = \left( \hat{A} + e^{x\hat{A}} \hat{B} e^{-x\hat{A}} \right) \hat{F}(x) $

---

**Step 2: 计算伴随作用 **$ e^{x\hat{A}} \hat{B} e^{-x\hat{A}} $

定义算符函数 $ \hat{G}(x) = e^{x\hat{A}} \hat{B} e^{-x\hat{A}} $。对其求导：

$ \frac{d\hat{G}}{dx} = \hat{A} e^{x\hat{A}} \hat{B} e^{-x\hat{A}} - e^{x\hat{A}} \hat{B} \hat{A} e^{-x\hat{A}} = e^{x\hat{A}} [\hat{A}, \hat{B}] e^{-x\hat{A}} $

因为前提条件设定 $ [\hat{A}, \hat{B}] $ 与 $ \hat{A} $ 对易，所以指数算符 $ e^{x\hat{A}} $ 可以穿过对易子：

$ \frac{d\hat{G}}{dx} = [\hat{A}, \hat{B}] e^{x\hat{A}} e^{-x\hat{A}} = [\hat{A}, \hat{B}] $

由于 $ \frac{d\hat{G}}{dx} $ 为常数算符，对 $ x $ 从 $ 0 $ 到 $ x $ 积分，且初始条件 $ \hat{G}(0) = \hat{B} $：

$ \hat{G}(x) = \hat{B} + x[\hat{A}, \hat{B}] $

也就是证明了著名的阿达马引理（Hadamard Lemma）在初阶截断的情形：



$ e^{x\hat{A}} \hat{B} e^{-x\hat{A}} = \hat{B} + x[\hat{A}, \hat{B}] $

---

**Step 3: 解关于 **$ \hat{F}(x) $** 的微分方程**

将 $ \hat{G}(x) $ 的结果代回 $ \frac{d\hat{F}}{dx} $ 的表达式中：

$ \frac{d\hat{F}}{dx} = \left( \hat{A} + \hat{B} + x[\hat{A}, \hat{B}] \right) \hat{F}(x) $

注意：右侧括号内的项 $ \hat{C}(x) = \hat{A} + \hat{B} + x[\hat{A}, \hat{B}] $ 与其在不同时刻的值是对易的，因为 $ [\hat{A}+\hat{B}, [\hat{A},\hat{B}]] = 0 $。因此可以直接像标量微分方程那样积分：

$ \hat{F}(x) = \hat{F}(0) \exp\left\{ \int_0^x (\hat{A} + \hat{B} + x'[\hat{A}, \hat{B}]) dx' \right\} $

由初始条件 $ \hat{F}(0) = e^0 e^0 = \hat{I} $，完成积分得：

$ \hat{F}(x) = \exp\left( x(\hat{A} + \hat{B}) + \frac{1}{2}x^2[\hat{A}, \hat{B}] \right) $

---

**Step 4: 取 **$ x = 1 $** 并整理**

令 $ x = 1 $，得到：

$ e^{\hat{A}} e^{\hat{B}} = \exp\left( \hat{A} + \hat{B} + \frac{1}{2}[\hat{A}, \hat{B}] \right) $

由于 $ [\hat{A}, \hat{B}] $ 是与 $ \hat{A}+\hat{B} $ 对易的中心元（相当于复数），指数可以拆分：

$ \exp\left( \hat{A} + \hat{B} + \frac{1}{2}[\hat{A}, \hat{B}] \right) = e^{\hat{A}+\hat{B}} \cdot e^{\frac{1}{2}[\hat{A}, \hat{B}]} $

两侧同乘以 $ e^{-\frac{1}{2}[\hat{A}, \hat{B}]} $，即得证：

$ \boxed{e^{\hat{A}+\hat{B}} = e^{\hat{A}} e^{\hat{B}} e^{-\frac{1}{2}[\hat{A}, \hat{B}]}} \quad \mathrm{Q.E.D.} $

---

## 二、 一般形式（级数展开形式）简介
当对易子并不与算符本身对易时（即高阶对易子不为零），BCH 公式的一般表达式为：

$ e^{\hat{A}} e^{\hat{B}} = \exp\left( \hat{A} + \hat{B} + \frac{1}{2}[\hat{A}, \hat{B}] + \frac{1}{12}[\hat{A}, [\hat{A}, \hat{B}]] - \frac{1}{12}[\hat{B}, [\hat{A}, \hat{B}]] + \dots \right) $

一般形式的通用证明通常利用**微分流形与李代数**中的微分映射：

1. 构造算符 $ Z(t) $ 使得 $ e^{Z(t)} = e^{\hat{A}} e^{t\hat{B}} $。
2. 利用李代数的微分公式：

$ \frac{d}{dt} e^{Z(t)} = e^{Z(t)} \left( \frac{1 - e^{-\mathrm{ad}_{Z(t)}}}{\mathrm{ad}_{Z(t)}} \frac{dZ}{dt} \right) $

其中 $ \mathrm{ad}_X(Y) = [X, Y] $ 为伴随作用。  
3. 比较等式两边并用伯努利数（Bernoulli numbers）展开解出 $ \frac{dZ}{dt} $，最后对 $ t $ 积分即可得到无穷级数形式。
