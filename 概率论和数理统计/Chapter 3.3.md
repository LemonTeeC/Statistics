# Chapter 3.3

### 9. X,Y~ U(0,1) and are i.i.d. , find pdf of Z= X+Y

From convolution formula, we know that

$$
f_{Z}(z)=\int_D f_X(x)f_Y(z-x)dx
$$

Then, we note that the variables change to x and z, we first note that $x \in(0,1), z \in (0,2)$.

Then we find the intersection of X and Z-X. The integration area should be $\{0<x<1\} \cap \{0<z-x<1\}$. We plot the diagram and find that the integration have 2 sections.

### 12. $X_1,X_2$ are i.i.d. with pdf f(x)= 2x, 0<x<1; f(x) = 0, otherwise. Find max{1,2} - min{1,2}

As $\max\{X_1,X_2\}-\min\{X_1,X_2\}=|X_1-X_2|$, we first find the pdf of $X_1-X_2$. Normally, we will do it directly, but for this question, we can do transformation to simply it.

$$
\begin{cases}
u=x_1-x_2\\
v=x_2
\end{cases} \Rightarrow |J|=\bigg|\frac{\partial(x_1,x_2)}{\partial(u,v)}\bigg|=1
$$

Then, we find the joint pdf 

$$
f_{U,V}(u,v)=f_X(u+v)f_Y(v)
$$

After that, we find the marginal pdf

$$
f_U(u)=\int_D f_X(u+v)f_Y(v) dv
$$