---
title: 'Conditional Distribution'
date: 2020-06-14
permalink: /posts/2020/06/14/conditional_distribution
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/6GM_cxHn6FY"> </iframe>

## Conditional Distribution
- 사건 $E, F$가 있을 때 조건부 확률 $P(E\|F)={P(E\cap F)\over P(F)}$이다.

- $X, Y$가 이산 확률 변수일 때, Y가 주어졌을 때 X의 conditional PMF는 다음과 같다.  
$P_{X|Y}(x|y)$  
$=P(X=x|Y=y)$  
$={P(X=x, Y=y)\over P(Y=y)}$  
$={p_{XY}(x,y)\over p_Y(y)}$  

- $X, Y$가 연속 확률 변수일 때, Y가 주어졌을 때 X의 conditional PDF는 다음과 같다.  
$P(X\in A|Y=y)$  
$=\int_Af_{X|Y}(x|y)\;dx$  

## Conditional Distribution - Example 1
확률 변수 $X, Y$의 결합 확률 분포 $p_{XY}(x,y)$는 다음과 같다.

$P(0,0)=0.4$  
$P(0,1)=0.2$  
$P(1,0)=0.1$  
$P(1,1)=0.3$  

이 때, $Y=1$일 때의 X의 conditional PMF를 구하라.

$P_{X\|Y}(X=0\|Y=1)={P_{XY}(0,1)\over P_Y(1)}={0.2\over 0.5}=0.4$  
$P_{X\|Y}(X=1\|Y=1)={P_{XY}(1,1)\over P_Y(1)}={0.3\over 0.5}=0.6$  

## Conditional Distribution - Example 2
확률 변수 $X, Y$의 결합 확률 분포 $f_{XY}(x,y)$는 다음과 같다. 

$$f_{XY}(x,y)=
\begin{cases}
{12\over 5}x(2-x-y) & 0 < x <1, 0 < y <1 \\
0 & else \\
\end{cases}$$

$f_{X|Y}(x|y)$  
$={f_{XY}(x,y)\over  f_Y(y)}$  
$={f_{XY}(x,y)\over \int_0^1f(x,y)dx}$  
$={f_{XY}(x,y)\over \int_0^1f(x,y)dx}$  
$={ {12\over 5}x(2-x-y))\over {12\over 5}\int_0^1x(2-x-y)dx}$  
$={x(2-x-y))\over {2\over 3}-{y\over 2}}$  
$={6x(2-x-y)\over 4-3y}$  

## Conditional Distribution - Independent
- 이산형 확률 변수
$P_{X|Y}(x|y)=P(X=x)$  

- 연속형 확률 변수
$f_{X|Y}(x|y)=f_X(x)$  

## Conditional Distribution - Independent - Example
$X, Y$가 서로 독립이며, 파라미터가 $\lambda_1, \lambda_2$인 포아송 분포를 따를 때, $X+Y=n$이 주어졌을 때 $X$의 conditional PMF를 구하라.

$P(X=k|X+Y=n)$  
$={P(X=k,X+Y=n)\over P(X+Y=n)}$  
$={P(X=k,Y=n-k)\over P(X+Y=n)}$  
$={P(X=k)P(Y=n-k)\over P(X+Y=n)}$  
$={e^{-\lambda_1}\lambda_1^k\over k!}{e^{-\lambda_2}\lambda_2^{n-k}\over (n-k)!}[{e^{-(\lambda_1+\lambda_2)}(\lambda_1+\lambda_2)^{n}\over n!}]^{-1}\quad (\because X+Y\sim Poisson(\lambda_1, \lambda_2))$  
$\sim Binomial(n,{1\over\lambda_1+\lambda_2})$