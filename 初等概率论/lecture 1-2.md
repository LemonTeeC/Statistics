# lecture 1-2

In this chapter, we first introduce some tricks to construct some sequences of sets with good properties.

For any event sequence {An}, we can construct:

1. {Bn} is monotonic decreasing sequence

$$
{B_n = \bigcup^{\infty}_{k=n}A_k}
$$

1. {Bn} is monotonic increasing sequence

$$
B_n = \bigcap^{\infty}_{k=n}A_k
$$

1. Bn is mutually exclusive events

$$
B_1=A_1, \ B_n = A_n-A_{n-1}-...-A_1
$$

1. From union to intersection

$$
A\cup B = 1-(A \cup B)^c = 1- A^c\cap B^c
$$

1. Exchange of limit and probability mapping
    
    well, we know that if the sequence of events is monotonic, then we can exchange the sign of limit and probability mapping. We can actually extend it to any sequence of events.
    
    $$
    \forall \  \{A_n\}, \ \lim_{n\to \infty}P(A_n) = P(\lim_{n \to \infty}A_n)
    $$
    

LHS is the limit of sequence, RHS is limit of event.

We can define limit superior and limit inferior for set.

$$
\lim_{n\to \infty}\sup A_n = \bigcap^{\infty} _{n=1}\bigcup^{\infty}_{k=n} A_k=\{\omega| \omega 属于无穷多个A_i\}
$$

$$
\lim_{n\to \infty}\inf A_n = \bigcup^{\infty} _{n=1}\bigcap^{\infty}_{k=n} A_k=\{\omega|\omega至多不属于有限个A_i\}
$$

上极限讲的是只要$\omega$属于无穷多个A即可. 但下极限要求$\omega$属于无穷多个A，又要求$\omega$最多在有限个A里面不存在. 可以看到下极限有着更强的条件，也说明凡是在下极限中存在的元素必然在上极限存在，下极限是上极限的子集

---

### Tutorial class:

1**.(Polya坛子问题)一个坛子装有b个黑球，r个红球，任意取出一个，然后放回并再放入c个与取出的颜色相同的球。**

1.一共抽取n个球，求抽取到n1个黑球，n2个红球的概率，其中n1+n2=n

首先考虑头n1次全是黑球，后面n2次全是红球的概率，我们有

$$
Prob=\big[\frac{b}{b+r}.\frac{b+c}{b+r+c}...\frac{b+(n_1-1)c}{b+r+(n_1-1)c}\big].\big[\frac{r}{b+r+n_1c}...\frac{r+(n_2-1)c}{b+r+(n-1)c}\big]
$$

再考虑n1次黑球可以在n次抽取中任意出现，于是有

$$
required\ prob. = \begin{pmatrix}n\\n_1\end{pmatrix}

\big[\frac{b}{b+r}.\frac{b+c}{b+r+c}...\frac{b+(n_1-1)c}{b+r+(n_1-1)c}\big].\big[\frac{r}{b+r+n_1c}...\frac{r+(n_2-1)c}{b+r+(n-1)c}\big]
$$

1. 第m次与第n次都取出黑球的概率都是 b(b+c)/(b+r)(b+r+c)

we do it by induction.

first consider m=1, let Ai be the event that a black ball is drawn in the i th drawing.

$$
P(A_1An)=P(A_1)P(A_n|A_1)=P(A_1)P_{b+c,b+r+c}(A_{n-1})=\frac{b(b+c)}{(b+r)(b+r+c)}

$$

then when m = k,

$$
\begin{split}
P(A_kA_n)
&=
P(A_{1})P(A_kA_n|A_{1})+P(A_{1}^c)P(A_kA_n|A_{1}^c) \\
&=
P(A_{1})P_{b+c,b+r+c}(A_{k-1}A_{n-1})+P(A_1^c)P(A_{k-1}A_{n-1})\\
&=\frac{b}{b+r}.\frac{(b+2c)(b+c)}{(b+r+c)(b+r+2c)}+\frac{r}{b+r}.\frac{b(b+c)}{(b+r)(b+r+c)}\\
&=
\frac{b(b+c)}{(b+r)(b+r+c)}

\end{split}
$$

**2.循环排列**

先思考循环全排列，一个有n个不同的人组合而成的圆圈，每个人看作一个连接点，我们一共有n个连接点. 将这n个连接点分别打断，我们有n种排列. 所以我们知道排列数

$$
nx=n! \iff x=(n-1)!
$$

现在考虑一个从n个不同的人抽取k个人可以得到的循环排列数. 类似的， 我们可以得到

$$
 x=\frac{P_k^n}{k}
$$