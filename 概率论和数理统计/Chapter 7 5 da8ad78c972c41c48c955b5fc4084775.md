# Chapter 7.5

### ANOVA

It is important to remember the deductions and definitions of a few formulas or identities.

error sum of squares with-in sample variations

$$
\begin{split}
SSE=&\sum_i^I \sum_j^J (x_{ij}-\bar{x}_{i.})^2 \\
&=\sum_i^I(J-1)S^2_i \\
&=(J-1)(S^2_1+S^2_2+...+S^2_I)
\end{split}
$$

sum of squares of treatments

$$
\begin{split}
SSTr&=\sum_i^I\sum_j^J(\bar{x}_{i.}-\bar{x})^2 \\
&=\sum_i^IJ(\bar{x}_{i.}-\bar{x})^2 \\
&=J[(\bar{x}_{1.}-\bar{x})^2+...+(\bar{x}_{I.}-\bar{x})^2]
\end{split}
$$

and finally, total sum of squares

$$
\begin{split}
SST &=\sum_i^I\sum_j^J(x_{ij}-\bar{x})^2 \\
&=SSTr \ + \ SSE
\end{split}
$$

we have some nice properties:

- $SSE$ and $SSTr$ are independent
- $SSE / \sigma^2 \sim \chi^2(IJ-I)$
- If $H_0$ is true, where $\mu_0 =\mu_1=...=\mu_I$, then $SSTr/\sigma^2 \sim \chi^2(I-1)$.

Hence, we can use it to construct a F distribution, if F is too large, we reject $H_0$. 因为$H_0$成立的话，组间均方就和祝内均方一样，他们的比例自然不应该有大偏差

对均方的定义如下, 每一自由度上的平方和

$MSTr=SSTr/(I-1),$ where $f_{SSTr}=I-1$

$MSE=SSE/(IJ-I)$, where $f_{SSE}=IJ-I$

对于自由度, 我们可以通过它的分布来记忆, 但更本质的来源还是要看SST和SSTr的定义. 比如SSE, 在每个treatment组内, 实际上的维度或者说自由变量只有J-1个, 因为最后一个总是可以被均值和前J-1个线性表出, 值得注意的是均值不算自由变量. 我们又知道总共有I组, 所以自由度就是$I(J-1)$

检验统计量为, 

$$
F=\frac{MSTr}{MSE}=\frac{SSTr/(I-1)}{SSE/(IJ-I)}
$$

这条公式是自然的, 我们想检验每个treatment的期望是否相等, 如果真的全部相等, 那么组间的期望也会相等. 所以我们尝试让SSTr和SSE做比较, 但注意到这两个变量的自由度不同, 为了排除自由度的干扰, 我们应该除去自由度, 或者说使用均方做比较

如果$H_1$为真, 那么SSTr就会很大, 这导致F很大, 自然有拒绝域$R=\{\vec{x}:F \geq F_{\alpha}(I-1,IJ-I) \}$