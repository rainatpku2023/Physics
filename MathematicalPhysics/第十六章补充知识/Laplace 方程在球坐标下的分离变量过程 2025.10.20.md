## 1 球坐标系下Laplace方程的形式
+ 三维$ \mathrm{Laplace} $方程的定义为：

$ \nabla^2 u = 0 $

+ 在球坐标中，设径向坐标为$ r $，极角为$ \theta $，方位角为$ \phi $，$ \mathrm{Laplace} $方程形式为：

$ \frac{1}{r^2}\frac{\partial }{\partial r}(r^2 \frac{\partial u}{\partial r})+ \frac{1}{r^2 \sin \theta}\frac{\partial}{\partial \theta}(\sin\theta \frac{\partial u }{\partial \theta}) + \frac{1}{r^2\sin^2\theta} \frac{\partial^2u}{\partial \phi^2}  =0 $

    - 需要补充上的周期性条件和有界条件为：

$ u|_{r=0} 有界 $

$ u|_{\theta=0} 有界 $$ u|_{\theta=\pi} 有界 $

$ u|_{\phi=0} =u|_{\phi=2\pi}  $$ \frac{\partial u}{\partial \phi}|_{\phi=0} =\frac{\partial u}{\partial \phi}|_{\phi=2\pi}  $

## 2 变量分离问题
### 2-1 径向部分和角向部分的分离
+ 假设待求函数$ u $可以分离为径向部分和角向部分的乘积，即：

$ u(r,\theta,\phi) = R(r)S(\theta, \phi) $

+ 将其代入$ \mathrm{Laplace} $方程：

$ \frac{1}{r^2}\frac{d }{d r}(r^2 \frac{d R}{d r})S+ \frac{1}{r^2 \sin \theta}\frac{\partial}{\partial \theta}(\sin\theta \frac{\partial S }{\partial \theta})R + \frac{1}{r^2\sin^2\theta} \frac{\partial^2S}{\partial \phi^2}R  =0 $

+ 两边同时除以$ R(r)S(\theta,\phi) $，并移项得：

$ \frac{1}{R}\frac{d }{d r}(r^2 \frac{d R}{d r}) = 

- \frac{1}{S}[\frac{1}{ \sin \theta}\frac{\partial}{\partial \theta}(\sin\theta \frac{\partial S }{\partial \theta}) + \frac{1}{\sin^2\theta} \frac{\partial^2S}{\partial \phi^2}] = \lambda $

+ 实现**变量分离**：

$ \frac{d }{d r}(r^2 \frac{d R}{d r})  - \lambda R = 0 $

$ \frac{1}{ \sin \theta}\frac{\partial}{\partial \theta}(\sin\theta \frac{\partial S }{\partial \theta}) + \frac{1}{\sin^2\theta} \frac{\partial^2S}{\partial \phi^2} + \lambda S = 0 $

    - 需要特别注意，要将第二个式子中的$ \lambda $保持符号为正。此时$ \lambda_l = l(l+1) $。
+ 结合上定解条件：

$ \frac{d }{d r}(r^2 \frac{d R}{d r})  - \lambda R = 0 $

$ R(0)有界 $



$ \frac{1}{ \sin \theta}\frac{\partial}{\partial \theta}(\sin\theta \frac{\partial S }{\partial \theta}) + \frac{1}{\sin^2\theta} \frac{\partial^2S}{\partial \phi^2} + \lambda S = 0 $

$ S|_{\theta=0} 有界 $$ S|_{\theta=\pi} 有界 $

$ S|_{\phi=0} =S|_{\phi=2\pi}  $$ \frac{\partial S}{\partial \phi}|_{\phi=0} =\frac{\partial S}{\partial \phi}|_{\phi=2\pi}  $

    - <font style="color:#DF2A3F;">可见角向部分函数</font>$ S $<font style="color:#DF2A3F;">的方程与定解条件组成了一个本征值问题。</font>

### 2-2 极角和方位角部分的分离
+ 假设角向$ S $部分可以分离为极角部分$ \Theta $和方位角部分$ \Phi $，即：

$ S(\theta,\phi) = \Theta(\theta)\Phi(\phi) $

+ 将其代入角向部分方程：

$ \frac{1}{ \sin \theta}\frac{d}{d \theta}(\sin\theta \frac{d \Theta }{d \theta})\Phi

 + \frac{1}{\sin^2\theta} \frac{d^2\Phi }{d \phi^2} \Theta+ \lambda \Theta \Phi = 0 $

+ 两边同时除以$ \Theta(\theta)\Phi(\phi) $并乘以$ \sin^2 \theta $，并移项得：

