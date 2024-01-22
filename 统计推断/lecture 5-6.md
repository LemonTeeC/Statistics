# lecture 5-6

lecture 5: 

invariance property of MLEs. If $\hat\theta^{MLE}$ is the MLE of $\theta$, then $g(\hat\theta^{MLE})$ is the MLE of $g(\theta)$

It is easy to prove this theorem if g is one-to-one. When it comes to non-surjective mapping, we avoid the problem by restricting the function g to act like 1-to-1, which is that we restrict the domain of g, all pre image of g should be those $\theta$ which can maximise $L(\theta)$.

Also, MLE is function of sufficient statistics.

---

lecture 6:

regularity conditions: some things should be careful

we say a distribution family satisfies the regularity condition, and for this family $\theta$ should be 1-D parameter. Also, like exponential family, x and $\theta$ should have common support, which means x should not depend on $\theta$. 

now, lets consider more about fisher information and score function.

Score function:

$$
S(\bold x;\theta)=l'_n(\theta;\bold x)
$$

fisher information:

$$
initial\ defintion:  I_n(\theta)=E\{[l'(\theta)]^2 \}
$$

under regularity condition, we can show that $E(S(\bold x;\theta))=0$, and $Var(S(\bold x;\theta))=I_n(\theta)$. After some more operations, we can show that 

$$
under  \ regularity:I_n(\theta)=-E[l''(\theta)]
$$

be careful, we do the expectation with respect to X. 

Under this regularity conditions, MLE can have asymptotic normality

$$
\sqrt{n}(\hat\theta_n-\theta) \xrightarrow{d}N\bigg(0,\frac{1}{I(\theta)}\bigg)
$$

---

接下来，我们对无偏估计做进一步的讨论，我们尝试去找最好的无偏估计，which is UMVUE.

首先给出一个充分必要条件, if W is UMVUE, and Var(W)<$\infty$, then W is uncorrelated with all unbiased estimators of 0. 不过，这个充要条件并没有告诉我们如何去构造一个UMVUE, 而且一个$\theta$可以有许多无偏估计，一个个去检验是不现实的. 所以我们给出一个推论, 去考虑充分统计量T(X).

> If T(X) is a sufficient statistics, and h(T(X)) is unbiased estimate of $\theta$ and $Var(h(T(X))<\infty$. If for all $\delta(T)  \ satisfying \ E(\delta(T))=0, \ \forall \theta \in \varTheta$, s.t. $\delta(T) \ and \ h(T)$ are uncorrelated, then h(T) is UMVUE.
> 

REMARK:  First, the unbiased estimator of 0 should hold for all $\theta$. Second, we need to make sure that h(T) is uncorrelated to all unbiased estimator of 0.

除了上述的how to check UMVUE，现在我们给出另一个方法CR不等式

首先需要明确的是，CR不等式成立必须要求分布族满足正则条件, 并且在重积分中，求导和积分可交换. 幸运的是，指数族满足所有这些条件. 但这不意味着指数族的UNVUE可以达到CR下界. 

$$
CR \ Inequality:Var(\hat g(\bold X)) \geq\frac{[g'(\theta)]^2}{nI(\theta)}
$$

where $\hat g(\bold X)$ is an unbiased estimator of $g(\theta)$.

我们现在提出寻找UMVUE的方法, 第一个是Rao-Blackwell Theorem. 通过这个theorem, 我们可以在无偏估计和充分统计量的基础上找到一个方差更小的无偏估计.

> Let T be a sufficient statistic of $g(\theta)$ and $\hat g(\bold X)$ is an unbiased estimate of $g(\theta)$, then $h(T)=E(\hat g(\bold X)|T)$ is a better estimate of $g(\theta)$.
> 

REMARK: The reason we use sufficient statistics here is that by definition of sufficient statistics, given T, distribution of  $\bold X$ doesn’t depend on $\theta$, then  the conditional expectation $E(\hat g(\bold X)|T)$ doesn’t depend on $\theta$, hence we ensure that $h(T)$ is statistics. Also, we can continue this process again and again, say we now have h(T), which is better than $\hat g(\bold X)$, then we can construct $h'(T)$, where $h'(T)=E(h(T)|T)$. $h'(T)$  is better than $h(T)$. But the problem is we don’t know when the process will end.

Finally, we give the strongest Theorem Lehmann-Scheffe Theorem.

> Let T(X) be a sufficient and complete statistics. If $\hat g(T(\bold X))$ is an unbiased estimator of $g(\theta)$, then $\hat g(T(\bold X))$ is the unique UMVUE of $g(\theta)$.
> 

REMARK: So, this theorem sovle the problem mentioned above, as $\hat g(T(\bold X))$ is unique now, we cannot construct another better unbiased estimator. 

---

hw:

(7) and (8):  If we want to find UMVUE, we have 2 methods:

1. T is sufficient and complete + h(x) is unbiased $\Rightarrow$ f(T) = E(h(x)|T) is UMVUE
2. T is sufficient and complete + directly guess a f(T), do a bias correction

For method 1, try to find some indicator functions as h(x), why?

consider  E(h(x)|T), we have 

$$
 E(h(x)|T=t)= \frac{E(h(x)\cap \{T=t\})}{P(T=t)}=\frac{P(\{h(x)=1\} \cap \{ T=t\})}{P(T=t)}
$$

be careful for the expectation in the numerator, x is random variable and T is now a constant. so the expectation is equal to $P(\{h(x)=1\} \cap \{ T=t\})$ which is easy to do. Or, we think about the conditional probability mass function, even though a condition is given here, h(x) can only take 0 or 1. Then, it is still a expectation of indicator function. Also, remember to find the distribution of T, e.g. sum of geometric distribution is negative binomial distribution.

(6): so if T~Ga(n/2, 1/2), then aT~Ga(n/2, 1/(2a))