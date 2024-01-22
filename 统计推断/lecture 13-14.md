# lecture 13-14

**UMPT**

> Consider all level $\alpha$ tests of $H_0: \theta \in \varTheta_0 \leftrightarrow \theta \in \varTheta_1$. Let $\Phi_\alpha$  be the family of these tests. If $\forall \varphi_1\in \Phi_\alpha$, we have $\beta_\varphi(\theta) \geq \beta_{\varphi_1}(\theta),\forall \theta \in \varTheta_1$, then we call $\varphi(\cdot)$  UMPT. The word ‘uniform’ indicates that $\varphi$ is the most powerful test among all tests in the family $\forall \theta \in \varTheta_1$.
> 

We first introduce Neyman-Pearson Lemma here.

> For test $H_0: \theta = \theta_0 \leftrightarrow H_1:\theta = \theta_1$, then there always exists a test function and a positive constant C and $r \in[0,1]$, such that
> 

 $\varphi(\bold{x})=\begin{cases}
1, \ f(\bold{x},\theta_1)/f(\bold{x},\theta_0)>c \\
r, \ f(\bold{x}, \theta_0)/f(\bold{x}, \theta_1)=c \\
0, \ f(\bold{x}, \theta_0)/f(\bold{x}, \theta_1)<c
\end{cases} \ and \  E_{\theta_0}[\varphi(x)]=\alpha$ (exisistence).  If $\varphi(x)$ satisfies these 2 conditions then it is the UMPT.

REMARK: The likelihood ratio is different here, we call it the generalised likelihood ratio.

我们给出3个推论, 证明都不难

> $H_0: \theta \in \varTheta_0 \leftrightarrow \theta \in \varTheta_1$, let $\varphi(\bold{x})$ be the UMPT with level of significance $\alpha$, then its power . $E_{\theta}\varphi(\bold{x}) \geq \alpha, \forall \theta \in \varTheta_1$
> 

$Proof:$ Construct a constant function, $\varphi^*(\cdot) = \alpha$, which is indeed a test with level of significance $\alpha$. As $\varphi(\bold{x})$ is the UMPT, we must have $E_{\theta}\varphi(\bold{x}) \geq E[\varphi^*(\bold{x})] = \alpha , \forall \theta \in \varTheta_1$

> If $\lambda({\bold{x}})=h(T(\bold{x}))$, and $h(\cdot )$ is strictly increasing, then $\varphi(\bold{x})$ can be written as
> 

$$
\varphi(\bold{x})=\begin{cases}
1, \ \bold{x}\in \{\bold{x}:T(X)>k\}\\
\gamma,\ \bold{x} \in  \{\bold{x}:T(X)=k\}\\
0, \ \bold{x} \in \{\bold{x}:T(X) <k\}
\end{cases} \ and \  E_{\theta_0}[\varphi(x)]=\alpha
$$

$Proof.$ We should think carefully before starting the proof. The form of rejection region is constructed by a estimator of the parameter we want to test. So, when we construct the region, we actually think that $H_0$ is false and $H_1$  is true. Now, let’s start the proof.  $\{\lambda({\bold{x}}) >c\}=\{h(T({\bold{x}})) >(c)\}=\{T({\bold{x}}) >h^{-1}(c)\},$ where $h^{-1}(c)=k$.       $\square$

REMARK: The subtle thing here is that we should prove $h(\cdot)$ is strictly increasing under $H_1$.

在证明指数分布族的UMPT里，从$H_0: \theta = \theta_0 \leftrightarrow H_1:\theta > \theta_1$到 $H_0: \theta \leq \theta_0 \leftrightarrow H_1:\theta > \theta_1$的推广需要注意. 书上的证明只提到证明 $\pi_\varphi(\theta)$ 在 $H_0$ 成立的情况下是严格增函数, 但是没有直接说明$\beta_\varphi(\theta) \geq \beta_{\varphi_1}(\theta),\forall \theta \in \varTheta_1$. 我们考虑另外一个检验函数 $\varphi_1(x)$, 在 $H_0$ 成立的情况下，始终有$E[\varphi_1(x)] \leq \alpha$ . 所以有 $E_{\theta_0}[\varphi_1(x)] \leq \alpha$ , 但我们知道 $\varphi(x)$是 $\theta =\theta _0$情况下的UMPT, 所以这才说明了 $\beta_\varphi(\theta) \geq \beta_{\varphi_1}(\theta),\forall \theta \in \varTheta_1$. 由此可见 $\varphi(x)$才是UMPT.