$ \frac{1}{\Theta}\sin\theta\frac{d}{d \theta}(\sin\theta \frac{d \Theta }{d \theta})
 + \lambda\sin^2\theta = - \frac{1}{\Phi}\frac{d^2\Phi }{d \phi^2}
= \mu $

+ 实现**变量分离**：

$ \frac{1}{\Theta}\sin\theta\frac{d}{d \theta}(\sin\theta \frac{d \Theta }{d \theta}) + \lambda\sin^2\theta  - \mu =0 $

$ \frac{d^2\Phi }{d \phi^2}+ \mu \Phi = 0 $

    - 即：

$ \frac{1}{\sin\theta}\frac{d}{d \theta}(\sin\theta \frac{d \Theta }{d \theta}) + (\lambda  - \frac{\mu}{\sin^2\theta})\Theta =0 $

$ \frac{d^2\Phi }{d \phi^2}+ \mu \Phi = 0 $

+ 结合上定解条件：

$ \frac{1}{\sin\theta}\frac{d}{d \theta}(\sin\theta \frac{d \Theta }{d \theta}) + (\lambda  - \frac{\mu}{\sin^2\theta})\Theta =0 $

$ \Theta(0)有界 $$ \Theta(\pi)有界 $



$ \frac{d^2\Phi }{d \phi^2}+ \mu \Phi = 0 $

$ \Phi(0) = \Phi(2\pi) $$ \Phi'(0) = \Phi'(2\pi) $

    - <font style="color:#DF2A3F;">可见方向角部分</font>$ \Phi $<font style="color:#DF2A3F;">组成本征值问题。</font>

## 3 本征值问题求解
### 3-1 方位角部分本征值问题
+ 本征值问题为：

$ \frac{d^2\Phi }{d \phi^2}+ \mu \Phi = 0 $

$ \Phi(0) = \Phi(2\pi) $$ \Phi'(0) = \Phi'(2\pi) $

    - 其中本征值为$ \mu $，待求函数为$ \Phi(\phi) $。

#### 方位角部分本征值与本征函数
+ 一组本征值与本征函数的选取方式为【方式1】：

$ \mu_m = m^2 ,\; m = 0,1,2,3,...  $

    - 对应的本征函数为：

$ \Phi_{m1}(\phi) = \cos m\phi, \; m = 0,1,2,3... $

$ \Phi_{m2}(\phi) = \sin m\phi, \; m = 1,2,3... $

    - 正交归一性为：
+ 另外一组选取方式为【方式2】：
    - 本征值：

$ \mu_m = m^2 ,\; m = 0,1,2,3,...  $

    - 本征函数：

$ \Phi_{m}(\phi) = e^{im\phi}, \; m =0,±1,±2,±3,... $

### 3-2 极角部分本征值问题
+ 将$ \mu_m = m^2 ,\; m = 0,1,2,3,...  $代入极角方程，得到本征值问题为：

$ \frac{1}{\sin\theta}\frac{d}{d \theta}(\sin\theta \frac{d \Theta }{d \theta}) + (\lambda  - \frac{m^2}{\sin^2\theta})\Theta =0 $

$ \Theta(0)有界 $$ \Theta(\pi)有界 $

    - 其中本征值为$ \lambda $，待求函数为$ \Theta(\theta) $。

#### 极角部分本征值与本征函数
+ 一组本征值与本征函数的选取为：
    - 本征值为：

$ \lambda_l = l(l+1), \; l = m,m+1,m+2,... $

    - 对应的本征函数为：

$ \Theta_{lm}(\theta) = P_l^{|m|}(\cos\theta) $

+ 其中$ P_l^m(x) $为$ m $<font style="color:#117CEE;">阶</font>$ l $<font style="color:#117CEE;">次</font>$ \mathrm{Legendre} $<font style="color:#117CEE;">函数</font>。

