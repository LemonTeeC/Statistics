# lecture 7-8

$$
prove \ E(X^n)=M^{(n)}(0)
$$

Proof: 

$$
\begin{split}
M(t)&=E(e^{tx}) \\
&=\int^{\infty}_{-\infty}(1+tx+\frac{(tx)^2}{2!}+...+\frac{(tx)^n}{n!}+...)f(x)dx\\
&=1+tm_1+\frac{t^2}{2!}m_2+...+\frac{t^n}{n!}m_n+...
\end{split}
$$

where $m_i=E(X^i)$ is the ith moment. Then, differentiate with respect to t, we have

$$
\begin{split}
M^{(n)}(t)&= 0+0+0+...+(\frac{t^n}{n!}m_n)^{(n)}+...\\
&=m_n+tm_{n+1}+...
\end{split}
$$

sub t=0,

$$
\begin{split}
M^{(n)}(0)&= m_n\\
&= E(X^n)   \\

\end{split}

$$

**REMARK: You may wonder that if we can do differentiation term by term to a infinite series of function. Recall from advanced calculus or analysis, if $\sum_{n=1}^{\infty}u_n(x)$ is uniformly convergent, then we can do differentiation term by term. i.e.  $\boldsymbol[\sum_{n=1}^{\infty}u_n(x)\boldsymbol]'=\sum_{n=1}^{\infty}u_n'(x)$.**

---

I always feel complexed about ordered statistics, the rigorous definition is that:

$$
\begin{split}Let  \ X_1,X_2,...,X_n \ be \ random \ variable \ in \ (\Omega,\cal{F}, \Bbb{P}), \ \forall \omega\in\Omega, \ order \ them, \ we \ have  \\

\end{split}

 
$$

$$
X_{(1)}(\omega)\leq X_{(2)} (\omega) \leq ...\leq X_{(n)}(\omega)
$$

The joint density function of the ordered statistics is:

$$
f(x_1,x_2,...,x_n)=n!\prod^n_{i=1}f(x_i)
$$

**Intuition: As $X_{(1)},...,X_{(n)}$  are i.i.d. and the probability of $X_{(i)}=X_{(j)}=0$, so all of them are different. Then, we note that ordered statistics actually doesn’t care about permutation. For example $X_{(1)}$ can actually be any $X_i$ as long as it is the smallest. Thus, this n ordered statistics can arrange in any sequence, the no. of sequence is n!**

---

### A deduction of Beta distribution from Binomial distribution.

If $X \sim b(n,p)$, then $P(X=k) =\binom{n}{k}p^k(1-p)^{n-k}$, but in reality, usually we cannot ensure p is a constant, we deduct it by frequency. Consider p is variable, directly related to probability we have 

$$
\begin{equation}f(p)=k
\end{equation}
$$

---