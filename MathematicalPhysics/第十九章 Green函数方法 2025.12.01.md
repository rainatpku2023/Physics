[lecture8(ch19)-Green函数方法.pdf](https://dengbaiyu2023.yuque.com/attachments/yuque/0/2025/pdf/2371504/1762435971083-d39da64e-b706-4e13-ba11-c6534bf76751.pdf)

[WuCS格林函数1.pdf](https://dengbaiyu2023.yuque.com/attachments/yuque/0/2025/pdf/2371504/1763615241304-35eb1d7a-56d7-4858-814b-e35c233a93fa.pdf)

[WuCS格林函数2.pdf](https://dengbaiyu2023.yuque.com/attachments/yuque/0/2025/pdf/2371504/1763615241413-afd1409c-0eec-4f38-88d0-5e4d0d0d3747.pdf)

[数学物理方法 第三版 (吴崇试, 高春媛) (Z-Library).pdf](https://dengbaiyu2023.yuque.com/attachments/yuque/0/2025/pdf/2371504/1764590433787-b2a1ce8e-c0cf-4121-a830-385308aa15ce.pdf)

### 常微分方程初值问题的Green函数
#### 问题概述
+ 用$ \mathrm{Green} $函数方法求解下列定解问题：

$ \frac{d}{dt}[p(t)\frac{dy(t)}{dt}]+q(t)y(t) = f(t),\;t>0 $

$ y(0) = A,\; y'(0) = B $

#### 求解Green函数
+ 上述方程常微分方程初值问题对应的$ \mathrm{Green} $函数满足的定解问题为：

$ \frac{d}{dt}[p(t)\frac{dg(t;\tau)}{dt}]+q(t)g(t;\tau) = \delta(t-\tau),\;\tau>0,t>0 $

$ g(t;\tau)|_{t<\tau}=0,\;\frac{dg(t;\tau)}{dt}|_{t<\tau}=0 $

    - 相应的定解问题表示，时间上更靠后一个时间点的源不能对前面的时间点的场产生任何影响。



+ 对于$ t\neq\tau $的部分，相应的定解问题可以改为：

$ \frac{d}{dt}[p(t)\frac{dg(t;\tau)}{dt}]+q(t)g(t;\tau) = 0,\;\tau>0,t>0,t\neq\tau $

    - 可以设：

$ g(t;\tau) =
\begin{cases}
C_1 y_1(t)+ C_2 y_2(t),0<t<\tau \\
D_1 y_1(t)+ D_2 y_2(t),0<\tau<t
\end{cases} $

    - 根据定解条件$ g(t;\tau)|_{t<\tau}=0,\;\frac{g(t;\tau)}{dt}|_{t<\tau}=0 $：

$ C_1 = 0,\; C_2 = 0 $

$ \Rightarrow g(t,\tau) = 0,0<t<\tau $

+ $ 0<\tau<t $范围内$ g(t;\tau) $需要根据$ t = \tau $处$ g(t;\tau) $的行为进行推断，
    - 即$ D_1,D_2 $需要根据$ t = \tau $处$ g(t,\tau) $的行为进行求解：
    - 首先，$ t = \tau $处$ g(t;\tau) $应该连续，即：

$ g(\tau-\epsilon;\tau) = g(\tau+\epsilon;\tau),\; \epsilon \rightarrow 0 $

        * 即：

$ 0 = D_1 y_1(\tau) + D_2 y_2(\tau) $

    - 其次，$ t = \tau $处$ \frac{dg(t;\tau)}{dt} $应该产生一个类似于$ k\eta(t-\tau) $行为的跃变，对方程两侧积分：

$ \int_{\tau-\epsilon}^{\tau+\epsilon} \{\frac{d}{dt}[p(t)\frac{dg(t;\tau)}{dt}]+q(t)g(t;\tau)\}dt

= \int_{\tau-\epsilon}^{\tau+\epsilon} \delta(t-\tau)dt,\;\tau>0,t>0,\epsilon\rightarrow 0 $

        * 利用$ \mathrm{Delta} $函数的性质，右侧积分可以化为$ 1 $：

$ RHS = 1 $

        * 左侧可以进行积分：

$ LHS =  [p(t)\frac{dg(t;\tau)}{dt}]|_{t=\tau-\epsilon}^{\tau+\epsilon}+\int_{\tau-\epsilon}^{\tau+\epsilon}q(t)g(t;\tau)dt
,\;\tau>0,t>0,\epsilon\rightarrow 0 $

            + 根据$ t = \tau $处$ g(t;\tau) $应该连续，第二项积分可以化为$ 0 $，$ t\rightarrow \tau $时$ p(t) $没有奇异行为，则可以化为：

$ LHS = p(\tau)[\frac{dg(t;\tau)}{dt}]|_{t=\tau-\epsilon}^{\tau+\epsilon}
= p(\tau)[D_1 y_1'(\tau) + D_2 y_2'(\tau)] $

        * 由此，可以得到：

$ p(\tau)[D_1 y_1'(\tau) + D_2 y_2'(\tau)]=1 $

    - 综上，得到方程组：

$ \begin{cases}
0 = D_1 y_1(\tau) + D_2 y_2(\tau)\\
D_1 y_1'(\tau) + D_2 y_2'(\tau)=\frac{1}{p(\tau)}
\end{cases} $

        * 由此可以解出$ D_1,D_2 $，带入后得到$ \mathrm{Green} $函数：

$ g(t,\tau) =
\begin{cases}
0,0<t<\tau \\
D_1 y_1(t)+ D_2 y_2(t),0<\tau<t
\end{cases} $

#### 用Green函数求出原初值问题的解
+ 我们现在已经求出了$ \mathrm{Green} $函数，下面用$ \mathrm{Green} $函数求解原来的初值问题。



+ 我们先写出定解问题：

$ \frac{d}{dt}[p(t)\frac{dy(t)}{dt}]+q(t)y(t) = f(t),\;t>0 $

$ y(0) = A,\; y'(0) = B $

    - 作变量替换$ t\rightarrow \tau $：

$ \frac{d}{d\tau}[p(\tau)\frac{dy(\tau)}{d\tau}]+q(\tau)y(\tau) = f(\tau),\;\tau>0 $

$ y(0) = A,\; y'(0) = B $



+ 再写出$ \mathrm{Green} $函数满足的定解问题：

$ \frac{d}{dt}[p(t)\frac{dg(t;\tau)}{dt}]+q(t)g(t;\tau) = \delta(t-\tau),\;\tau>0,t>0 $

$ g(t;\tau)|_{t<\tau}=0,\;\frac{dg(t;\tau)}{dt}|_{t<\tau}=0 $

    - 作变量替换$ t\rightarrow -\tau $，$ \tau\rightarrow -t $，这样做是因为$ t<\tau $时$ -\tau<-t $：

$ \frac{d}{d(-\tau)}[p(-\tau)\frac{dg(-\tau;-t)}{d(-\tau)}]+q(-\tau)g(-\tau;-t) = \delta(-\tau+t),\;\tau>0,t>0 $

$ g(-\tau;-t)|_{-\tau<-t}=0,\;\frac{dg(-\tau;-t)}{d(-\tau)}|_{-\tau<-t}=0 $

    - 如果有$ p(t) = p(-t),q(t)=q(-t) $，结合$ \mathrm{Delta} $函数的性质，定解问题可以化为：

$ \frac{d}{d\tau}[p(\tau)\frac{dg(-\tau;-t)}{d\tau}]+q(\tau)g(-\tau;-t) = \delta(t-\tau),\;\tau>0,t>0 $

$ g(-\tau;-t)|_{-\tau<-t}=0,\;\frac{dg(-\tau;-t)}{d\tau}|_{-\tau<-t}=0 $

    - 如果$ \mathrm{Green} $函数具有**<font style="color:#DF2A3F;">时间倒易性</font>**$ g(-\tau;-t) = g(t;\tau) $，那么定解问题可以进一步化为：

$ \frac{d}{d\tau}[p(\tau)\frac{dg(t;\tau)}{d\tau}]+q(\tau)g(t;\tau) = \delta(t-\tau),\;\tau>0,t>0 $

$ g(t;\tau)|_{t<\tau}=0,\;\frac{dg(t;\tau)}{d\tau}|_{t<\tau}=0 $



+ 总结：

$ \frac{d}{d\tau}[p(\tau)\frac{dy(\tau)}{d\tau}]+q(\tau)y(\tau) = f(\tau),\;\tau>0 $

$ y(0) = A,\; y'(0) = B $

$ \frac{d}{d\tau}[p(\tau)\frac{dg(t;\tau)}{d\tau}]+q(\tau)g(t;\tau) = \delta(t-\tau),\;\tau>0,t>0 $

$ g(t;\tau)|_{t<\tau}=0,\;\frac{dg(t;\tau)}{d\tau}|_{t<\tau}=0 $



+ 此时给第一个方程乘以$ g(t;\tau) $，第二个方程乘以$ y(\tau) $，相减：

$ \{\frac{d}{d\tau}[p(\tau)\frac{dg(t;\tau)}{d\tau}]+q(\tau)g(t;\tau)\}y(\tau)-\{\frac{d}{d\tau}[p(\tau)\frac{dy(\tau)}{d\tau}]+q(\tau)y(\tau)\}g(t;\tau) = y(\tau)\delta(t-\tau)-f(\tau)g(t;\tau) $

    - 显然可以先做初步的简化：

$ \{\frac{d}{d\tau}[p(\tau)\frac{dg(t;\tau)}{d\tau}]\}y(\tau)-\{\frac{d}{d\tau}[p(\tau)\frac{dy(\tau)}{d\tau}]\}g(t;\tau) = y(\tau)\delta(t-\tau)-f(\tau)g(t;\tau) $

    - 两侧<font style="color:#DF2A3F;">对</font>$ \tau $<font style="color:#DF2A3F;">在</font>$ (0,+\infin) $<font style="color:#DF2A3F;">区间内积分</font>：

$ y(t) = \int_0^{+\infin} f(\tau)g(t;\tau)d\tau + \int_0^{+\infin}\{\frac{d}{d\tau}[p(\tau)\frac{dg(t;\tau)}{d\tau}]\}y(\tau)-\{\frac{d}{d\tau}[p(\tau)\frac{dy(\tau)}{d\tau}]\}g(t;\tau)d\tau $

    - 右侧可以$ y(\tau),g(t;\tau) $移入微分号内，发现可以保持等式成立，相当于加减了同一个项：

$ RHS = \int_0^{+\infin} f(\tau)g(t;\tau)d\tau + \int_0^{+\infin}\frac{d}{d\tau}[p(\tau)\frac{dg(t;\tau)}{d\tau}y(\tau)]-\frac{d}{d\tau}[p(\tau)\frac{dy(\tau)}{d\tau}g(t;\tau)]d\tau $

    - 此时可以将$ \tau $直接积分一次：

$ RHS = \int_0^{+\infin} f(\tau)g(t;\tau)d\tau + [p(\tau)\frac{dg(t;\tau)}{d\tau}y(\tau)]_0^{+\infin}-[p(\tau)\frac{dy(\tau)}{d\tau}g(t;\tau)]_0^{+\infin} $

$ =\int_0^{+\infin} f(\tau)g(t;\tau)d\tau + p(\tau)[\frac{dg(t;\tau)}{d\tau}y(\tau)-\frac{dy(\tau)}{d\tau}g(t;\tau)]_0^{+\infin} $



    - 考虑到$ y(0) = A,\; y'(0) = B $以及$ g(t;\tau)|_{t<\tau}=0,\;\frac{g(t;\tau)}{d\tau}|_{t<\tau}=0 $：

$ \boxed{
y(t) = \int_0^{t}g(t;\tau)f(\tau)d\tau-p(0)[A\frac{dg(t;\tau)}{d\tau}-Bg(t;\tau)]_{\tau=0}} $

        * $ g(t;\tau)|_{t<\tau}=0,\;\frac{g(t;\tau)}{d\tau}|_{t<\tau}=0 $主要是使$ \tau>t $部分积分为零，一方面修改了第一项积分的上限为$ t $，另一方面第二项的$ \tau=+\infin $端贡献为零。

#### 结果的物理解释
+ 解为：

$ 
y(t) = \int_0^{t}g(t;\tau)f(\tau)d\tau-p(0)[A\frac{dg(t;\tau)}{d\tau}-Bg(t;\tau)]_{\tau=0} $

    - 第一项$ \int_0^{t}g(t;\tau)f(\tau)d\tau $代表了方程非齐次项对于场的影响。
        * 积分范围为$ \tau \in (0,t) $只有存在于当下之前的源才有可能对当下的场产生影响。
    - 第二项$ -p(0)[A\frac{dg(t;\tau)}{d\tau}-Bg(t;\tau)]_{\tau=0} $代表了初始条件对场的影响。

#### 补充证明Green函数的时间倒易性
+ 前面提到变量替换需要用到$ \mathrm{Green} $函数的时间倒易性，即：

$ g(-\tau;-t) = g(t;\tau) $

    - 吴崇试的书中给出了完整的证明：

<img src="https://cdn.nlark.com/yuque/0/2025/png/2371504/1764642263813-e6486678-3ba3-407e-813a-89e6d2646a63.png" width="650" title="" crop="0,0,1,1" id="u95425575" class="ne-image">

<img src="https://cdn.nlark.com/yuque/0/2025/png/2371504/1764642278516-38310715-36d7-4682-a31a-ee7a633433f0.png" width="650" title="" crop="0,0,1,1" id="ufbf21ae3" class="ne-image">

#### 对于微分算符的讨论
+ 原来的定解问题为：

$ \frac{d}{dt}[p(t)\frac{dy(t)}{dt}]+q(t)y(t) = f(t),\;t>0 $

$ y(0) = A,\; y'(0) = B $

+ 可以写成微分算符形式：

$ \hat{L}y(t) = f(t),\; t>0  $

$ y(0) = A,\; y'(0) = B $

    - 其中微分算符$ \hat{L} $的表达式是：

$ \hat{L} = \frac{d}{dt}[p(t)\frac{d}{dt}]+q(t) $

+ 之前我们说到：

> + <font style="color:#8A8F8D;">再写出</font>$ \mathrm{Green} $<font style="color:#8A8F8D;">函数满足的定解问题：</font>
>
> $ \frac{d}{dt}[p(t)\frac{dg(t;\tau)}{dt}]+q(t)g(t;\tau) = \delta(t-\tau),\;\tau>0,t>0 $
>
> $ g(t;\tau)|_{t<\tau}=0,\;\frac{dg(t;\tau)}{dt}|_{t<\tau}=0 $
>
>     - <font style="color:#8A8F8D;">作变量替换</font>$ t\rightarrow -\tau $<font style="color:#8A8F8D;">，</font>$ \tau\rightarrow -t $<font style="color:#8A8F8D;">，这样做是因为</font>$ t<\tau $<font style="color:#8A8F8D;">时</font>$ -\tau<-t $<font style="color:#8A8F8D;">：</font>
>
> $ \frac{d}{d(-\tau)}[p(-\tau)\frac{dg(-\tau;-t)}{d(-\tau)}]+q(-\tau)g(-\tau;-t) = \delta(-\tau+t),\;\tau>0,t>0 $
>
> $ g(-\tau;-t)|_{-\tau<-t}=0,\;\frac{dg(-\tau;-t)}{d(-\tau)}|_{-\tau<-t}=0 $
>
>     - <font style="color:#8A8F8D;">如果有</font>$ p(t) = p(-t),q(t)=q(-t) $<font style="color:#8A8F8D;">，结合</font>$ \mathrm{Delta} $<font style="color:#8A8F8D;">函数的性质，定解问题可以化为：</font>
>
> $ \frac{d}{d\tau}[p(\tau)\frac{dg(-\tau;-t)}{d\tau}]+q(\tau)g(-\tau;-t) = \delta(t-\tau),\;\tau>0,t>0 $
>
> $ g(-\tau;-t)|_{-\tau<-t}=0,\;\frac{dg(-\tau;-t)}{d\tau}|_{-\tau<-t}=0 $
>

+ 其中第二步到第三步，微分算符形式并没有发生变化，还是$ \frac{d}{dt}[p(t)\frac{d}{dt}]+q(t) $的形式。
    - 这依赖于$ \hat{L} = \frac{d}{dt}[p(t)\frac{d}{dt}]+q(t) $的时间反演对称性，这并不是一个普遍的性质。



+ 为了说明这一点，我们引用吴崇试书中对于热传导方程$ \mathrm{Green} $函数的论述：

<img src="https://cdn.nlark.com/yuque/0/2025/png/2371504/1764642698087-b8341e95-2e18-464e-b2a3-50d54f990887.png" width="650" title="热传导方程Green函数，热传导方程微分算符不具有时间反演对称性" crop="0,0,1,1" id="ucc2ee8e3" class="ne-image">

+ 第一处箭头，作变量替换$ t\rightarrow -t' $，$ t'\rightarrow -t $后，微分算符作如下替换：

$ \frac{\partial}{\partial t} \rightarrow \frac{\partial}{\partial (-t')} = -\frac{\partial}{\partial t'} \neq \frac{\partial}{\partial t'} $

    - 可见微分算符形式发生了改变。
    - 究其原因，是因为微分算符$ \frac{\partial}{\partial t} $是一阶微分算符，不具有时间反演对称性。
+ 这一个影响也延续到了后面用$ \mathrm{Green} $函数表示原定解问题的解的过程中。
    - 第二个箭头处应该是减号，如果微分算符具有时间反演对称性。
    - $ \frac{\partial}{\partial t} $不具有时间反演对称性，它在时间反演变换下会编号，导致此处变为加号。



+ 我们也对比说明波动方程$ \mathrm{Green} $函数的论述：

<img src="https://cdn.nlark.com/yuque/0/2025/png/2371504/1764643129546-0e120256-2488-42f5-8895-2ccb5429f5e1.png" width="650" title="波动方程Green函数，波动方程微分算符具有时间反演对称性" crop="0,0,1,1" id="u49aaf454" class="ne-image">

+ 第一处箭头，作变量替换$ t\rightarrow -t' $，$ t'\rightarrow -t $后，微分算符作如下替换：

$ \frac{\partial^2}{\partial t^2} \rightarrow \frac{\partial^2}{\partial (-t')^2} = \frac{\partial^2}{\partial t'^2}  $

    - 可见微分算符形式没有发生改变。
    - 究其原因，是因为微分算符$ \frac{\partial^2}{\partial t^2} $是二阶微分算符，具有时间反演对称性。

#### 推迟格林函数与超前格林函数
+ 上述论述中讨论的都是**推迟格林函数（Retarded Green's Function）**，它要求场只能对之前的源发生响应。
    - 相应地，推迟格林函数满足的定解问题为：

$ \frac{d}{dt}[p(t)\frac{dg_{ret}(t;\tau)}{dt}]+q(t)g_{ret}(t;\tau) = \delta(t-\tau) $

$ g_{ret}(t;\tau)|_{t<\tau}=0,\;\frac{dg_{ret}(t;\tau)}{dt}|_{t<\tau}=0 $

+ 实际上还可以定义**超前格林函数（Advanced Green's Function）**，它要求场只能对之后的源发生响应。
    - 超前格林函数的满足定解问题为：

$ \frac{d}{dt}[p(t)\frac{dg_{adv}(t;\tau)}{dt}]+q(t)g_{adv}(t;\tau) = \delta(t-\tau) $

$ g_{adv}(t;\tau)|_{t>\tau}=0,\;\frac{dg_{adv}(t;\tau)}{dt}|_{t>\tau}=0 $

### 常微分方程边值问题的Green函数
#### 问题概述
+ 用$ \mathrm{Green} $函数方法求解下列定解问题：

$ \frac{d}{dx}[p(x)\frac{dy(x)}{dx}]+q(x)y(x) = f(x),\; a<x<b $

$ y(a) = A,\; y(b) = B $

#### 求解Green函数
+ 上述方程常微分方程初值问题对应的$ \mathrm{Green} $函数满足的定解问题为：

$ \frac{d}{dx}[p(x)\frac{dg(x;\xi)}{dx}]+q(x)g(x;\xi) = \delta(x-\xi),\; a<x<b $

$ g(a;\xi)=0,\;g(b;\xi)=0 $



+ 对于$ x\neq \xi $的部分，相应的定解问题可以改为：

$ \frac{d}{dx}[p(x)\frac{dg(x;\xi)}{dx}]+q(x)g(x;\xi) = 0,\; x\in(a,b), x\neq \xi $

    - 可以设：

$ g(x;\xi) =
\begin{cases}
C_1 y_1(x)+ C_2 y_2(x),a<x<\xi \\
D_1 y_1(x)+ D_2 y_2(x),\xi<x<b
\end{cases} $

    - 由四个未知数$ C_1,C_2,D_1,D_2 $需要求解。
    - 根据定解条件可以对系数进行限定：

$ \boxed{g(a;\xi) = C_1 y_1(a)+ C_2 y_2(a)=0} $

$ \boxed{g(b;\xi) = D_1 y_1(b)+ D_2 y_2(b)=0} $

        * 这是第一个方程和第二个方程。
+ 这样就得到了两个方程，还需要得到两个方程才能求出解，考察连接点$ x=\xi $处$ g(x;\xi) $的行为：
    - 首先，$ x = \xi $处$ g(x;\xi) $应该连续，即：

$ g(\xi-\epsilon;\xi) = g(\xi+\epsilon;\xi),\; \epsilon \rightarrow 0 $

        * 即：

$ \boxed{C_1 y_1(\xi)+ C_2 y_2(\xi) =D_1 y_1(\xi)+ D_2 y_2(\xi)} $

            + 这是第三个方程。



    - 其次，$ x = \xi $处$ \frac{dg(x;\xi)}{dt} $应该产生一个类似于$ k\eta(x-\xi) $行为的跃变，对方程两侧积分：

$ \int_{\xi-\epsilon}^{\xi+\epsilon} \{\frac{d}{dx}[p(x)\frac{dg(x;\xi)}{dx}]+q(x)g(x;\xi)\}dx

= \int_{\xi-\epsilon}^{\xi+\epsilon} \delta(x-\xi)dx,\;a<x,\xi<b,\epsilon\rightarrow 0 $

        * 利用$ \mathrm{Delta} $函数的性质，右侧积分可以化为$ 1 $：

$ RHS = 1 $

        * 左侧可以进行积分：

$ LHS =  [p(x)\frac{dg(x;\xi)}{dt}]|_{x=\xi-\epsilon}^{\xi+\epsilon}+\int_{\xi-\epsilon}^{\xi+\epsilon}q(x)g(x;\xi)dt
,\;a<x,\xi<b,\epsilon\rightarrow 0 $

            + 根据$ x = \xi $处$ g(x;\xi) $应该连续，第二项积分可以化为$ 0 $，$ x\rightarrow \xi $时$ p(x) $没有奇异行为，则可以化为：

$ LHS = p(\xi)[\frac{dg(x;\xi)}{dx}]|_{x=\xi-\epsilon}^{\xi+\epsilon}
= p(\xi)[D_1 y_1'(\xi) + D_2 y_2'(\xi)-C_1 y_1'(\xi) - C_2 y_2'(\xi)] $

        * 由此，可以得到：

$ p(\xi)[D_1 y_1'(\xi) + D_2 y_2'(\xi)-C_1 y_1'(\xi) - C_2 y_2'(\xi)]=1 $

            + 移项：

$ \boxed{D_1 y_1'(\xi) + D_2 y_2'(\xi)-C_1 y_1'(\xi) - C_2 y_2'(\xi)=\frac{1}{p(\xi)}} $

            + 这是第四个方程。



    - 综上，得到方程组：

$ 
\begin{cases}
 C_1 y_1(a)+ C_2 y_2(a)=0\\
D_1 y_1(b)+ D_2 y_2(b)=0 \\
C_1 y_1(\xi)+ C_2 y_2(\xi) =D_1 y_1(\xi)+ D_2 y_2(\xi)\\
D_1 y_1'(\xi) + D_2 y_2'(\xi)-C_1 y_1'(\xi) - C_2 y_2'(\xi)=\frac{1}{p(\xi)}

\end{cases} $

        * 由此可以解出$ C_1,C_2,D_1,D_2 $，带入后得到$ \mathrm{Green} $函数：

$ g(x;\xi) =
\begin{cases}
C_1 y_1(x)+ C_2 y_2(x),a<x<\xi \\
D_1 y_1(x)+ D_2 y_2(x),\xi<x<b
\end{cases} $

#### 用Green函数求出原边值问题的解
+ 先写出原来的定解问题：

$ \frac{d}{dx}[p(x)\frac{dy(x)}{dx}]+q(x)y(x) = f(x),\; a<x<b $

$ y(a) = A,\; y(b) = B $

    - 作变量替换$ x\rightarrow\xi $可得：

$ \frac{d}{d\xi}[p(\xi)\frac{dy(\xi)}{d\xi}]+q(\xi)y(\xi) = f(\xi),\; a<\xi<b $

$ y(a) = A,\; y(b) = B $



+ 再写出$ \mathrm{Green} $函数满足的定解问题：

$ \frac{d}{dx}[p(x)\frac{dg(x;\xi)}{dx}]+q(x)g(x;\xi) = \delta(x-\xi),\; a<x<b $

$ g(a;\xi)=0,\;g(b;\xi)=0 $

    - 作变量替换$ x\rightarrow\xi $，$ \xi\rightarrow x $可得：

$ \frac{d}{d\xi}[p(\xi)\frac{dg(\xi;x)}{d\xi}]+q(\xi)g(\xi;x) = \delta(\xi-x),\; a<\xi<b $

$ g(a;x)=0,\;g(b;x)=0 $

    - 如果$ \mathrm{Green} $函数具有**<font style="color:#DF2A3F;">空间对称性</font>**$ g(\xi;x) = g(x;\xi) $，那么定解问题可以进一步化为：

$ \frac{d}{d\xi}[p(\xi)\frac{dg(x;\xi)}{d\xi}]+q(\xi)g(x;\xi) = \delta(\xi-x),\; a<x<b $

$ g(a;\xi)=0,\;g(b;\xi)=0 $



+ 总结：

$ \frac{d}{d\xi}[p(\xi)\frac{dy(\xi)}{d\xi}]+q(\xi)y(\xi) = f(\xi),\; a<\xi<b $

$ y(a) = A,\; y(b) = B $

$ \frac{d}{d\xi}[p(\xi)\frac{dg(x;\xi)}{d\xi}]+q(\xi)g(x;\xi) = \delta(\xi-x),\; a<x<b $

$ g(a;\xi)=0,\;g(b;\xi)=0 $



+ 第二个式子乘以$ y(\xi) $，第一个式子乘以$ g(x;\xi) $，相减：

$ \{\frac{d}{d\xi}[p(\xi)\frac{dg(x;\xi)}{d\xi}]+q(\xi)g(x;\xi)\}y(\xi)-\{\frac{d}{d\xi}[p(\xi)\frac{dy(\xi)}{d\xi}]+q(\xi)y(\xi)\}g(x;\xi) = \delta(\xi-x)y(\xi)-f(\xi)g(x;\xi) $

    - 可以进行初步的化简，先消去相同的项：

$ \{\frac{d}{d\xi}[p(\xi)\frac{dg(x;\xi)}{d\xi}]\}y(\xi)-\{\frac{d}{d\xi}[p(\xi)\frac{dy(\xi)}{d\xi}]\}g(x;\xi) = \delta(\xi-x)y(\xi)-f(\xi)g(x;\xi) $

    - 两侧<font style="color:#DF2A3F;">对</font>$ \xi $<font style="color:#DF2A3F;">在</font>$ (a,b) $<font style="color:#DF2A3F;">区间内积分</font>：

$ y(x)=\int_a^b f(\xi)g(x;\xi)d\xi +\int_a^b\{\frac{d}{d\xi}[p(\xi)\frac{dg(x;\xi)}{d\xi}]\}y(\xi)-\{\frac{d}{d\xi}[p(\xi)\frac{dy(\xi)}{d\xi}]\}g(x;\xi)d\xi $

    - 右侧，注意到将$ y(\xi),g(x;\xi) $移到中括号中不改变表达式的值，相当于加减了同一项：

$ RHS=\int_a^b f(\xi)g(x;\xi)d\xi +\int_a^b\frac{d}{d\xi}[p(\xi)\frac{dg(x;\xi)}{d\xi}y(\xi)]-\frac{d}{d\xi}[p(\xi)\frac{dy(\xi)}{d\xi}g(x;\xi)]d\xi $

$ =\int_a^b f(\xi)g(x;\xi)d\xi +\int_a^b\frac{d}{d\xi}[p(\xi)\frac{dg(x;\xi)}{d\xi}y(\xi)-p(\xi)\frac{dy(\xi)}{d\xi}g(x;\xi)]d\xi $

    - 这个时候就可以先对$ \xi $积分一次了：

$ RHS = \int_a^b f(\xi)g(x;\xi)d\xi +\{p(\xi)[\frac{dg(x;\xi)}{d\xi}y(\xi)-\frac{dy(\xi)}{d\xi}g(x;\xi)]\}_{\xi=a}^{\xi=b} $

    - 代入定解条件$ y(a) = A,\; y(b) = B $和  $ g(a;\xi)=0,\;g(b;\xi)=0 $：

$ \boxed{y(x) = \int_a^b f(\xi)g(x;\xi)d\xi + Bp(b)\frac{d(x;\xi)}{d\xi}|_{\xi =b}-Ap(a)\frac{d(x;\xi)}{d\xi}|_{\xi =a}} $

#### 结果的物理解释
+ 解为：

$ y(x) = \int_a^b f(\xi)g(x;\xi)d\xi + Bp(b)\frac{d(x;\xi)}{d\xi}|_{\xi =b}-Ap(a)\frac{d(x;\xi)}{d\xi}|_{\xi =a} $

    - 第一项$ \int_a^b f(\xi)g(x;\xi)d\xi $代表所有源对于场的影响的叠加。
    - 后面两项$ Bp(b)\frac{d(x;\xi)}{d\xi}|_{\xi =b}-Ap(a)\frac{d(x;\xi)}{d\xi}|_{\xi =a} $代表边界条件对于场的影响。

#### 补充证明Green函数的空间对称性
+ 前面提到变量替换需要用到$ \mathrm{Green} $函数的空间对称性，即：

$ g(\xi;x) = g(x;\xi) $

+ 下面引用吴崇试书中的证明：

<img src="https://cdn.nlark.com/yuque/0/2025/png/2371504/1764646874460-2e0cb07e-cb9e-456d-a864-57f7387061c8.png" width="650" title="" crop="0,0,1,1" id="u3a77785b" class="ne-image">

<img src="https://cdn.nlark.com/yuque/0/2025/png/2371504/1764646885299-83b37472-e40d-4b05-bc35-d8d0d84a0263.png" width="650" title="" crop="0,0,1,1" id="u0777df50" class="ne-image">

### Green函数方法的一般讨论
#### Green函数方法的求解步骤
1. 写出原来的定解问题。
2. 将原来的定解问题的非齐次项改成$ \mathrm{Delta} $函数，写出相应$ \mathrm{Green} $函数满足的定解问题。
3. 求解$ \mathrm{Green} $函数：
    1. 先考察$ x=\xi,\;t=\tau $两端的齐次问题的一般解。两侧各有2个叠加系数，总共4个叠加系数。
    2. 根据$ \mathrm{Green} $函数满足的边界条件/初始条件列方程，这能列出2个方程。
    3. 根据$ \mathrm{Green} $函数及其导数在$ x=\xi,\;t=\tau $处的连续/跃变行为，这能列出2个方程。
    4. 根据bc中的4个方程求解出a中所说的叠加系数，这也就求出了$ \mathrm{Green} $函数。
    5. 需要说明的是，这只是求解$ \mathrm{Green} $函数的一种方法，在偏微分方程习题中还会见到用$ \mathrm{Delta} $函数按照相应齐次问题本征函数组展开的方式。
4. 用$ \mathrm{Green} $函数表示出原来定解问题的解。
    1. 写出原来的定解问题，进行场变量源变量的变量替换。
    2. 写出$ \mathrm{Green} $函数满足的定解问题，进行场变量源变量的变量替换，再利用空间对称性/时间倒易性将变量替换后的函数换为原来的$ \mathrm{Green} $函数。
    3. ab两个方程分别乘以$ g(x;\xi)/g(t;\tau) $以及$ y(\xi)/y(\tau) $，相减再积分。
    4. 利用$ \mathrm{Delta} $函数化简方程，再代入边界条件/初始条件，求出$ y(x)/y(t) $，即原来定解问题的解。

#### Green函数的物理意义
+ $ g(x;\xi) $反映了在微分算符$ \hat{L} $规则下$ \xi $处点源$ \delta(x-\xi) $对于场点$ x $处的影响。
+ $ g(t;\tau) $反映了在微分算符$ \hat{L} $规则下$ \tau $处点源$ \delta(t-\tau) $对于场点$ t $处的影响。

### 多元函数Green函数方法
#### Green第二公式
+ 之前在用$ \mathrm{Green} $函数叠加出原来定解问题的特解时，由以下步骤：

>     - <font style="color:#8A8F8D;">两侧</font><font style="color:#DF2A3F;">对</font>$ \xi $<font style="color:#DF2A3F;">在</font>$ (a,b) $<font style="color:#DF2A3F;">区间内积分</font><font style="color:#8A8F8D;">：</font>
>
> $ y(x)=\int_a^b f(\xi)g(x;\xi)d\xi +\int_a^b\{\frac{d}{d\xi}[p(\xi)\frac{dg(x;\xi)}{d\xi}]\}y(\xi)-\{\frac{d}{d\xi}[p(\xi)\frac{dy(\xi)}{d\xi}]\}g(x;\xi)d\xi $
>
>     - <font style="color:#8A8F8D;">右侧，注意到将</font>$ y(\xi),g(x;\xi) $<font style="color:#8A8F8D;">移到中括号中不改变表达式的值，相当于加减了同一项：</font>
>
> $ RHS=\int_a^b f(\xi)g(x;\xi)d\xi +\int_a^b\frac{d}{d\xi}[p(\xi)\frac{dg(x;\xi)}{d\xi}y(\xi)]-\frac{d}{d\xi}[p(\xi)\frac{dy(\xi)}{d\xi}g(x;\xi)]d\xi $
>
> $ =\int_a^b f(\xi)g(x;\xi)d\xi +\int_a^b\frac{d}{d\xi}[p(\xi)\frac{dg(x;\xi)}{d\xi}y(\xi)-p(\xi)\frac{dy(\xi)}{d\xi}g(x;\xi)]d\xi $
>
>     - <font style="color:#8A8F8D;">这个时候就可以先对</font>$ \xi $<font style="color:#8A8F8D;">积分一次了：</font>
>
> $ RHS = \int_a^b f(\xi)g(x;\xi)d\xi +\{p(\xi)[\frac{dg(x;\xi)}{d\xi}y(\xi)-\frac{dy(\xi)}{d\xi}g(x;\xi)]\}_{\xi=a}^{\xi=b} $
>

+ 第一行到第二行实际上是用到了勒让德变换，加上了并减去了同一项。
    - 最终第三行到第四行完成了一次积分。



+ 对于多元函数，这称这个步骤用$ \mathrm{Green} $**第二公式**表示：

$ \iiint_V[u(\vec{r})\nabla^2v(\vec{r})-v(\vec{r})\nabla^2u(\vec{r})]d\vec{r} = \oiint_\Sigma [u\nabla v-v\nabla u]\cdot d\vec{\Sigma} $

    - 其中$ \Sigma $是体积$ V $的外边界面，并且规定外法线方向为正。
    - 这一个公式可以简称为$ \mathrm{Green} $公式。

#### 多元函数Green函数方法研究的内容
1. 对于不同的偏微分算符，$ \mathrm{Green} $函数应该如何求解。如何使用$ \mathrm{Green} $函数叠加出原来的定解问题的解。
2. $ \mathrm{Green} $函数在源点附近的行为，即偏微分算符规定的物理定律下，点源产生的影响（场）如何。
    1. 例子：一维的点源相当于二维的线元、三维的面元，因此渐进行为自然不与二维三维的点源相同。
3. $ \mathrm{Green} $函数的其他性质
    1. 例如电象法。