#### 知识链接：l 次 Legendre 多项式
[【未完】第十六章 球函数 2025.10.04](https://dengbaiyu2023.yuque.com/org-wiki-dengbaiyu2023-vsgo6q/dw1fe5/cqakb1k6s3xu2yu2#Yb9Th)

#### 知识链接：m 阶 l 次连带 Legendre 函数
[【未完】第十六章 球函数 2025.10.04](https://dengbaiyu2023.yuque.com/org-wiki-dengbaiyu2023-vsgo6q/dw1fe5/cqakb1k6s3xu2yu2#wjQVJ)

### 3-3 角向部分本征值问题
#### 角向部分本征值与本征函数
+ 综合[方位角部分本征函数](#mx5hf)与[极角部分本征函数](#PY3YW)，构造角度部分本征函数，即**球谐函数**：
    - 本征值为$ \lambda_l = l(l+1) $
    - 在[方式1](#mx5hf)中，球谐函数的表达式为：

$ S_{lm1}(\theta,\phi) = \Theta_{lm}(\theta) \Phi_{m1}(\phi)= P_l^m(\cos\theta)\cos m\phi $

$ S_{lm2}(\theta,\phi)  = \Theta_{lm}(\theta) \Phi_{m2}(\phi)= P_l^m(\cos\theta)\sin m\phi $

    - 在[方式2](#mx5hf)中，球谐函数的表达式为：

$ S_{lm}(\theta,\phi) = \Theta_{lm}(\theta) \Phi_{m}(\phi)= P_l^{|m|}(\cos\theta)e^{im\phi} $

    - 在物理中一般使用第二种表达方式。
+ 结合球谐函数的正交归一性关系，常常定义**归一化球谐函数**：

$ Y_l^m(\theta,\phi) = \sqrt{\frac{(l-|m|
)!}{(l+|m|)!}\frac{2l+1}{4\pi}} S_{lm}(\theta,\phi) = \sqrt{\frac{(l-|m|
)!}{(l+|m|)!}\frac{2l+1}{4\pi}} P_l^{|m|}(\cos\theta)e^{im\phi} $

#### 知识链接：球谐函数
[【未完】第十六章 球函数 2025.10.04](https://dengbaiyu2023.yuque.com/org-wiki-dengbaiyu2023-vsgo6q/dw1fe5/cqakb1k6s3xu2yu2#A1gVl)

#### 知识链接：归一化球谐函数
[【未完】第十六章 球函数 2025.10.04](https://dengbaiyu2023.yuque.com/org-wiki-dengbaiyu2023-vsgo6q/dw1fe5/cqakb1k6s3xu2yu2#bbVbO)

### 3-4 径向部分求解
+ 将本征值$ \lambda_l = l(l+1), \; l = m,m+1,m+2,... $代入径向方程：

$ \frac{d }{d r}(r^2 \frac{d R}{d r})  - l(l+1) R = 0 $

#### 径向部分通解
    - 求出**通解**：

$ R_{l1}(r) = r^l $

$ R_{l2}(r) =r^{-l-1} $

        * $ R_1 $在无穷远处发散，$ R_2 $在原点处发散。

#### 径向部分一般解
    - 叠加出**一般解**为：

$ R_l(r) = C_{l1}R_{l1}(r) + C_{l2}R_{l2}(r) $

$ = C_{l1}r^l + C_{l2}r^{-l-1} $

### 3-5 整体方程求解
#### 整体部分通解
+ 根据[径向部分通解](#o8kcQ)和[角向部分通解](#OvaOk)，可以构造出$ \mathrm{Laplace} $**方程整体的通解**：

$ u_{lm1}(r,\theta,\phi) = R_{l1}(r) Y_l^m(\theta,\phi) = r^l\sqrt{\frac{(l-|m|
)!}{(l+|m|)!}\frac{2l+1}{4\pi}} P_l^{|m|}(\cos\theta)e^{im\phi} $

$ u_{lm2}(r,\theta,\phi) = R_{l2}(r) Y_l^m(\theta,\phi) = r^{-l-1}\sqrt{\frac{(l-|m|
)!}{(l+|m|)!}\frac{2l+1}{4\pi}} P_l^{|m|}(\cos\theta)e^{im\phi} $

    - $ u_{lm1} $在无穷远处发散，$ u_{lm2} $在原点处发散。

#### 整体部分一般解
+ 根据整体方程的通解，可以构造出$ \mathrm{Laplace} $**方程整体的一般解**：

$ u = \sum_{l=0}^{\infin} \sum_{m=-l}^{l} [C_{l1}R_{l1}(r)+C_{l2}R_{l2}(r)]D_mY_l^{m}(\theta,\phi) $

$ =\sum_{l=0}^{\infin} \sum_{m=-l}^{l}(C_{l1}r^l + C_{l2}r^{-l-1}) D_m\sqrt{\frac{(l-|m|)!}{(l+|m|)!}\frac{2l+1}{4\pi}} P_l^{|m|}(\cos\theta)e^{im\phi} $

    - 可以重新定义叠加系数：

$ C_{lm1} = C_{l1} D_m $

$ C_{lm2} = C_{l2} D_m $

        * $ \mathrm{Laplace} $**方程通解**可以改写为：

$ u = \sum_{l=0}^{\infin} \sum_{m=-l}^{l} [C_{lm1}R_{l1}(r)+C_{lm2}R_{l2}(r)]Y_l^{m}(\theta,\phi) $

$ =\sum_{l=0}^{\infin} \sum_{m=-l}^{l}(C_{lm1}r^l + C_{lm2}r^{-l-1}) \sqrt{\frac{(l-|m|)!}{(l+|m|)!}\frac{2l+1}{4\pi}} P_l^{|m|}(\cos\theta)e^{im\phi} $




