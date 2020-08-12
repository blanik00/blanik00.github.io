---
title: '미분계수와 도함수'
date: 2020-08-13
permalink: /lecture/2020/08/13/derivative
category:
  - lecture
tags:
  - 미적분
---

## 평균변화율
- 두 점을 지나는 직선의 기울기

![](https://user-images.githubusercontent.com/26649034/89911722-b6b1d180-dc2c-11ea-8b4c-326a906fee8d.png)

$${\triangle y\over\triangle x}={f(b)-f(a)\over b-a}={f(a+\triangle x)-f(a)\over \triangle x}$$

## 순간변화율, 미분계수
- 접선의 기울기

$$\begin{matrix}
f'(a) &=& lim_{\triangle x\rightarrow\infty}{\triangle y\over\triangle x} \\
       &=& lim_{\triangle x\rightarrow\infty}{f(a+\triangle x)-f(a)\over \triangle x} \\
       &=& lim_{h\rightarrow0}{f(a+h)-f(a)\over h} \\
       &=& lim_{x\rightarrow a}{f(x)-f(a)\over x-a} \\
\end{matrix}$$

## 도함수
- $f'(x), y', {dy\over dx}, {d\over dx}f(x)$

- $f'(x)=lim_{\triangle x\rightarrow\infty}{f(x+\triangle x)-f(x)\over \triangle x}$

## 미분법
- 우리가 자주 사용하는 함수의 도함수를 만들어 놓는 것을 미분이라고 한다.

- 미분법은 미분을 하는 방법

- $y=x^n\Rightarrow y'=nx^{n-1}$

- $y=c\Rightarrow y'=0$

- $y=f(x)\pm g(x)\Rightarrow y'=f'(x)\pm g'(x)$

- $y=cf(x)\Rightarrow y'=cf'(x)$

- 위 내용만 알고 있으면 우리가 알고 있는 모든 다항함수를 미분할 수 있다.

- ex. $y=x^2+2x+3\Rightarrow y'=2x+2$

## 곱의 미분법
- $y=f(x)g(x)\Rightarrow y'=f'(x)g(x)+f(x)g'(x)$


## 미분가능성과 연속성
- 함수 $f(x)$가 $x=a$에서 
	1. 미분가능 $\rightarrow$ 연속
	2. 연속 $\nrightarrow$ 미분가능

- 예를 들어, $f(x)=\|x\|$는 $x=0$에서 연속이지만, 미분 가능하지는 않음.($lim_{ x\rightarrow0+}$에서의 접선의 기울기는 1이고, $lim_{ x\rightarrow0-}$에서의 접선의 기울기는 -1이다.)

## 미분가능성의 활용
- $g(x), h(x)$는 다항함수이다.

$$f(x)=
\begin{cases}
g(x) & (x\ge a) \\
h(x) & (x < a)
\end{cases}$$

실수 전체에서 미분 가능하려면 어떤 조건을 만족해야 할까?
1. $g(a)=h(a)$
2. $g'(a)=h'(a)$