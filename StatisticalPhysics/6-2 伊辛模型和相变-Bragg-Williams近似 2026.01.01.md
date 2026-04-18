[第六章-6.2-伊辛模型和相变-brag-william 近似.pdf](https://dengbaiyu2023.yuque.com/attachments/yuque/0/2025/pdf/2371504/1766712634640-fa39bcf9-a2fc-4f0f-9dd6-53b6014485d0.pdf)

本文使用Gemini完成。

# Bragg-Williams 近似（平均场近似）推导
### 1. 基本定义与参数
系统共有 $ N $ 个自旋，其中 $ N_+ $ 个自旋向上，$ N_- $ 个自旋向下。

$ N_+ + N_- = N $

引入序参数（磁化强度）$ m $，使得：

$ N_+ = \frac{1}{2}(1+m)N, \quad N_- = \frac{1}{2}(1-m)N $

系统的总能量哈密顿量为：

$ E = -J \sum_{\langle i,j \rangle} \sigma_i \cdot \sigma_j - h \sum_{i} \sigma_i $

---

### 2. 熵的计算
满足上述条件的微观状态数 $ \Omega $（即排列组合数）：

$ \Omega = \frac{N!}{N_+! N_-!} $

根据玻尔兹曼熵公式 $ S = k_B \ln \Omega $：

$ S = k_B \ln \frac{N!}{N_+! N_-!} = k_B \left[ \ln N! - \ln N_+! - \ln N_-! \right] $

利用斯特林近似（Stirling's approximation: $ \ln n! \approx n \ln n - n $）：

$ S \approx k_B \left[ N \ln N - N_+ \ln N_+ - N_- \ln N_- \right] $

代入 $ N_+ $ 和 $ N_- $ 的表达式并化简：

$ S = -k_B N \left[ \frac{1+m}{2} \ln \frac{1+m}{2} + \frac{1-m}{2} \ln \frac{1-m}{2} \right] $

---

### 3. 近邻关联与能量近似
定义近邻关联对数：

+ $ N_{++} $：两个自旋同时向上的近邻对数
+ $ N_{--} $：两个自旋同时向下的近邻对数
+ $ N_{+-} $：一个自旋向上、一个自旋向下的近邻对数

总近邻对数为：

$ N_{++} + N_{--} + N_{+-} = \frac{1}{2} dN $

> **注：** $ d $ 为配位数（Coordination number）。例如：一维 $ d=2 $；二维方格子 $ d=4 $；三维立方格子 $ d=6 $。
>

系统的能量期望值可以表示为：

$ E = -J(N_{++} + N_{--} - N_{+-}) - h(N_+ - N_-) $

---

### 4. Bragg-Williams 假设
在该近似下，假设近邻对的分布是完全随机的（忽略空间关联）：

$ \frac{N_{++}}{\frac{1}{2}dN} \approx \left(\frac{N_+}{N}\right)^2, \quad \frac{N_{--}}{\frac{1}{2}dN} \approx \left(\frac{N_-}{N}\right)^2, \quad \frac{N_{+-}}{\frac{1}{2}dN} \approx 2\left(\frac{N_+}{N}\right)\left(\frac{N_-}{N}\right) $

代入计算能量项中的自旋乘积和：

$ N_{++} + N_{--} - N_{+-} = \frac{1}{2} dN \left( \frac{N_+ - N_-}{N} \right)^2 = \frac{1}{2} d N m^2 $

由此得到平均能量 $ \bar{E} $：

$ \bar{E} = -\frac{1}{2} J d N m^2 - N h m $

---

### 5. 亥姆霍兹自由能 (Helmholtz Free Energy)
结合 $ F = \bar{E} - TS $，得到每单位自旋的平均自由能（或总自由能）：

$ F = -\frac{1}{2} J d N m^2 - N h m + N k_B T \left[ \frac{1+m}{2} \ln \frac{1+m}{2} + \frac{1-m}{2} \ln \frac{1-m}{2} \right] $

后面还有另外一种自由能推导方法，用到了广义熵的表达式。在此不再赘述。需要可以查看老师的pdf。
