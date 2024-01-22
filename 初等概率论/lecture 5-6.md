# lecture 5-6

### What’s the connection between Geometric Distribution and Exponential Distribution?

**Motivation**: We know that Geometric Distribution and Exponential Distribution are only memoryless r.v. in discrete and continuous r.v. respectively. So, it’s natural to think that there exists a connection between them.

考虑一个n次的伯努利实验，当第一次实验成功（A）的次数服从几何分布. 每次A发生的概率都是p，这说明实验失败的概率都是以1-p恒定进行的，这也代表实验的失败率是恒定的，我由此可以假定失败实验的时间间隔T服从指数分布.

令$X\sim Ge(p)$, $T\sim Exp(\lambda)$, 有$X=n,T=n\delta$, $\delta$为时间间隔

于是有,

$$
\begin{split}
\Bbb P(X\leq n)&=\Bbb P(T\leq n\delta) \\
1-(1-p)^n&=1-e^{-\lambda n \delta}\\
\delta &=\frac{ln(1-p)}{\lambda}

\end{split}
$$

所以，当实验的时间间隔为$\delta$时，我们可以得到这样的CDF图像,

![Screenshot 2023-10-11 at 21.35.45.png](lecture%205-6%20f9a9dd7338e64d34ba719a83cffd3fa1/Screenshot_2023-10-11_at_21.35.45.png)

可以看到，当T是k$\delta$的时候，事件发生，于是两个CDF曲线相交. 两个分布的CDF有相当的关联. 

---