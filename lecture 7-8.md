# lecture 7-8

首先, 我们看两个假设检验 $H_0: \mu=25 \leftrightarrow H_a:\mu>25$ 以及 $H_0: \mu\leq25 \leftrightarrow H_a:\mu>25$, 对于这两个假设检验，我们的procedure是一样，所以我们对二者不加以区分. 原因在于我们拒绝$H_0$是当检验统计量T(X)远远大于25, 那么当T(X)远远大于25，它自然远远偏离小于25的数字. 

当然, 我们可以更严格地证明这一件事情. $H_0: \mu=\mu_0 \leftrightarrow H_a:\mu>\mu_0$, 有拒绝域 $R= \{ \vec{x}:\sqrt{n}(\vec{x}-\mu_0)/\sigma >z_{\alpha} \}$, **在这个拒绝域下**，如果 $\alpha(\mu_{\star})<\alpha(\mu_0)$ , 那么可以知道若能在拒绝域$R$拒绝 $\mu=\mu_{\star}<\mu_0$, 自然可以在一个更大的第一类错误的情况下拒绝$\mu = \mu_{\star}$

我们知道拒绝域和接受域构成了一个全集，那么在**给定样本量**的情况下，一个越大另一个就越小，自然第一类错误概率越大，第二类错误概率越小，反之亦然，二者不能同时很小. 虽然我们不想错误的拒绝原假设，但想正确拒绝原假设, 所以我们要让错误拒绝原假设（第一类错误）的概率很小，这对应的概率$\alpha$ 称做 significance level. 我们对这个东西的理解依旧是从频率近似概率，我们不断进行抽样，不断重复，最后发现有约 $\alpha \%$ 的样本统计量错误拒绝了 $H_0$ , 即犯了第一类错误. $\alpha$越小，越少第一类错误发生，反过来说，一旦 $H_0$ 真的被拒绝, 这其实提供了一种信念，告诉我们$H_0$有可能真的错了, T(X) 给出的against $H_0$的信息其实非常可靠. (To be more precise, the errors come from our test statistics or the test procedure.)

我们给出一个更严格的定义：

$\alpha(\theta)=P_{\theta}(X \in W), \theta \in \varTheta_0$,   $\beta(\theta)= P_{\theta}(X \in {W^c}), \theta \in \varTheta_1$

我们定义power function ( It means the power of the test procedure ):

$$g(\theta)=
\begin{cases}
\alpha(\theta) , \theta \in \varTheta_0\\
1-\beta(\theta), \theta \in \varTheta_1
\end{cases}$ or   $\begin{cases}
\alpha(\theta)=g(\theta), \theta \in \varTheta_0\\
\beta(\theta)=1-g(\theta), \theta \in \varTheta_1
\end{cases}$$

可以见到power function 表达的是X在不同参数空间下，落入拒绝域的概率. 在$H_0$为真的情况下, $g(\theta)$就是第一类错误的概率，在$H_a$为真的情况下，$g(\theta)$就是正确的概率

我们知道在significance level不同的情况下，同样的样本可以导致不同的结论，即可能接受 $H_0$ 或者拒绝 $H_0$ . 这是很好理解的，比如当$\alpha$越来越小，拒绝域就越来越小，原本能落入拒绝域的样本就落入了接受域，这导致假设检验的结果改变. 那我们现在反过来想，在假设 $H_0$ 为真的情况下, 我们直接通过一个样本观察值去构造一个最小的能够拒绝 $H_0$ 的significance level, (or, p-value is the probability, assuming that $H_0$ is true, of obtaining a value of the test statistics at least as contradictory to $H_0$ as the value calculated from the available sample.) 我们把这个值叫做p-value, 当然, p-value随着不同样本而改变. 

现在我们思考 $p$ 和 $\alpha$ 之间的关系，我们或许可以这样思考，$p$是一种比较客观的significance level因为它是直接从样本算出来的, 而$\alpha$是我们心目中的significance level, 它是我们在一开始就存在的偏见，我们认为有 $\alpha$ 这么大比例的第一类错误会发生. 可是当 $\alpha \geq p$ , 我们就发现事实好像没有那么糟糕, 也许这个世界上不会有 $\alpha$ 那么多的第一类错误会发生, 发生错误的比例应该是小于 $\alpha$ 的, 我们的偏见实在是太多了. 回到我们最开始的想法，我们不想错误的拒绝 $H_0$ 但想正确的拒绝 $H_0$ , 那么现在我们就应该放下偏见，我们可以认为我们不会再错误的拒绝它了, 所以若 $\alpha \geq p$，则在显著性水平 $\alpha$ 下拒绝 $H_0$ . (或者说$p$越小就给我们更多的信念或者证据去拒绝$H_0$并且不拒绝$H_a$) 反过来，若 $\alpha <p$ , 则在显著性水平 $\alpha$ 下不拒绝 $H_0$ , 背后的道理无非就是将上面的故事反过来说一遍. 

