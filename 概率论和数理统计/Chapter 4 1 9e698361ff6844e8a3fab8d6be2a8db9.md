# Chapter 4.1

### 1. If $X_n \xrightarrow{P} X$  and  $X_n \xrightarrow{P}Y$, prove P(X=Y) = 1

We need to know an inequality and an theorem in order to solve the question. The first one is that 

$$
\{|A+B|\geq \epsilon \}\subset \{|A|\geq \frac{\epsilon }{2}\}\cup\{|B|\geq\frac{\epsilon}{2}\}
$$

we can prove it like that, since we have $\varepsilon \leq |A+B| \leq |A| +|B|$, the numbers between $\varepsilon \ and \ |A+B|$   are fewer than the number between $\varepsilon  \ and \ |A|+|B|$, thus we have more choices of A and B for the latter one, hence the cardinality of the set is greater.

A more general case is that

$$
\{|A+B+C+...|\geq \epsilon \}\subset \{|A| \geq a \}\cup\{|B| \geq b\}\cup\{|C|\geq c\} \cup ...\\where \ a+b+c+...= \epsilon
$$

The theorem is (we used this theorem before when we proved Chebyshev Ineuqality)

$$
\{|X-Y|>0\}=\{X\neq Y\}=\bigcup_{n=1}^{\infty}\{|X-Y|\geq\frac{1}{n}\}
$$

### 5. Prove that  $X_n\xrightarrow{P}X$  if and only if  $E(\frac{|X_n-X|}{1+|X_n-X|})\rightarrow0$

We first introduce an important tool in statistics, the indicator function.

$$
I_A(\omega)  /  I_A=\begin{cases}0\quad \omega \notin A\\ 1\quad \omega \in A\end{cases} \quad OR \quad I_{\{X \in A\}}=\begin{cases}0 \quad X \notin A \\ 1 \quad X \in A\end{cases}
$$

We note that the indicator function is a function of X, then we denote it as $Y = I_{\{X \in A\}}$. We can find the expectation of Y.

$$
E(Y)=E(I_{\{X \in A\}})=P(X \in A)
$$

which means the expectation of indicator function is the probability of event A happened.

Then we can prove from left to right.

If we want to prove from right to left, we need to recall a corollary from 2.3, which is

$$
P(X\geq \varepsilon)\leq \frac{E(g(X))}{g(\varepsilon)},\ g(x)\ is \ a\ monotonic \ non-decreasing \ function
$$

### 8. If $X_n\xrightarrow{L}X$ , and $a_n,\ b_n \ converges\ to\ a \ and \ b \ respectively$. prove that $a_nX_n+b_n\xrightarrow{L}aX +b$

If we want to prove week convergence of a sequence of random variables, we only need to show that $\lim\limits_{n\to\infty}F_n(x)=F(x),\ \forall x\in D_F$

Note that $F_{aX}(x)=F_X(\frac{x}{a})$, which is possible since we only do a linear transformation to X.

Then, $\lim\limits_{n\to \infty}F_{aX}(x)=\lim\limits_{n\to \infty}F_X(\frac{x}{a})=F_X(\frac{x}{a})=F_{aX}(x),\forall x \in D_F$, hence we prove the first part, i.e. $aX_n \xrightarrow{L}aX$

For the second part, it is tricky, we need to use the corollary from the question below

### 15.  If $X_i \sim U(0,1), \ let \ Y_n = (\prod\limits_{i=1}^nX_i)^{\frac{1}{n}}$, prove $Y_n \xrightarrow{P}c$, and find c.

Chebyshev inequality is frequently used in this type of question. It states that

$$
P(|X-E(X)|\geq \varepsilon)\leq \frac{Var(X)}{\varepsilon^2}
$$

Then, we take natural log on Yn

---

I don’t think this chapter exercise is good