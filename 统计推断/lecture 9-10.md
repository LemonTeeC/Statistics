# lecture 9-10

### 个别假设检验的处理手法

在计算p值时，我们发现under $H_0$, test statistics的分布若是正态分布或者t分布这种对称分布就有很好的p值公式, 特别是处理双边检验问题的时候, 我们可以得到

$$
\begin{split}p &= P(|T|\geq|t_0| \ given \ H_0 \ is \ true) \\
&=P(T \geq |t_0|)+P(T \leq -|t_0|)
\end{split}
$$

可以看到，两个概率是相等的.

但是, 如果检验统计量的分布不是对称的，例如卡方分布和F分布，我们处理双边检验的p值就需要额外小心, 比如卡方分布, 我们会得到两个尾部概率$P(\chi^2 \leq\chi^2_0)$ 和 $P(\chi^2 \geq\chi^2_0)$, 但由于卡方分布不是对称的, 这两个概率并不相等, 但对于假设检验, 我们的核心是拒绝域, 所以我们若选取一个更小的尾部概率就可以保证有一个更强的证据去落到拒绝域，所以有

$$
p= 2 \min \big\{ P(\chi^2 \leq\chi^2_0), \  P(\chi^2 \geq\chi^2_0)\big\}
$$

另外一个需要注意的是两单点分布样本的大样本检验. 例如$X_i \sim b(1,p_1)$, $Y_j \sim b(1, p_2)$, 我们提出假设检验$H_0: p_1=p_2 \leftrightarrow H_1:p_1 \neq p_2$ , 由中心极限定理我们有

$$
\begin{equation}\frac{\bar{X}-p_1}{\sqrt{p_1(1-p_1)/n}} \xrightarrow{d}N(0,1)
\end{equation}
$$

同时我们知道$\bar{X}(1-\bar{X})$是$p_1(1-p_1)$的consistent estimator, 又由continuous mapping theorem和slusky theorem得到

$$
\begin{equation}
\frac{\sqrt{p_1(1-p_1)/n}}{\sqrt{\bar{X}(1-\bar{X})/n}} \xrightarrow{p}1
\end{equation}
$$

再$(1) \times (2)$, 并由slusky theorem, 

$$
\frac{\bar{X}-p_1}{\sqrt{\bar{X}(1-\bar{X})/n}} \xrightarrow{d}N(0,1)
$$

于是可以得到

$$
\frac{\bar{X}-\bar{Y}-(p_1-p_2)}{\sqrt{\bar{X}(1-\bar{X})/n + \bar{Y}(1-\bar{Y})/m}} \xrightarrow{d}N(0,1)
$$

under $H_0$, 我们可以构建检验统计量, 但**此处需要特别注意, 由于此时$p_1=p_2$, 我们分母的$\bar{X}$和$\bar{Y}$需要统一替换成$\hat{p}_0$,where** 

$$
\hat{p}_0=\frac{n\bar{X}+m\bar{Y}}{n+m}
$$

此时有test statistics, 但分子无需替换, 原因在于$\bar{X}$和$\bar{Y}$是随机变量

$$
 T(\bold{X})=\frac{\bar{X}-\bar{Y}}{\sqrt{\hat{p}_0(1-\hat{p}_0)/n + \hat{p}_0(1-\hat{p}_0)/m}} 
$$