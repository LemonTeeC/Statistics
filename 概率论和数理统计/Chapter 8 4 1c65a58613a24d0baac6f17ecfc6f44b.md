# Chapter 8.4

先回顾一下线性代数中我们如何处理最小二乘问题$A\bold{x}=\bold{b}$, 我们想找一个x使得

$$
||\bold{b}-A\hat{\bold{x}}||<||\bold{b}-A\bold{x}||, \forall \bold{x} \in \R^n
$$

如果$\bold{b}$本身在C(A)上, 那么必然存在$\bold{x}$使得不等式的左侧为0, 这组解显然是最小二乘解, 但很多时候$\bold{b} \notin C(A)$, 所以最小二乘解必然是$\bold{b}$在$C(A)$上的投影, 我们把这个投影denote as $\hat{\bold{b}}$, 显然有

$$
A\hat{\bold{x}}=\hat{\bold{b}}
$$

那么有 $\hat{\bold{b}}-A\hat{\bold{x}} \perp C(A)$, 等价的有$\bold{a_j} \cdot (\hat{\bold{b}}-A\hat{\bold{x}} )=0 \iff \bold{a_j} ^T (\hat{\bold{b}}-A\hat{\bold{x}} )=0$. 将所有的列向量组成矩阵, 就有

$$
A^T (\hat{\bold{b}}-A\hat{\bold{x}} )=0
$$

整理可得

$$
A^TA\bold{x}=A^T\bold{b}
$$

回到一元线性回归的最小二乘问题, 我们想对方程求解, 使得sum of square of residuals最小

$$
\begin{pmatrix}
  1 & x_1 \\
  1 & x_2 \\
  \vdots & \vdots \\
1 & x_n
\end{pmatrix}
\begin{pmatrix}
  \beta_0  \\
  \beta_1  \\
\end{pmatrix}=
\begin{pmatrix}
  y_1  \\
  y_2  \\
\vdots \\
y_n
\end{pmatrix} \iff X \vec{\beta}=\bold{y}
$$

我们想找$\beta$使得 squares of residuals最小其实就是使得$||\bold{y}-X\vec{\beta}||$最小(将其写成scalar form即可验证), 所以这里的$\beta$依然是$\bold{y}$在$C(X)$上的投影对应的线性组合的系数. 

---

用微积分的方法就是解决优化问题

$$
\argmin_{\beta_0,\ \beta_1}\sum^n_{i=1}(y_i-\beta_0-\beta_1x_i)^2
$$

令$Q(\beta_0,\beta_1) = \sum^n_{i=1}(y_i-\beta_0-\beta_1x_i)^2$,解得( we call the left one Normal Equations)

$$
\begin{cases}
\frac{\partial Q}{\partial \beta_0}=0, \\ 
\frac{\partial Q}{\partial \beta_1}=0 
\end{cases}
\Rightarrow
\begin{cases}
\hat{\beta}_1=\frac{l_{xy}}{l_{xx}}, \\ \hat{\beta_0}=\bar{y}-\hat{\beta}_1\bar{x}
\end{cases}
$$

where

$$
l_{xy}=\sum(x_i-\bar{x})(y_j-\bar{y}) \\l_{xx}=\sum(x_i-\bar{x})(x_i-\bar{x}) \\
l_{yy}=\sum(y_j-\bar{y})(y_j-\bar{y})
$$

 有两个有趣的式子, $\hat{y}_i=\hat\beta_0+\hat\beta_1 x_i$ and $\bar{y}=\hat\beta_0+\hat\beta_1 \bar{x}$

we have some nice properties

- $\hat{\beta}_0 \sim N(\beta_0, (1/n+ \bar{x}^2/l_{xx})\sigma^2)$, $\hat{\beta}_1 \sim N(\beta_1, \sigma^2/ l_{xx})$
- $Cov(\hat{\beta}_0,\hat{\beta}_1)=-\bar{x}\sigma^2/l_{xx}$
- given $x_0$, $\hat{y}_0=\hat{\beta}_0+\hat{\beta}_1x_0 \sim N(\beta_0+\beta_1x_0, (1/n+ (x_0-\bar{x})^2/l_{xx})\sigma^2)$

证明不难, 主要还是熟练度, 涉及一些比较subtle的变换

比较值得注意的是, 想要提高估计精度, 也就要求given $x_0$, $\hat{y}_0$的方差更小, 要么n更大, 要么$l_{xx}$更大

(要求$x_1, ...,x_n$更加分散, 意味着提供更长的区间的信息)

---

对于回归方程, 一个值得注意的点是我们关注的是**y的期望**, 这是因为y本身是个随机变量, 我们关注y的取值并没有意义, 因为我们无法控制, 但期望是确定的，所以回归方程就是从$E(y)=\beta_0+\beta_1x$推广到$\hat{y}=\hat{\beta}_0+\hat{\beta}_1x$, where $\hat{y}=\hat{E}(y)$

和anova类似, 我们有 sum of square of regression $SSR= \sum (\hat{y}_i-\bar{y})^2=\hat\beta_1^2l_{xx}$ (我们可以认为这是回归方程可以解释的方差, 回归值和真值的差的平方和)

sum of square of error $SSE=\sum (\hat{y}_i-y_i)^2$（这是无法被回归线解释的部分）

total sum of squares $SST= \sum (y_i-\bar{y})^2=l_{yy}$, 又有$SST=SSE+SSR$

于是我们定义 coefficient of determination $R^2 := 1- SSE/SST$，这告诉我们方差可解释的比例有多大. $R$ 我们一般称为相关系数. 

对于这几个随机变量，有以下性质   ($S_R=SSR, S_e=SSE)$

- $E(S_R)=\sigma^2+\beta_1^2l_{xx}$
- $E(S_e)=(n-2)\sigma^2 \Rightarrow S_e/(n-2)$  is unbiased estimator of $\sigma^2$
- $S_e /\sigma^2 \sim \chi^2(n-2)$ ( 计算$\hat{\beta_0},\hat{\beta_1}$使用了两个自由度）
- under $H_0$, $S_R/\sigma^2\sim \chi^2(1)$
- $S_e, \ S_R$   and $\bar{y}$ are mutually independent

Under $H_0$, we can have 2 test statistics for $H_0:\beta_1=0 \leftrightarrow H_1:\beta_1 \neq 0$

$$
F=\frac{S_R}{S_e/(n-2)}\sim F_{1, \ n-2} \   ,  \ R=\{F \geq F_\alpha(1,n-2)\}
$$

如果$H_0$为真，这说明y和x完全没有线性关系，那么SSR应该相当小，SSE应该相当大，整个比例就应该相当小. 反过来，如果F很大，就应该拒绝原假设

Also, we have

$$
t=\frac{\hat{\beta}_1-\beta_1}{\hat{\sigma}/\sqrt{l_{xx}}}\sim t(n-2), \ R=\{|t|>t_{\alpha/2}(n-2)\}
$$

where $\hat{\sigma} = \sqrt{S_e/(n-2)}$, we also call $\hat{\sigma}^2$ least squares estimate of $\sigma^2$

REMARK: 需要注意，t检验在这里的普适性更强，他可以同时应付单边和双边检验. 但是F检验只能够用于双边检验，这主要因为F是比例，而$\hat{\beta}_1$服从正态分布. 更有趣的是, 我们可以证明$F=t^2$, 这某种意义上也说明F检验只适用于双边检验, 因为平方之后没有正负就失去了方向性.