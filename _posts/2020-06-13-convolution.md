---
title: 'Joint Probability Distribution - Convolution'
date: 2020-06-13
permalink: /posts/2020/06/13/convolution
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/Uc5MuEfGZ6Q"> </iframe>

## Sums of Independent Random Variables
확률 변수 $X, Y$는 독립이다. $X + Y$의 확률 분포는 무엇인가

우선은 $X+Y$의 누적 확률 함수를 구해보자.

$F_{XY}(a)=P[X+Y < a]$  

$=\int\int_{X+Y < a}f_{XY}(xy)\;dx\;dy$  

$=\int\int_{X+Y < a}f_{X}(x)f_{Y}(y)\;dx\;dy$  

$=\int_{-\infty}^{\infty}\int_{-\infty}^{a-y} f_{X}(x)f_{Y}(y)\;dx\;dy$  

$=\int_{-\infty}^{\infty}\int_{-\infty}^{a-y} f_{X}(x)\;dxf_{Y}(y)\;dy$  

$=\int_{-\infty}^{\infty}F_X(a-y)f_{Y}(y)\;dy$  

$F_{X+Y}$는 $F_X$, $F_Y$의 convolution이라고 한다.

convolution($F_{X+Y}$)을 미분해서 PDF인 $f_{XY}$를 구할 수 있다.

$f_{XY}$  

$={d\over da}\int_{-\infty}^{\infty}F_X(a-y)f_Y(y)\;dy$  

$=\int_{-\infty}^{\infty}{d\over da}F_X(a-y)f_Y(y)\;dy$  

$=\int_{-\infty}^{\infty}f_X(a-y)f_Y(y)\;dy$  

즉, 확률 변수 $X, Y$가 독립이라면 $X+Y$의 PDF는 $\int_{-\infty}^{\infty}f_X(a-y)f_Y(y)\;dy$와 같이 표현한다.

## Identically Distributed Uniform Random Variables
X, Y가 독립이며, Uniform Distribution을 따르며, 파라미터는 (0,1)이다. 이 때 $X+Y$의 PDF를 구하라.

$f_{X+Y}(a)=\int_{0}^{1}f_X(a-y)f_Y(y)\;dy$  

$=\int_{0}^{1}f_X(a-y)\;dy$  ($\because f_Y(y)=1$)  

$Let\;a-y=t,\;dy=-dt$  

$=\int_{a}^{a-1}f_X(t)\;(-dt)$  

$=\int_{a}^{a-1}f_X(t)\;(-dt)$  

$=\int_{a-1}^{a}f_X(t)\;dt$  

**Case 1.** $0\le a \le 1$  

$\int_{0}^{a}f_X(t)\;dt=a$  

**Case 2.** $1 < a < 2$  

$\int_{a-1}^{1}f_X(t)\;dt=2-a$  

<그림 1>  

## Gamma Random Variables
- 서로 독립이며, 파라미터가 $(s,\lambda)$, $(t,\lambda)$인 감마 분포를 따르는 확률 변수 X, Y가 있다. 이 때, X+Y는 파라미터가 $(s+t, \lambda)$인 감마 분포를 따른다.
- 일반화 시켜 보면, 서로 독립이며, 파라미터가 $(t_1,\lambda)$, ..., $(t_n,\lambda)$인 감마 분포를 따르는 확률 변수 $X_1$, ..., $X_n$이 있다. 이 때, $X_1+...+X_n$는 파라미터가 $(\sum_{i=1}^{n}t_i, \lambda)$인 감마 분포를 따른다.

## Gamma and Exponential Random Variables
- 파라미터가 $\lambda$이며, 지수 분포를 따르는 확률 변수 $X_1$, ..., $X_n$이 있다. 이 때, $X_1+...+X_n$는 파라미터가 $(n, \lambda)$인 감마 분포를 따른다.

증명 생략

## Normal Random Distribution
- 파라미터가 $(\mu_i, \sigma_i)$이며, 정규 분포를 따르는 확률 변수 $X_1$, ..., $X_n$이 있다. 이 때, $X_1+...+X_n$는 파라미터가 $(\sum_{i=1}^{n}\mu_i, \sum_{i=1}^{n}\sigma_i^2)$인 감마 분포를 따른다.

## Poisson Random Distribution
- 파라미터가 $\lambda_i$이며, 포아송 분포를 따르는 확률 변수 $X_1$, ..., $X_n$이 있다. 이 때, $X_1+...+X_n$는 파라미터가 $\sum_{i=1}^{n}\lambda_i$인 포아송 분포 분포를 따른다.

## Binomial Random Distribution
- 파라미터가 $(n_i, p)$이며, 이항 분포를 따르는 확률 변수 $X_1$, ..., $X_n$이 있다. 이 때, $X_1+...+X_n$는 파라미터가 $(\sum_{i=1}^{n}n_i, p)$인 이항 분포를 따른다.