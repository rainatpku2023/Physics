## 1. 偏微分算符 $ \partial $ 的厄米共轭推导
在量子力学中，算符 $ \hat{A} $ 的厄米共轭（伴随算符）$ \hat{A}^\dagger $ 定义为满足内积等式 $ \langle \phi | \hat{A} \psi \rangle = \langle \hat{A}^\dagger \phi | \psi \rangle $ 的算符。

对于偏微分算符 $ \partial_j = \frac{\partial}{\partial x_j} $，推导过程如下：

1. **写出内积积分形式**（考虑一维情况以简化，高维同理）：

$ \langle \phi | \partial_x \psi \rangle = \int_{-\infty}^{+\infty} \phi^*(x) \left( \frac{d}{dx} \psi(x) \right) dx $

2. **应用分部积分法**：

$ \int \phi^* \frac{d\psi}{dx} dx = \left[ \phi^* \psi \right]_{-\infty}^{+\infty} - \int \left( \frac{d\phi^*}{dx} \right) \psi dx $

3. **利用边界条件**：在量子力学束缚态中，波函数在无穷远处趋于零，故 $ \left[ \phi^* \psi \right] = 0 $。
4. **整理项**：

$ \langle \phi | \partial_x \psi \rangle = \int \left( -\frac{d\phi}{dx} \right)^* \psi dx = \langle -\partial_x \phi | \psi \rangle $

**结论**：

+ **伴随算符（转置效应）**：$ \partial^\dagger = -\partial $。负号源于分部积分。
+ **复共轭**：$ \partial^* = \partial $（微分操作本身不含虚数单位 $ i $）。
+ **动量算符厄米性**：$ \hat{p}^\dagger = (-i\hbar\partial)^\dagger = (+i\hbar)(-\partial) = -i\hbar\partial = \hat{p} $。

---

## 2. 爱因斯坦求和约定：算符矢量积的“定海神针”
在经典力学中，我们习惯使用 $ \vec{A} \times (\vec{B} \times \vec{C}) = \vec{B}(\vec{A} \cdot \vec{C}) - \vec{C}(\vec{A} \cdot \vec{B}) $。但在量子力学中，算符具有**非对易性**，这种简写极易导致作用顺序的混乱。

**爱因斯坦求和约定的重要性体现在：**

1. **严格保序**：它迫使我们写出分量式 $ \epsilon_{ijk} \hat{A}_j \epsilon_{kmn} \hat{B}_m \hat{C}_n $，从下标排列中一眼看出 $ \hat{A} $ 位于最左侧，其微分作用范围覆盖了右侧所有的 $ \hat{B} $ 和 $ \hat{C} $。
2. **避免歧义**：通过指标 $ \delta_{im}\delta_{jn} $ 的缩并，我们可以精确地定位每一个算符分量的位置，而不会像矢量简写法那样产生“$ \vec{A} $ 到底是在点乘 $ \vec{C} $ 还是在点乘 $ \vec{B} $”的模糊感。

---

## 3. 算符三重积公式：$ \hat{\mathbf{A}} \times (\hat{\mathbf{B}} \times \hat{\mathbf{C}}) $
利用爱因斯坦求和约定推导出的标准量子算符形式：

$ [\hat{\mathbf{A}} \times (\hat{\mathbf{B}} \times \hat{\mathbf{C}})]_i = \hat{A}_j \hat{B}_i \hat{C}_j - \hat{A}_j \hat{B}_j \hat{C}_i $

转化为矢量表示（需严格遵守从左往右的作用顺序）：

$ \hat{\mathbf{A}} \times (\hat{\mathbf{B}} \times \hat{\mathbf{C}}) = \sum_j \hat{A}_j \hat{\mathbf{B}} \hat{C}_j - (\hat{\mathbf{A}} \cdot \hat{\mathbf{B}}) \hat{\mathbf{C}} $

### 实例分析：$ \hat{\mathbf{p}} \times (\hat{\mathbf{r}} \times \hat{\mathbf{p}}) $ 的展开
当算符间不对易时，求和约定会自动暴露出“量子修正项”：

1. **第一项** $ \hat{p}_j \hat{r}_i \hat{p}_j $：由于 $ \hat{p}_j \hat{r}_i = \hat{r}_i \hat{p}_j - i\hbar \delta_{ij} $，该项变为 $ \hat{r}_i \hat{p}^2 - i\hbar \hat{p}_i $。
2. **第二项** $ \hat{p}_j \hat{r}_j \hat{p}_i $：由于 $ \hat{p}_j \hat{r}_j = \hat{r}_j \hat{p}_j - 3i\hbar $，该项变为 $ (\hat{\mathbf{r}} \cdot \hat{\mathbf{p}}) \hat{p}_i - 3i\hbar \hat{p}_i $。

**最终合成**：

$ \hat{\mathbf{p}} \times (\hat{\mathbf{r}} \times \hat{\mathbf{p}}) = \underbrace{\hat{\mathbf{r}} \hat{p}^2 - (\hat{\mathbf{r}} \cdot \hat{\mathbf{p}}) \hat{\mathbf{p}}}_{\text{经典项}} + \underbrace{2i\hbar \hat{\mathbf{p}}}_{\text{量子修正}} $

---

## 4. 核心要点对比表
| 概念 | 经典力学 | 量子力学 (算符) | 物理/数学根源 |
| :--- | :--- | :--- | :--- |
| **乘法顺序** | $ AB = BA $ | $ \hat{A}\hat{B} \neq \hat{B}\hat{A} $ | 海森堡不确定性原理 |
| **微分共轭** | 无伴随概念 | $ \partial^\dagger = -\partial $ | 内积定义与分部积分 |
| **三重积工具** | $ BAC-CAB $ 公式 | 爱因斯坦求和约定分量式 | 必须显式维持算符的左侧作用位置 |
| **量子修正** | $ 0 $ | 出现 $ i\hbar $ 相关项 | 算符在“穿过”彼此过程中产生的对易子效应 |

