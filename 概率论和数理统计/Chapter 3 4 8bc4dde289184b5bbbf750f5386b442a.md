# Chapter 3.4

### 3. Choose 2 different numbers from 0,1,…,n, find E(|X-Y|)

We simply consider the definition of E(Z=|X-Y|). Note that if Z=i, then there are many choices of X and Y while all the choices have equal probability.

$P(X=i,Y=j)=\frac{1}{n(n+1)}, i\neq j$ 

Then let X=i ,Y=j, for |X-Y|=a, we have 2 cases, one is X>Y, one is X<Y, the case for X-Y=0 is trivial.

For X-Y>0, we do it like recursion. We first randomly choose X=i, then we can choose Y from 0 to i-1. Sum up all the cases of X from i=0 to i=n, we have $\sum\limits_{i=0}^{n}(\sum\limits_{j=0}^{i-1}(i-j))$ .

Similarly for X-Y<0, we have $\sum\limits_{i=0}^{n}(\sum\limits_{j=i+1}^{n}(j-i))$. Sum the 2 cases together, we get the answer.

### 14. X,Y~N(0,1), find E( max{X, Y} )

1. we need to know $\max\{X,Y\}= \frac{X+Y+|X-Y|}{2}$
2. Note that normal distribution has additivity, so X-Y~N(0,2)

### 20. Roll a dice for n times, find the covariance and correlation for the occurrence of 1 and occurrence of 6.

If we want to find the occurrence of1 and 6, we don’t need to consider P(X=k) directly, instead, we can let 

$$
X_i=\begin{cases}1, i^{th}\ term \ is \ 1\\0,others\end{cases}
$$

then, we have 

$$
X=\sum\limits^{n}_{i=1}X_i
$$

We note that

$$
X_i \sim b(1,\frac{1}{6})\Rightarrow X\sim b(n,\frac{1}{6})
$$

Then, consider XY, we have

$$
XY=(X_1+X_2+...+X_n)(Y_1+Y_2+...+Y_n)=\sum\limits_{i=1}^{n}(X_iY_i)+\sum\limits_{i<j}^{}(X_iY_j)+\sum\limits_{i>j}^{}(X_iY_j)
$$

We know that $\{X_iY_i=1\}=\empty$, then $E(\sum\limits_{i=1}^{n}(X_iY_i))=0$.

### 44. Let X~N(0,1) and Y has probability 0.5 to get 1 or -1 respectively. X and Y are independent. Let Z =  XY. (i) prove Z~N(0,1) (ii) X and Z don’t have correlation but are not independent.

We note that X is continuous random variable and Y is discrete random variable, then we cannot use formula to deduct the density function of Z. We need to use the distribution of Z in order to solve the question.

$$
P(XY\leq z)=\frac{1}{2}P(X\leq z)+\frac{1}{2}P(-X\leq z) =P(X\leq z)\Rightarrow Z\sim N(0,1)
$$