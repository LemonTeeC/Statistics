# Chapter 5.3

### 12. Show that  $Cov(\bar x, s^2) = \frac{v_3}{n}, \ where \ v_3 = E[x-E(x)]^3, \ E(\bar x) = \mu$

Intuition: We first note that the highest term of R.H.S. is 3, then we try to do some operations so that the highest term of the L.H.S. is also 3. 

First, we have

$$
Cov(\bar x, s^2) = E(\bar x \sdot s^2)-E(\bar x)E(s^2)
$$

We note that both terms have 3 as the highest term, so we just try to combine 2 terms together. Then we have

$$
E(\bar x \sdot s^2)-E(\bar x)E(s^2) = E(\bar x \sdot s^2)-\mu E(s^2)= E[(\bar x-\mu)s^2]
$$

Then, we try to simplify $(\bar x-\mu)s^2$  in order to get more information. The trick is that we want all x transform into $x - \mu$, because after doing that, we have all the term about x having the format as x-E(x) just like v3. so we get

$$
\begin{split}
(\bar x-\mu)s^2 &= (\bar x-\mu)\frac{1}{n-1}(\sum^n_{i=1}x^2_i-n \bar x^2)\\
&= (\bar x-\mu)\frac{1}{n-1}[\sum^n_{i=1}(x_i-\mu)^2-n(\bar x -\mu)^2]
\end{split}
$$

Then, we can find the expectation of them separately. 

First,

$$
\begin{split}
E(\bar x-\mu)[\sum^n_{i=1}(x_i-\mu)^2]
&= \sum^n_{i=1}E[(\bar x-\mu)(x_i-\mu)^2] \\

\end{split}
$$

Then, we have 

$$
E[(\bar x-\mu)(x_i-\mu)^2] =
\frac{1}{n}E(x_i-\mu)^3-\sum_{i \not = j}E[(x_j-\mu)(x_i-\mu)^2]
$$

note that $x_i, \ x_j$  are independent, then we have $E(x_j-\mu)E(x_i-\mu)^2 = 0$. Thus, we have

$$
\begin{equation}E[(\bar x-\mu)(x_i-\mu)^2] =
\frac{1}{n}E(x_i-\mu)^3 = \frac{v_3}{n}
\end{equation}
$$

Second,

$$
\begin{equation}E(\bar x- \mu)^3 = \frac{1}{n^3}\sum^n_{i=1}E(x_i-\mu)^3=\frac{v_3}{n^2}
\end{equation}
$$

Combine them together, we get the answer

### 22. Find the distribution  of  $x_{(1)}$ and  $x_{(n)}$, given P(X=k)

For this type of question, the intuition is similar. We just find $P(X \leq k)$ and $P(X \geq k)$.

Since we have $P(x_{(1)}=k) = P(x_{(1)}\geq k) - P(x_{(1)}\geq k+1)$ 

and $P(x_{(n)}=k) = P(x_{(n)} \leq k)-P(x_{(n)} \leq k-1)$

but actually, we can use formula to solve this question, recall that

$$
p_{(k)}(x)=\frac{n!}{(k-1)!(n-k)!}[F(x)]^{k-1}[p(x)][1-F(x)]^{n-k}
$$

### 28. If F(x) is continuous and $\mu_i = F(x_{(i)})$, prove $\mu_1 \leq \mu_2 \leq ... \leq \mu_n$,  $\mu_i$ 是U(0,1)的次序统计量.

(i) First, we prove that if F(x) is strictly monotonic increasing, then $F(X) \sim U(0,1)$.

Proof: Let $Y=F_X(X)$, cases for $y< 0$, $y\geq 1$  are obvious. 

When $0\leq y<1$, $F_Y(y) = P(Y\leq y)=P(F_X(X)<y)=P(X\leq F_X^{-1}(y))=F_X(F_X^{-1}(y))=y$

Thus, we have $F_Y(y) = \begin{cases}
0, \ y<0 \\ y, \ 0<y\leq 1\\
1, \ y\geq 1
\end{cases} \Rightarrow Y\sim U(0,1)$

Let’s go back to this question, as $x_{(i)}$ are ordered, so $F(x_{(i)})$ is monotonic increasing.             $\boxtimes$

(ii)

(iii) Only prove a integral here                                                         **REMARK：$I$  is Beta function, I forgot……**

$$
I=\int^1_0t^i(1-t)^{n-i-1}dt,where\  \ i,n\in\R \ and \ i< n\\ 

\begin{split}
 I
&=\int^1_0(1-t)^{n-i-1}d(\frac{t^{i+1}}{i+1}) \\
&=\frac{n-i-1}{i+1}\int^1_0t^{i+1}(1-t)^{n-i-2}dt
\end{split}

$$

we note that $\max\{i\}=n-1$, and by induction, the integral will become 

$$
\begin{split}
I
&=\frac{(n-i-1)!}{(i+1)(i+2)...(n-1)}\int^1_0t^{n-1}dt \\
&= \frac{i!(n-i-1)!}{(n-1)!}\sdot\frac{1}{n} \\
&=\frac{i!(n-i-1)!}{n!}  
\end{split}  
$$

### 31.

通过观察1个和2个次序统计量的密度函数, 可以推测n个次序统计量的密度函数. 我们观察到每个次序统计量的之间的距离都是1, 所以常数的分母就是n个 1! 相乘, 分子还是n! . 同理, 对于F(x) 和 1-F(x), 他们的次数都应该是0, 因为没有统计量在$x_{(1)},x_{(n)}$两边. 所以

$$
p(x_1,x_2,...,x_n)=n!\prod^n_{i=1}p(x_i)
$$

well, this observation may seem not natural. Let me introduce a more natural proof. Please see 统计辅修-lecture 7-8