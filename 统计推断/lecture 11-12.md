# lecture 11-12

### likelihood test

整个likelihood test 的motivation还是很自然的, 我们把整个参数空间分成两部分$\varTheta_0$和$\varTheta_1$, 我们想检验假设$H_0:\theta\in\varTheta_0 \leftrightarrow H_1: \theta \in \varTheta_1$ ， 也就是说我们想从样本观察值去检查是否有一个$\theta_0\in \varTheta_0$, 使得$X_i \sim f(x; \theta_0)$. 从likelihood 的角度看，由于必然有

$$
\sup_{\theta \in \varTheta_0} L(\theta;\bold{x})=L(\hat{\theta}_{MLE,0}) \leq \sup_{\theta \in \varTheta} L(\theta;\bold{x})=L(\hat{\theta}_{MLE}) 
$$

但如果相差过大，则说明$\theta$在$\varTheta_0$的似然性更小, 我们定义一个likelihood ratio

$$
\lambda(\bold{x}):=\frac{L(\hat{\theta}_{MLE,0})}{L(\hat{\theta}_{MLE})} \leq 1
$$

很自然，如果如果这个ratio 远小于1, 或者说小于某个$\lambda_0$, 那么我们就应该拒绝原假设. 当然我们可以取对数, 得到log likelihood, 有$\lambda<\lambda_0 \iff -2 \log \lambda > C=-2 \log \lambda_0$

我们可以写出non-randomized test, 

$$
\varphi(\bold{x}) =\begin{cases}
1, \ \lambda < \lambda_0 \\
0, \lambda \geq \lambda_0
\end{cases}
$$

在实际处理这种问题的时候, 我们会发现$\lambda(\bold{x})$的形式很复杂，我们找不到它的分布, 但很多时候我们可以通过一定的变换使得$\lambda(\bold{X})=g(T(\bold{X}))$的形式, 其中$T(\bold{X})$的分布是已知的. 自然, 如果$\lambda<\lambda_0$,而且$g(\cdot)$是可逆的话, 就可以找到一个等价形式$T(\bold{X})<or>C'$, 我们这时候再通过$T(\bold{X})$的拒绝域去控制$\alpha$. 

我们会有一个问题, 即$\alpha$是$H_0$成立的情况下才有的概率, 那likelihood ratio不是同时涉及到两个假设吗? think carefully, likelihood ratio的分母是定义在整个参数空间上的likelihood, 所以它不涉及$H_a$的问题, 或者说它任意情况下都必然成立, 所以我们可以直接用likelihood ratio去控制$\alpha$. 

存在一个比较好的性质, suppose the dimensionality(free parameters in the parameter space) of $\varTheta$ is k and the dimensionality of $\varTheta_0$ is s, is k-s = t >0, and the pdf satisfies certain regularity conditions, then for the test problem:

$$
H_0:\theta \in \varTheta \leftrightarrow H_1 : \theta \in \varTheta _1
$$

under $H_0$ and $n  \to \infty$, we have

$$
-2 \log \lambda (\bold{X}) \xrightarrow{d}\chi^2 _t
$$

$\lambda \Lambda$