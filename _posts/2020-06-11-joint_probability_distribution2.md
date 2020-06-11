---
title: 'Joint Probability Distribution(2)'
date: 2020-06-11
permalink: /posts/2020/06/11/joint_probability_distribution2
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/XOP_ENqWdJ0"> </iframe>

## Marginal Probability Function(주변 확률 변수)
### 이산형  
$g(x)=\sum_{y}p_{XY}(x,y)$ - Summation of $p_{XY}(x,y)$ over the values of $Y$  
$h(y)=\sum_{x}p_{XY}(x,y)$ - Summation of $p_{XY}(x,y)$ over the values of $X$

### 연속형  
$g(x)=\int_{-\infty}^{\infty}f_{XY}(x,y)\;dy$ - Integral of $f_{XY}(x,y)$ with respect to $Y$ over the values of $Y$.
$h(y)=\int_{-\infty}^{\infty}f_{XY}(x,y)\;dx$ - Integral of $f_{XY}(x,y)$ with respect to $X$ over the values of $X$.

### $X$와 $Y$의 결합 확률 분포로부터 $X$의 분포를 구할 수 있다.

$F_{X}(a)$  
$=P[X\le a]$  
$=P[X\le a, Y < \infty]$  
$=\lim_{b\to\infty}P[X\le a, Y < b]$ (결합 누적 확률 분포)  
$=\lim_{b\to\infty}F_{XY}(a,b)$  

## Independent Random Variables(독립 확률 변수)
- 확률 변수 $X$와 $Y$는 다음 조건을 만족할 때 독립이다.  
$$P[X\in A, Y\in B]=P[X\in A]P[Y\in B]$$

- 이를 일반화 시켜보면, 확률 변수 $X_1, X_2, ..., X_n$은 다음 조건을 만족할 때 독립이다.  
$$P[X_1\in A_1, ..., X_n\in A_n]=P[X_1\in A_1],..., P[X_n\in A_n]$$

즉, 결합 확률 함수를 각각의 주변 확률 변수의 곱으로 표현할 수 있다면 독립이다.

independent $\Leftrightarrow$ dependent

Loosely speaking, 분포 하나를 알더라도 그것이 다른 분포에 영향을 미치지 않을 때 독립이라고 한다.

### 증명
- 이산형  
$P[X\in A, Y\in B]$  
$=\sum_{y\in B}\sum_{x\in A}p(x,y)$  
$=\sum_{y\in B}\sum_{x\in A}p_X(x)p_Y(y)$  
$=\sum_{x\in A}p_X(x)\sum_{y\in B}p_Y(y)$  
$=P[X\in A]P[Y\in B]$  

- 연속형  
$P[X\in A, Y\in B]$  
$=\int_{y\in B}\int_{x\in A}f(x,y)\;dxdy$  
$=\int_{y\in B}\int_{x\in A}f_X(x)f_Y(y)\;dxdy$  
$=\int_{x\in A}f_X(x)\;dx\int_{y\in B}f_Y(y)\;dy$  
$=P[X\in A]P[Y\in B]$  

## Independent Random Variables - Example
$X$, $Y$의 결합 확률 분포가 다음과 같다. $X\sim Geometric(\theta)$, $Y\sim Bernoulli(\theta)$를 따른다고 할 때, $X$, $Y$는 독립인가?

$P_{XY}(x,y)$  
$=\theta^{y+1}(1-\theta)^{x-y}$  
$=\theta^{y}\theta(1-\theta)^{x-1+1-y}$  
$=\theta^{y}\theta(1-\theta)^{x-1+1-y}$  
$=(1-\theta)^{x-1}\theta\cdot\theta^{y}(1-\theta)^{1-y}$  
$=p_X(x)\cdot p_Y(y)$  

