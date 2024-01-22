# lecture 11-12

First, note that $Corr(X,Y)=Corr(X-E(X),Y-E(Y))$

---

**Probability generating function (PGF)**

Let X be positive discrete r.v. 

$$
g(s)=E(s^X)=\sum^{\infty}_{j=0}s^j\Bbb P (X=j),s\in[-1,1]
$$

A nice property is that

If $\{X_j\}$ i.i.d. and take positive value, and PMF of $X_j$ is $\psi(s)$. And $N$ is a positive discrete r.v. and PMF is $G(s)$. Then $W=X_1+X_2+...+X_N$ has PMF $H(s)=G[\psi(s)]$

OR, for fewer notations, let $\psi(s)=g_X(s)$, $G(s)=g_N(s)$, then $H(s)=g_W(s)=g_N[g_X(s)]$. we have $g_W(s)= g_N(s):s \mapsto g_X(s)$

**Moment generating function (MGF)**

$$
\begin{split}
M_X(t)&=E(e^{tX})\\
&=E(\sum_{n=0}^{\infty}\frac{(tX)^n}{n!})\\
&=\sum_{n=0}^{\infty}E(\frac{(tX)^n}{n!})\\
&=\sum_{n=0}^{\infty}\frac{t^n}{n!}E(X^n)\\
&=\frac{t^0E(X^0)}{0!}+\frac{t^1E(X^1)}{1!}+\frac{t^2E(X^2)}{2!}+...
\end{split}
$$

We have 2 ways to find $E(X^n)$:

1. $E(X^n)=M^{(n)}(0)$
2. Find the coefficient of $t^n$ by Taylor expansion if we know $M_X(t)$

Example: $X \sim N(0,1),find \ E(X^n)$ given $M_X(t)=e^{t^2/2}$

Method 1 is very complicated in this case. We use method 2.

By Taylor expansion, we have 

$$
\begin{split}
M_X(t)&= \sum^{\infty}_{n=0}\frac{(\frac{t^2}{2})^n}{n!}\\
&=\sum^{\infty}_{n=0}\frac{1}{2^n \cdot n!}t^{2n}\\

\end{split}
$$

Thus, we have

$$
E(X^n)=\begin{cases}
0, n \ is \ odd \\ 
[n!/(n/2)!] \cdot 1/2^{n/2}, n \ is \ even
\end{cases}
$$

Note that the pre-image of  $M_X(t) \ and \ \phi_X(t)$ has range, usually $t\in D, \ where \ D \sub \R$

---

太他妈难了                                                           **REMARK:关于此章内容，Intro. to Prob. 讲解的极好**

对于大数定律，我们是在尝试寻找一个**随机变量**$\frac{1}{n}\sum_iX_i$和一个**常数**$E(X)$之间的关系，回想我们在学习函数列极限的时候，我们说数列和某个常数有关系是说这个数列收敛到这个常数上，所以类似的，我们也想讨论样本均值$\frac{1}{n}\sum_iX_i$如何收敛到$E(X)$上. 为了能讨论敛散性，首先要通过一些操作让$\frac{1}{n}\sum_iX_i$变成一个常数，最直观的方法就是让$\frac{1}{n}\sum_iX_i$去映射 $\omega$. 很多时候我们发现, 当n越来越大之后，$\frac{1}{n}\sum_iX_i(\omega)$,和$E(X)$之间的发生大偏差的概率就越来越小, 于是就有了**弱大数定律**

$$
Given \ \{X_i\} \ are \ i.i.d. \ and  \ Var(X_i)<\infty, \ then \ \forall \varepsilon >0, \ we \ have \\\lim_{n \to \infty}P(\big| \frac{1}{n}\sum^{\infty}_{i=1}X_i-E(X_1)\big|\geq\varepsilon)=0
$$

所以一个偶然的随机变量就和一个常数构建起了联系，偶然性与必然性的桥梁被建立

我们仔细思考这条定律告诉了我们什么，反过来说，当随机变量的序列的长度为无穷大时，它们的**平均值逼近定值的概率**将趋近于1. 但概率等于1，是说我们肯定能找到某一条序列，这条序列的样本均值肯定能逼近 $\mu$, 但是我们不能保证每一条序列都逼近 $\mu$，所以即使我们的n非常大，仍然会有一些偏离$\mu$  的序列. 换句话说，弱大数定律表明了一种存在性

所以我们现在的想法是能不能有一个更强的定律，使得我们可以筛选出所有能逼近 $\mu$的序列. 这也就得到了**强大数定律.** 直观的看，若$\{X_i\}$服从强大数定律必然可以推出它服从弱大数定律. 用语言解释强大数定律就是说，当随机变量序列的长度为无穷大时，它们的**平均值必然趋于定值** $\mu$. 我们称这种序列是几乎处处收敛的，或者以概率1收敛的

(因为我们已经筛选出了在n非常大的时候平均值必然趋于定值 $\mu$的序列，那些不收敛的序列是非常少的，选中这些序列的概率就为0，所以那些个别的n是不影响概率的，所以也称为几乎处处收敛）

$$
Given \ \{X_i\} \ are \ i.i.d. \ and  \ E|X_i|<\infty, \ then \ \forall \varepsilon >0, \ we \ have \\
\\P(\lim_{n \to \infty}\frac{1}{n}\sum^{\infty}_{k=1}X_k=EX_1)=1
$$

更一般的，我们定义

**依概率收敛:                                                                        发生大偏差的概率=0, 数列几乎不会再有大偏差**

$$
\lim_{n\to \infty}P(\{\omega\in\Omega:\big |X_n(\omega)-X(\omega)\big|\geq\varepsilon\})=0 \\denote \ as \  Y_n \xrightarrow{P}Y
$$

**几乎处处收敛:                         即使存在一些数列是有大偏差的,但选中其的概率为0, 也就是几乎选不中**

$$
P(\{\omega \in \Omega:\lim_{n \to \infty}X_n(\omega)=X(\omega)\})=1 \\ denote \ as \ Y_n \xrightarrow{a.s.}Y
$$

**证明思路：**

对于依概率收敛，其实是把 $P( \cdot)$ 看成一个数列，再求数列极限. 所以我们首先化简概率

对于以几乎处处收敛，我们先找到数列极限再去找概率

---