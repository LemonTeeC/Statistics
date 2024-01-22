# lecture 3-4

### Poisson Distribution and Exponential Distribution: How do we get them?

在miss cat的课上，他并没有十分清楚讲解我们得到Poisson Distribution的motivation，但理解这个motivation对我们理解Poisson distribution and Exponential distribution有重要的帮助.

首先我们回顾一下二项分布，它所表达的是n重伯努利试验，事件A发生k次的概率，具体有:

$$
P(X=k)=\binom{n}{k}p^k(1-p)^{n-k}
$$

现在，让我们来思考一个更加复杂的情况，我们给定一个度量$M^{[1]}$，这个$M$可以是时间$t$，也可以是空间或者其他抽象的事情. 为了方便理解，我们认为这个度量$M$是时间$t$，现在我们想知道在这个度量上，某一伯努利试验A发生k次的概率. 我们首先提出两个假设：

1. 我们可以将时间$t$分割成$n$份，当$n$充分小时，在$\frac{t}{n}$里，只能发生一次伯努利试验
2. 每一次实验都是独立的

我们注意到，每次分割的次数其实都服从单点分布，所以在整个时间段$t$里，A发生的总次数就是一个二项分布. 同时，我们也发现，单点分布的概率p应该和n有关，时间间隔越短理论上概率应该越小，我们假定p和这个时间段存在一个线性关系，$p_n =  \tilde\lambda\sdot\frac{t}{n}$，其中$\tilde\lambda$是一个参数.

于是我们就可以得到总的发生次数，有$P(X=k)=\lim\limits_{n\to \infty}\binom{n}{k}p^k_n(1-p_n)^{n-k}$

经过一些简单的运算，我们得到:

$$
P(X=k) = e^{-\tilde\lambda t}\sdot\frac{(\tilde\lambda t)^k}{k!}
$$

我们令$\tilde\lambda t = \lambda$, 于是就有:

$$
P(X=k) = e^{-\lambda}\sdot\frac{\lambda^k}{k!}
$$

我们现在思考一下$\tilde\lambda$和$\lambda$的含义，易得$\tilde\lambda=\frac{np_n}{t}$，$\lambda=np_n$. 可以看到$\lambda$表达的是，时间t里事件A的发生率，如果将$\frac{t}{n}$定义为单位时间，那$\tilde\lambda$也就是说在单位时间里，事件A发生的平均数(或者事件A的概率).

在充分理解Poisson Distribution之后，我们可以思考Exponential Distribution表达了什么. 我们通过茆诗松的《概率论与数理统计教程》第102页的例2.5.5来理解Exponential Distribution. 

这题告诉我们如果某设备发生故障的次数N(t), (故障次数和t有关),   $N(t) \sim P(\lambda t)$, 则相继两次故障之间的时间间隔T，$T \sim Exp(\lambda)$. 直觉告诉我们, 如果 $\lambda$很大，即单位时间故障发生率很大，那么故障之间的时间间隔就应该很短，所以我们可以认为Poisson Distribution and Exponential Distribution的$\lambda$具有相同的含义. 我们发现$E(T) = \frac{1}{\lambda}$, 期望的意思也就每次故障的平均时间间隔，这里可以看到$\lambda$越大，那么故障之间的时间间隔就越短.

再举一个例子，如果$X \sim Exp(\lambda)$, 那$Y= \lambda X$又有什么样的含义？我们知道对于X，每次故障的平均时间间隔为$\frac{1}{\lambda}$, 那对于Y，每次故障的平均时间间隔变为1. 这样的话，$\lambda$就成了一个尺度参数(rate parameter), 它将单位时间再做了一次定义，变成了每次故障的平均时间间隔. (事实上，$Y \sim Exp(1)$ )$^{[2]}$

所以我们就可以从两个层面去理解$\lambda$，一个是事件发生率，一个是尺度参数.

**remark:**
[1]: 此处的度量是平凡的字面意思，并非度量空间的度量, i.e. 如$(\R^2, d_{l^2})$

[2]: 如果$X \sim Exp(\lambda)$, 那$Y= \lambda X \sim Exp(1)$

Proof: 考虑分布函数,

 $F_Y(y)=P_Y(Y\leq y)=P_X(\lambda X\leq y)=P_X(X\leq \frac{y}{\lambda})=1-e^{-y}\  \ \ \ \ \ \  \boxtimes$

**reference:**

1. 初等概率论 邓婉璐
2. 《概率论与数理统计教程》茆诗松

---

### How do we get Gamma distribution?

We note that when $\alpha = 1$, Gamma distribution becomes Exponential distribution i.e. $Ga(1,\lambda)=Exp(\lambda)$

As we know Exponential distribution measures the first time of a failure, so intuitively, we think $Ga(n, \lambda)$ measures the total time of n failures. Thus  $Ga(n,\lambda)=n \cdot Exp(\lambda)$

---

### 负超几何分布

超几何分布讨论的是不放回抽样模型里，给定总抽取次数，抽到k次白色的球概率。$X\sim H(w,b,n)$

$$
P(X=k)=\frac{\binom{w}{k} \binom{b}{n-k}}{\binom{w+b}{n}}
$$

负超几何分布讨论的是直到抽到r次黑色的球为止，抽到k次白球的概率

我们知道一共有r+k次抽取，最后一次一定是黑球，所以前r+k-1次抽取中，黑球和白球可以任意组合。有

$$
 P(X=k)=\frac{\binom{w}{k} \binom{b}{r-1}}{\binom{w+b}{r+k-1}}\cdot \frac{b-r+1}{w-r-k+1}
$$

我们也可以换一种思路，