不过有趣的是，我们一般会把我们一开始认为正确的东西放在零假设上，注意这只是一开始认为正确，我们现在非常想验证它，所以 
 $H_0$ 上的东西是我们非常想验证的东西. 所以当 $\alpha$ 很小, 原假设不容易被否定，但样本却落入了拒绝域，让我们否定了原假设，这时我们认为”拒绝原假设的结论就很可靠”. 但反过来， $\alpha$ 很小, 样本落入了接受域, 作出“接受 $H_0$ ”的结论并不可靠，这只能说明我们没有充分证据去拒绝它，但绝非有充分根据去说明它正确（此时我们会犯第二类错误，而且概率很大)

*不拒绝 $\neq$ 接受

REMARK: 在一些中文教科书上，第一类错误和第二类错误分别被翻译成弃真和取伪，很浪漫的名字

---

在能够接受假设检验之后，我们现在考虑具体检验的构造方法.

- 建立 $H_0 \leftrightarrow H_a$
- 根据 $H_0$ 和 $H_a$ 的特点选择 $T(X)$ 和拒绝域, 并且当 $H_0$ 成立时, $T(X)$的分布要完全已知

EXAMPLE: 比如假设是关于$\mu$的, 很自然的一个想法就是用$\bar{X}$去做近似, 比较$\bar{X}$和$\mu$, 于是我们得到一个拒绝域$R = \{ \bar{X}< \ or >c\}$, 而且我们知道$\bar{X}$的分布, $\bar{X} \sim N(\mu, \sigma^2/n)$, 当$H_0$成立，$\mu$已知，$\bar{X}$的分布就完全已知，我们就可以可以算出一个具体的概率$\alpha$，比如

$$
\alpha(\theta)=\Phi\bigg(\frac{c-\theta}{\sigma/\sqrt n}\bigg)
$$

不过值得注意的是, 虽然$\alpha$是$\theta$的函数, 但$\alpha$也可以看成待定参数$c$的函数, 如果我们想控制$\alpha$, 我们会反过来控制$c$

- 选择我们想要的$\alpha$, 确定拒绝域, 即确定参数$c$
- 检查假设统计量是不是在拒绝域内

REMARK: 我之前一直没有搞明白这里的逻辑，12.8的时候仔细想了想发现逻辑是这样的：我们拒不拒绝$H_0$其实就只看检验统计量，$H_0$只有对和错没有随机性，有随机性、有概率的是我们检验的过程. 我们控制第一类错误的概率, 其实是控制我们检验过程犯错的概率，当这个检验犯错的概率足够低，我们就可以在$T \in R$
的时候放心拒绝$H_0$

现在思考p-value的构造方法，准确的说是正态分布p-value的构造方法, 我们首先通过样本观察值算出一个$z_0$，我们再思考如果我们再抽样，再获得一个样本观察值，那新的值和这个$z_0$应该是什么关系？

首先考虑$H_0:\mu=\mu_0 \leftrightarrow H_a: \mu >\mu_0$的情况, 如果我们新的样本观察值能够更加contradictory to $H_0$, in favour of $H_a$, 自然说明新的样本观察值有更大的偏差, 所以新的值应该大于$z_0$, 所以

$$
p=P(Z\geq z_0 \ when \ H_0 \ is \ true)=1-\Phi(z_0)
$$

所以$H_0:\mu=\mu_0 \leftrightarrow H_a: \mu <\mu_0$, $p=\Phi (z_0)$

最后一种情况$H_0:\mu=\mu_0 \leftrightarrow H_a: \mu \neq \mu_0$, 既然我们要infavor of $H_a$，并且contradictory to $H_0$, 但这时候就涉及正负数的问题, 但我们可以添加绝对值, 只讨论数值的距离, 所以只需要$|z|$偏离$|z_0|$即可, 有

$$
\begin{split}
p&=P(|Z| \geq |z_0| \ when \ H_0 \ is \ true) \\
&=P(Z \leq-|z_0|  \ or \ Z \geq |z_0| \ when \ H_0 \ is \ true)\\
&=2(1-\Phi(|z_0|))
\end{split}
$$
