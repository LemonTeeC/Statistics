# lecutre 9-10

$$
 Prove  \ if \ E|X|=0, \ then \ P(X=0)=1 \iff X=0 \ a.s.
$$

Intuition: we want to prove P(X=0)=1 , it is equivalent to P(|X|>0) $= EI_{\{|X|>0\}}$=0. Also, we know if Y<X, then E(Y)<E(X). From the given condition, E|X|=0, then we only prove $I_{\{|X|>0\}}<|X|$

let’s draw the graph, we know that $E(a|X|)=aE|X|=0$, so we can choose some a.

![Screenshot 2023-10-25 at 19.31.24.png](lecutre%209-10%20e3ba648e809449829e9c4dce93372f9d/Screenshot_2023-10-25_at_19.31.24.png)

but there are always some x s.t. a|X| <1 no matter what $a$ we choose. Thus, Then, $I_{\{|X|>0\}}$ is not always under control. we change the indicator function to $I_{\{|X|>\frac{1}{a}\}}$. Thus, we always have $a|x| >I_{\{|X|>\frac{1}{a}\}}$. 

then, change a to n( just a change of dummy variable),if we prove $E(I_{\{|X|\geq\frac{1}{n}\}})=0$, then take $n \to \infty$, we prove what we initially need.

$$
\begin{split}
E(I_{\{|X|>\frac{1}{n}\}})&=P(|X|>\frac{1}{n})\\
&=P(n|X|>1)\\
&=E(I_{\{n|X|>1\}})\\
&\leq E(n|X| \cdot I_{\{n|X|>1\}})\\
&\leq E(n|X|)=0
\end{split}
$$

Very nice proof, we use some tricks here:                                                           **REMARK: $g(\cdot)$  is monotonic increasing** 

$$
\boxed{E(I_{\{f(X)>1\}})\leq E(f(X)I_{\{f(X)>1\}}) \leq E(f(X))} \\
\boxed{more \ generally, we \ have \ P(X>\varepsilon)\leq \frac{E(g(X))}{g(\varepsilon)}}
$$

**事实上，处理概率相关的不等式，常用的技术只有两种，一是放大被积函数，二是放大被积区域**

then we prove what we need,

$$
P(|X|>0)=P(\bigcup^{\infty}_{n=1}\lbrace |X|>\frac{1}{n}\rbrace)=\lim_{n\to \infty}P(|X|>\frac{1}{n})=0
$$

---

we have some important inequalities 

1. **Markov Inequality**

For r.v. X and $\epsilon$ >0, we have

$$
P(|X|\geq \varepsilon )\leq\frac{E|X|^{\alpha}}{\varepsilon^{\alpha}}
$$

Proof:

Again, if we want to prove inequality related to prob. and expectation, we try to use indicator function

$$
\begin{split}
P(|X|\geq \varepsilon )&=E(I_{\{|X|\geq\varepsilon\}})\\
&=E(I_{\{|X|^{\alpha}\geq\varepsilon^{\alpha}\}})\\
&\leq E( \frac{|X|^{\alpha}}{\varepsilon^{\alpha}} \cdot I_{\{|X|^{\alpha}\geq\varepsilon^{\alpha}\}})\\
&\leq E(\frac{|X|^{\alpha}}{\varepsilon^{\alpha}})=\frac{E|X|^{\alpha}}{\varepsilon^{\alpha}}
\end{split}
$$

1. **Chebyshev Inequality**

$$
P(|X-E(X)|\geq \varepsilon) \leq \frac{Var(X)}{\varepsilon^2}
$$

We prove it directly from Markov Ineuqality.

1. **Jensen Inequality**

If $\psi$  is a convex function, then

$$
\psi(E(X)) \leq E(\psi(X))
$$

1.  **Schmidt Inequality**

If $EX^2< \infty \ and  \ EY^2 < \infty$, then

$$
|E(XY)| \leq \sqrt{E(X^2)E(Y^2)}
$$

---

> we have 3 ways to interpret E(X) and Var(X), the most impressive thing is that we can consider random vectors as legal vectors to generate inner dot-product space, which give us more insight about random variables and a geometric view about E(·) and Var(·)
> 

---

We can prove that $E[(X-E(X|Y)) \cdot h(Y)]=0$, or if we define $\braket{X,Y}=E(XY)$, then we can consider E(X|Y) is the projection of X to  a plane $\sigma(Y)$, thus $E[(X-E(X|Y)]$ is the orthogonal vector to the plane $\sigma(Y)$.

With this geometric view, we now consider inequality

$$
\begin{equation}E[X-E(X|Y)]^2\leq E[X-g(Y)]^2
\end{equation}
$$

the left hand side is the norm of the orthogonal vector, which is also the square of the shortest distance from $X$ to $\sigma(Y)$. Thus, any vector other than $E(X|Y)$  should give greater norm. LHS = RHS if and only if $g(Y) =E(X|Y)$.

Of course, we can prove this inequality (1) rigorously.

Then, we try to interpret mathematical meaning of LHS. We know that E(X|Y) is a function of Y, denote it as m(Y). Then we try to solve an optimisation problem.

$$
\begin{equation}\argmin_{m(Y)} \{E[X-m(Y)]^2\}
\end{equation}
$$

The story of this optimisation is that we try to find a m(Y) which is “closest” to X. As m(Y) is “closest” to X,  $[X-m(Y)]^2$ is the smallest, then $E [X-m(Y)]^2$ is the smallest. 

From the inequality (1), we know that the m(Y) we searched for is E(X|Y). Thus, in optimisation view, E(X|Y) gives the **optimal forecast** of X.

---

After understanding the meaning of $E(X|Y)$, we now can understand the law of total variance in 2 ways.

**The first way:**

We now consider X as a group of so many datas. We want to find Var(X) of it. But a big group of datas is difficult to tackle with, then we try to divide X to some small groups by a restriction Y. Intuitively, Var(X)  should equal to variance inside each group + variance among each group. 

Consider how variance inside each group contributes to total variance, although each small group may have **equal variance in their on scale**, but with different mean, they actually contribute different variance to the total one. So, we first find the mean of each group, then find the variance of mean to this group of data, thus we **take the scale into account.**

Then, we also know even if the mean of each small group may equal, but variance in each small group may different, so we take this into account, and take the mean of variance of each small group.

$$
Var(X)=\overbrace{E(Var(X|Y))}^{组间方差}+\overbrace{Var(E(X|Y))}^{组内方差}
$$

**The second way:**

We know that $E(X|Y)$
 is an optimal forecast to X, so we can think that 

$$
Var(X) = Var(E(X|Y))+\varepsilon
$$

where $\varepsilon$ is the error. Let’s consider the error. Intuitively, the error comes from the the difference between X and E(X|Y), so $\varepsilon$ should be related to them. How can we change the difference between X and E(X|Y) to have the same unit as Var(X)? Recall the definition of Var(X), it is expectation of square of something, so we do the same thing to the difference, we have $E[X-E(X|Y)]^2$. Note that,                 **Pay attention to the first =, we use extra conditioning of total expectation here**

$$
\begin{split}
E[X-E(X|Y)]^2&=E[E((X-E(X|Y))^2|Y)] \\
&=E(Var(X|Y))
\end{split}
$$

Thus,

$$
Var(X)=\overbrace{E(Var(X|Y))}^{误差}+\overbrace{Var(E(X|Y))}^{最优估计}
$$

---