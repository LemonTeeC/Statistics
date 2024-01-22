# Chapter 6.1

### 8.

If  $T(\vec{x})$ is a linear unbiased estimator of $\mu$, then $\sum_{i=1}^na_i=1$. thus we can calculate $Cov(T,\bar{x})$

By bilinear property of covariance, we have 

$$
Cov(T,\bar{x})=\sum_{i=1}^nCov(a_ix_i,\frac{x_i}{n})=\frac{1}{n}\sum^n_{i=1}a_iVar(x_i)=\frac{\sigma^2}{n}
$$

### 11.

The most important thing here is that

$$
x_i-\bar{x}=\frac{n-1}{n}x_1-\frac{1}{n}x_2-...-\frac{1}{n}x_n
$$

Thus

$$
E(x_i-\bar{x})=0,\\  Var(x_i-\bar{x})=\bigg(\frac{n-1}{n}\bigg)^2\sigma^2+\frac{n-1}{n^2}\sigma^2=\frac{n-1}{n}\sigma^2
$$