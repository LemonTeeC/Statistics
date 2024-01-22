# lecture 1-2

lecture 1:

simple ideas, but be careful about empirical distribution function

---

lecture 2:

sample distribution:  通过抽样得到样本，样本的joint pdf/cdf 就刻画了joint distribution

sampling distribution: 通过抽样得到样本，再通过一个映射得到 $T(X_1,X_2,...,X_n)$，这个统计量也因为样本的随机性从而具有随机性，这个统计量背后的概率分布就称为sampling distribution

先介绍一些常用的公式，有

$$
\begin{equation}
\sum(x_i-\bar{x})^2=\sum x_i^2-\frac{(\sum x_i)^2}{n}=\sum x_i^2-n\bar{x}^2
\end{equation}
$$

$$
\begin{equation}
\begin{split}
\sum(x_i-\mu)^2&=\sum(x_i-\bar{x}+\bar{x}-\mu)^2\\
&=\sum(x_i-\bar{x})^2-2\sum(x_i-\bar{x})(\bar{x}-\mu)+n(\bar{x}-\mu)^2 \\
&=\sum(x_i -\bar x)^2+n(\bar x- \mu)^2
\end{split}
\end{equation}
$$

---

指数族其实比较容易记忆

$$
f(x;\vec{\theta})=h(x)C(\vec{\theta})exp \{ \sum_{i=1}^nQ_i(\vec{\theta})T_i(x)\}
$$

可以看到指数里面是两个分别关于$\vec{\theta}$和x的函数，指数外面也是这样. 但需要注意的是, 指数族要求$\vec{\theta}$和x有共同的支撑集，即说明x的取值不能depend on $\vec{\theta}$. 

---

充分统计量这个概念的主要想法还是说我们有一个样本$\vec{x}$, 这个样本携带某些我们感兴趣的信息$\theta$, 但是样本$\vec{X}$是n维的，处理这个样本是麻烦的，所以我们思考能不能通过映射得到一个统计量$T(\vec{x})$, 这个统计量是降维的，但是又捕获了所有关于$\theta$的信息, 我们把这样的统计量叫做充分统计量

更一般的数学表达是说$\vec{X}$是样本，而$F(\vec{x};\theta)$是总体分布函数，若统计量$T(\vec{x})$是充分的，这在给定$T(\vec{x})=t$之后，$\vec{X}$的分布和$\theta$无关

**REMARK: 这个想法是自然的，因为分布反映了概率，若我们认为$T(\vec{x})$包括了所有关于$\theta$的信息，那么给定T=t之后，$P(\vec{X}=\vec{x})\ or \ F(\vec{x})$就不应该依赖于$\theta$**

但显然，直接去找充分统计量是不明智的，所以我们有因子分解定理(Factorization theorem). 这个定理是说如果我们可以将概率密度函数拆成两部分，一部分依赖于$T=t$和$\theta$，一部分只依赖于$\vec{x}$，则$T$是充分统计量. 数学上，我们有

$$
f(\vec{x};\theta)=g(T(\vec{x}),\theta)h(\vec{x})
$$

更有趣的是，充分统计量有一种继承性. 也就是说，若T是充分统计量，存在某个函数$h(\cdot)$,使得T可以表示为$t=h(s)$,则统计量$S$也是充分统计量. 

**REMARK: 对于这个定理，intuitively，我们认为mapping是一种减少信息的操作，若统计量经过一个mapping后仍然是充分统计量，包含了关于$\theta$足够多的信息，自然$S$本身也应该是充分统计量.**

对等的如果我们有$g(\cdot)$是一个one-to-one function，则统计量$g(T)$也是充分统计量. 这也非常好理解，1-to-1 mapping将所有信息都对等的映射了，那信息没有丢失，所以新统计量也是充分统计量.

---

delta method

假设$\sqrt{n}(X_n-a)\xrightarrow{d}N(0,V)$, 且$g:\R\to\R$是连续可导函数，则

$\sqrt{n}(g(X_n)-g(a))\xrightarrow{d}N(0,(g'(a))^2 \cdot V)$

$proof$:

by mean value theorem and fix an $\omega$, we have

$$
g(X_n(\omega))-g(a)=g'(y)\cdot (X_n(\omega)-a)
$$

as $X_n$ is a sequence, we thus can represent y as the value of a sequence $Y_n$, then

$$
g(X_n(\omega))-g(a)=g'(Y_n(\omega))\cdot (X_n(\omega)-a)
$$

let $\omega$ be free,

$$
\begin{split}
g(X_n)-g(a)&=g'(Y_n)\cdot (X_n(\omega)-a) \\
\sqrt{n} \cdot g(X_n)-g(a)&=\sqrt{n} \cdot g'(Y_n)\cdot (X_n(\omega)-a) \\

\end{split}
$$

note that when $n \to \infty$, $E(X_n-a)=0$, then $X_n \xrightarrow{p}a$. By, inequality $|Y_n-a|\leq|X_n-a|$, 

we should have $Y_n \xrightarrow{P}a$. By continuous mapping theorem, $g(Y_n) \xrightarrow{P}g(a)$.

Finally, by Slusky’s theorem, we have

$$
\sqrt{n}(g(X_n)-g(a))\xrightarrow{d}N(0,(g'(a))^2 \cdot V)
$$

---

hw:

(7) 对于一些多参数分布，充分统计量是对于整个参数空间还是具体到一个参数. 第二个问题，因子分解定理出现两个统计量, 必须是联合统计量才是充分统计量，还是单独一个就可以