# lecture 3-4

lecture 3:

for a r.v. from an exponential family, it has a very good property, which is that $T(\vec{X})$ is sufficient statistics, which is easy to prove.

**minimal sufficient statistics** states that if T(X) and S(X) are 2 sufficient statistics, and there exists a function s.t. f(S(X))=T(X), then T(X) is the minimal sufficient statistics. 想法还是自然的，由于mapping是一种丢失信息的操作，mapping完之后还能是充分的话，那它就是minimal的. 不过需要注意，**minimal sufficient statistics** 不是唯一的，我们可以用一个 1 to 1 function去得到另一个**minimal sufficient statistics.** 

对于minimal sufficient statistics, 存在一个充要条件: $f(\bold x; \theta)/f(\bold y; \theta)$与$\theta$ 无关$\iff$$T(\bold x)=T(\bold y)$.

REMARK: 对于这个定理的理解我们首先思考密度函数的比例，由factorization theorem，我们知道这个比例总是可以表达出T(X)和T(Y), 并且这些充分统计量是和参数无法再分离的. 所以想不depend on参数, 就要想办法让T(X)=T(Y), 很多时候我们会发现参数可以由此消除. 

A more important concept is complete statistics. 如果说充分统计量是包含了所有的信息，那么完全统计量就是要求没有多余的信息. 充分统计量可以缺少部分的信息. 

对于exponential family来讲，如果我们将其表达成natural form，并且$\varTheta^*$, 即natural form $\theta$被表达成$\psi$后的新参数空间，是$\R^k$的子集且有内点，或者说 $\varTheta^*$ $\varTheta^*$$\R^k$. 那么一个极优良的性质就产生了，$T(\vec{X})$不仅是sufficient的更是complete的，这给我们使用Basu’s Theorem创造了极优的条件. Basu’s Theorem告诉我们如果上述的条件满足，即$T(x)$是完全充分统计量, 而且一个r.v.  $V(\vec{X})$的分布和 $\theta$无关，那么 $V(\vec{X})$和  $T(\vec{X})$就是独立的. 

对于完全统计量，我们也有非常好的性质，就是若$T$是完全统计量，那么对于一个可测函数$\delta(\cdot)$,$\delta({T})$也是完全统计量. 我们可以从完全统计量的定义看出这一点, 完全统计量说如果对于一个函数$\psi(\cdot)$, 满足$E_{\theta}(\psi(T(X))=0 \ , \forall \theta \in \varTheta$, 都有$\psi(T(X)) \xrightarrow{a.s.}0, \ \forall \theta \in \varTheta$, 就称T(X)为完全统计量. 

REMARK: 事实上，我不认为这是显然的, we should prove it

$proof:$

now consider the statistics $\delta(T(\bold{X}))$, let $\varphi( \cdot)$be a function s.t. $E[\varphi{(\delta(T(\bold{X}))})]=0$. equivalently, we have $E[\varphi∘\delta(T(X))]=0$, here we define a new function $\varphi∘\delta(\cdot)$. As we know that $T(X)$ is complete. Then, we have $\varphi∘\delta(T(X)) \xrightarrow{a.s.}0 \iff \varphi[\delta{(T(X)})]\xrightarrow{a.s.}0$, hence we prove that $\delta(T(X))$  is complete.    $\square$

值得注意的是，完备统计量是对于一个分布族而言的($\{f(x;\theta):\theta\in \varTheta\}$), 比如N(0,1)，这是一个特定的分布, 我们可以定义g(x)=x, 显然E(g(x))=0, 但P(g(x)=0)=0, 不等于1. 但对于一个分布族，$N(\theta,1), \ \theta \in \R$,完备统计量是存在的. 我们需要区分分布族的完备性和统计量的完备性

---

lecture 4:

对于maximum likelihood estimate，我们会考察似然函数的二阶导数是否小于0，不过很多时候我们会发现二阶导并不是恒小于0的，但我注意，我们只需要带入$\hat\theta^{MLE}$,检查在这一个点二阶导数是否小于0即可. 当然，对于个别的函数，二阶导数也不足够充分，我们还需要考察一阶导数在该点左右两边的正负

对于极大似然估计，若概率密度或者质量函数本身带有常数，在极大似然函数里可以将这个常数丢掉. 原因在于当我们对似然函数取对数后，常数项会被抽离出来，求导后必然等于0. 就算该似然函数需要通过定义才能找到最大值，但是由于其是常数，$\theta$的取值也不影响似然函数，所以常数是可以丢掉的

---

hw: