# Probability and Statistics

该笔记根据茆诗松所著的《概率论与数理统计教程》进行编写，主要记录个别难题的intuition，若有英语的语法错误，当没看到即可

| Distribution | f(x) | E(X) | Var(X) | $M_X(t)$ | REMARK |
| --- | --- | --- | --- | --- | --- |
| b(n,p) | $\binom{n}{k}p^k(1-p)^{n-k}, [0,n)$ | np | np(1-p) | $(1-p+pe^t)^n$ | 独立可加：b(n+m,p) |
| $P(\lambda)$ | $\frac{\lambda^k}{k!}e^{-\lambda}, [0,\infty)$ | $\lambda$ | $\lambda$ | $e^{\lambda (e^t-1)}$ | 独立可加：$P(\lambda_1+\lambda_2)$ |
| HGem(w,b,n)  不返回抽样 | $\frac{\binom{w}{k}\binom{b}{n-k}}{\binom{w+b}{n}}$ | $\frac{nw}{w+b}$ | $\frac{N-n}{N-1}np(1-p)$ |  | 可以由n个不独立但同分布的二项分布相加求得  $b(1,\frac{w}{w+b})$ |
| Ge(p) | $(1-p)^{k-1}p, [1,\infty)$ | $\frac{1}{p}$ | $\frac{1-p}{p^2}$ | $pe^t/[1-(1-p)e^t]$ | 独立可加：负二项分布 |
| Nb(r,p) | $\binom{k-1}{r-1}(1-p)^{k-r}p^r$ | $\frac{r}{p}$ | $\frac{r(1-p)}{p^2}$ | $[pe^t/(1-(1-p)e^t)]^r$ | 给定成功次数求总次数/ 失败次数 |
| U(a,b) | $\frac{1}{b-a}$ | $\frac{a+b}{2}$ | $\frac{(b-a)^2}{12}$ | $(e^{tb}-e^{ta})/t(b-a)$ | 由于$Y=F_X(X)\sim U(0,1)$, U是universal的 |
| $Exp(\lambda)$ | $\lambda e^{-\lambda x}, [0,\infty)$ | $\frac{1}{\lambda }$ | $\frac{1}{\lambda^2}$ | $\lambda/(\lambda-t)$ | 独立可加：因为$Exp(\lambda)=Ga(1,\lambda)$, 所以$X_1+...+X_n\sim Ga(n,\lambda)$ |
| $Ga(\alpha,\lambda)$ | $\frac{\lambda^\alpha}{\Gamma(\alpha)}x^{\alpha -1}e^{-\lambda x}, [0,\infty)$ | $\frac{\alpha}{\lambda }$ | $\frac{\alpha}{\lambda^2}$ | $(\lambda/(\lambda-t))^\alpha$ | 独立可加：$Ga(\alpha_1+\alpha_2,\lambda)$ |
| $Be(a,b)$  | $\frac{\Gamma(a+b)}{\Gamma(a)\Gamma(b)}x^{\alpha -1}(1-x)^{b-1},(0,1)$ | $\frac{a}{a+b}$ | $\frac{ab}{(a+b)^2(a+b+1)}$ |  | when p(x)=$ax^{a-1},X\sim Be(2,1)$ |
| $\chi^ 2(n)$ | $\frac{x^{n/2-1}e^{-x/2}}{\Gamma(n/2)2^{n/2}}$, $[0,\infty)$ | n | 2n | $(1/(1-2t))^{n/2}$ | 即$\alpha=n/2, \lambda=1/2$的Ga分布,独立可加 |
| $N(\mu, \sigma^2)$ | $\frac{1}{\sqrt{2 \pi}\sigma }e^{\frac{-(x-\mu)^2}{2\sigma^2}}$ | $\mu$ | $\sigma^2$ | $e^{\mu t+\sigma^2t^2/2}$ | 可加：$aX_1+bX_2 \sim N(\mu_1+\mu_2, a\sigma^2_1+b\sigma^2_2)$; $X \sim N(0,1),X^2 \sim \chi^2(1)$ |


$$
\begin{split}

\Gamma(\alpha)=\int^{\infty}_0x^{\alpha-1}e^{-x}dx, \ \Gamma(\frac{1}{2})&=\sqrt{\pi}, \ \Gamma(n+1)=n\Gamma(n)=n!\\

B(a,b)&=\int^1_0x^{a-1}(1-x)^{b-1}dx=\frac{\Gamma(a)\Gamma(b)}{\Gamma(a+b)}
\end{split}

$$

[Chapter 3.3](Probability%20and%20Statistics%2017fce9bf27174c53be10f62cfd70e598/Chapter%203%203%20543122032c2d4307a764572905121915.md)

- Introduce how to find joint distribution and pdf of random vectors

---

> Remember that the integration area of marginal pdf is restricted.
> 

[Chapter 3.4](Probability%20and%20Statistics%2017fce9bf27174c53be10f62cfd70e598/Chapter%203%204%208bc4dde289184b5bbbf750f5386b442a.md)

- Introduce covariance, correlation and their operations of n-dimensional random variables.

---

> Given 2 variables X and Y, and we need to find E(XY),  always find the density function or pmf of (X,Y) first. Then use the definition of expectation to find the answer.
> 

[Chapter 3.5](Probability%20and%20Statistics%2017fce9bf27174c53be10f62cfd70e598/Chapter%203%205%204472a39f10a8498f8ba35095657460d7.md)

- Introduce conditional distribution and expectation

---

> Note that p(x|y) have range of x under restriction of y. Thus E(X|Y) also have range of x under restriction of y.
> 

> Note that p(x|y) = p(x) if X and Y are independent random variables. which is easy to prove since we have $p(x|y)=\frac{p(x,y)}{p(y)} = \frac{p(x)p(y)}{p(y)}$
> 

[Chapter 4.1](Probability%20and%20Statistics%2017fce9bf27174c53be10f62cfd70e598/Chapter%204%201%209e698361ff6844e8a3fab8d6be2a8db9.md)

- Introduce convergence to probability and convergence to distribution

---

> Very hard, the proof is fucking difficult
> 

[Chapter 4.2](Probability%20and%20Statistics%2017fce9bf27174c53be10f62cfd70e598/Chapter%204%202%207c71a814bc0847d0bd9a05fce36d2b51.md)

- Introduce characteristic function of random variables

---

> we can use the limit of characteristic function to prove that a distribution converges to another distribution
> 

[Chapter 4.3](Probability%20and%20Statistics%2017fce9bf27174c53be10f62cfd70e598/Chapter%204%203%20e0f1d7a5c9354a7dbe7651b4dc1db6a3.md)

- Introduce law of large numbers and different theorem to determine whether {Xn} obeys the law

---

> Well, I think the most important thing in this chapter is to remember the Taylor expansion.
> 

$$
f(x)=\sum^{\infty}_{n=0}\frac{1}{n!}f^{(n)}(x_0)(x-x_0)^n+R_n(x), \ x \to x_0\\
R_n(x)=
o(x-x_0)^n \ \ or\\
\ \ \ \ \ \ \ \ \  \ \ \ \ \ \ \ \ \ \  \ \ \ \ \ \ \ \  \ \ \ R_n(x)=\frac{f^{(n+1)}(\xi)}{(n+1)!}(x-x_0)^{n+1}, \ \xi \in(0,1)

$$

[Chapter 5.3](Probability%20and%20Statistics%2017fce9bf27174c53be10f62cfd70e598/Chapter%205%203%209919de6328204cd2b5d2a19c93652526.md)

- 这一章的内容困扰了我很久，主要是我最开始直接跳了5.1和5.2，搞得没能理解清楚**总体，个体，样本，**后面搞得也看不懂什么事次序统计量. 经过回头复习，终于搞明白了

---

> 所谓的**总体**就是一个巨大的样本，这个总体里面包含了无限个个体(个体是一些数字)，同时这无限个体都遵从一种规则产生，我们把这个规则称为分布，所以无限个体都是同分布的. 于是从总体抽样$\iff$从分布抽样
> 

我们从无限个体抽出有限个个体，记n个个体. 我们把这n个个体统称为一个样本. (一般这样表达: $x_1,x_2,...,x_n$是一个样本). 我们抽出的个体在观察之前是未知的，所以具有随机性，他们是随机变量，可以记成$X_1,X_2,...,X_n$. 那在观察之后，我们就知道了每一个个体确定的值，所以我们又可以记录成$x_1,x_2,...,x_n$.  一般为了方便，我们会记录成$x_1,x_2,...,x_n$. 

我们提到过，所有$X_1,X_2,...,X_n$都是由一个分布生成的，所以$X_1,X_2,...,X_n$是同分布的

我们又认为抽样是独立的，因为我们先抽一个个体，但由于总体很大，下一个被抽到的个体是不会被影响的. 所以$X_1,...,X_n$又是独立的

现在有一个样本$x_1,x_2,...,x_n$，把这些样本的观察值进行排序，我们就得到了次序统计量，记为$x_{(1)},x_{(2)},...,x_{(n)}$

现在回过头看，发现对于随机变量的理解最重要的就是分清楚**随机**和**变量**两个词的意思，在观察之前我们不知道$X(\cdot)$ 取值，所以它是变量，在观察之后，但所谓的观察就是我们从样本空间 $\Omega$ $\Omega$$\omega$  ,通过映射$\omega \mapsto X(\omega)$, 得到了一个常数值 ，$X(\omega)$是确切的，随机性就体现在寻找$\omega$ 这件事情上

---

[Chapter 5.4](Probability%20and%20Statistics%2017fce9bf27174c53be10f62cfd70e598/Chapter%205%204%204a9137b53fe34832b2a792690624e4cf.md)

---

[Chapter 6.1](Probability%20and%20Statistics%2017fce9bf27174c53be10f62cfd70e598/Chapter%206%201%20dbd84bdb78014332b7b280e09c310794.md)

---

[Chapter 7.5](Probability%20and%20Statistics%2017fce9bf27174c53be10f62cfd70e598/Chapter%207%205%20da8ad78c972c41c48c955b5fc4084775.md)

---

[Chapter 8.4](Probability%20and%20Statistics%2017fce9bf27174c53be10f62cfd70e598/Chapter%208%204%201c65a58613a24d0baac6f17ecfc6f44b.md)
