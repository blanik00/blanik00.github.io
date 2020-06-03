---
title: 'Uniform Distribution'
date: 2020-05-31
permalink: /posts/2020/05/31/uniform_distribution
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/6xonZUbFSZ8"> </iframe>  

## Uniform Distributin
- 다음과 같이 정의된 확률 분포를 Uniform Distribution이라고 한다.

$$f(x)=
\begin{cases}
{1\over \beta-\alpha} & if\; \alpha < x < \beta \\
0 & otherwise
\end{cases}$$

## Uniform Distribution - CDF
$$F(a)=\int_{-\infty}^{a}f(x)dx$$

$x$의 범위를 나눠서 생각해보자.

1. $a\le\alpha$
$F(a)=\int_{-\infty}^{a}f(x)dx=\int_{-\infty}^{a}0dx=0$
2. $\alpha\le a\le\beta$
$F(a)=\int_{-\infty}^{a}f(x)dx=\int_{\alpha}^{a}{1\over \beta-\alpha}dx={a-\alpha \over \beta-\alpha}$
3. $a\le\beta$
$F(a)=\int_{\infty}^{a}f(x)dx=\int_{\alpha}^{\beta}{1\over \beta-\alpha}dx=1$

즉, Uniform Distribution의 CDF는 다음과 같다.

$$f(x)=
\begin{cases}
0 & a\le \alpha \\
{a-\alpha \over \beta-\alpha} & \alpha < a < \beta \\
1 & \beta \le a
\end{cases}$$

## Uniform Distribution - Mean and Variance
- $E[X]={\alpha+\beta\over 2}$
- $E[X^2]={\alpha^2+\alpha\beta+\beta^2 \over 3}$
- $E[X]={(\beta-\alpha)^2\over 12}$

## Uniform Distribution - Example
- 한 버스가 7시부터 15분 간격으로 정류장에서 출발한다고 한다. 만약 한 고객이 7시~7시 30분 사이에 도착한다면(Uniformly distributed), P(Wait less than 5 minutes)=?
- 고객은 7시~7시 30분 사이에 도착하므로 특정 시간에 도착할 확률은 1/30이다.
- 고객이 5분 미만으로만 기다리기 위해서는 7시 10분~7시 15분 사이, 7시 25분~7시 30분 사이에 도착해야 한다.
- $P(10<X<15)+P(25<X<30)=1/3$