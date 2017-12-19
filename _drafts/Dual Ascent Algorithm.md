# Dual Ascent Algorithm

Dual Ascent算法是ADMM算法的基础算法之一，想要了解ADMM算法的迭代原理以及分解策略，就必须先弄懂Dual Ascent算法的原理。在谈Dual Ascent算法前，我们先回顾一下Gradient Descent算法。

## Gradient Descent

Gradient Descent 算法求解的是无约束优化问题。如下：
$$
minimize   f(x)
$$
Gradient Descent 算法是沿负梯度方向以特定步长前进，不断迭代找到最优解。迭代过程为：
$$
x^{k+1}=x^k-\alpha*\Delta f(x^k)
$$
$\alpha$为步长，$\Delta f(x^k)$为$f(x)$在$x^k$处的梯度

## Dual Ascent 

Dual ascent算法求解的是等式约束优化问题。
$$
minimize   f(x)\\
Ax=b
$$
优化问题$(3)$的拉格朗日函数为
$$
L(x,y)=f(x)+y^T(Ax-b)
$$
优化问题$(3)$的对偶问题
$$
g(y)=\inf_{x}L(X,Y)=-f^*(-A^Ty)-b^Ty
$$
Dual Ascent 算法与Gradient算法一样是求解的minimize优化问题。Dual Ascent算法中将minimize问题转换为对偶的maximize问题，迭代过程为：
$$
x^{k+1}=argminL(x^k,y^k)
$$

$$
y^{k+1}=y^k+\alpha(Ax^{k+1}-b)
$$

$(5)$式为x-minimization步骤，实际上是实现了$g(y)=\inf_{x}L(X,Y)$的功能，$(7)$式为对偶变量y的更新，此处其实就是**Gradient Descent**的步骤，从$(4)$式可以看出$Ax^{k+1}-b$为$g(y)$在此处的斜率。

从这里可以看出其实Dual Ascent算法与Gradient Descent算法本质上是一样的，只是优化的方向不同而已。



## Dual Decomposition

既然Dual Ascent算法与Gradient Descent算法本质上是一样的，只是优化的方向不同，在求解效率上没有任何优势。**不过**，Dual Ascent算法的优势在于Dual Decomposition。





































[Reference]

Boyd S, Parikh N, Chu E, et al. Distributed optimization and statistical learning via the alternating direction method of multipliers[J]. Foundations and Trends® in Machine Learning, 2011, 3(1): 1-122.





