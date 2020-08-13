---
title: '부정적분과 정적분'
date: 2020-08-15
permalink: /lecture/2020/08/15/indefinite_integral
category:
  - lecture
tags:
  - 미적분
---

## 부정적분

$$\int f(x)dx=F(x)+c$$

- 이 때 $F(x)$를 부정적분이라고 한다.

- 또한, $c$를 적분 상수라고 한다.

- ${d\over dx}\int f(x)dx=f(x)$

- $\int{d\over dx} f(x)dx=f(x)+c$

## 부정적분의 성질
- 덧셈, 뺄셈, 실수배에 대해서 자유롭다.

- $\int kf(x)dx=k\int f(x)dx$

- $\int \{f(x)\pm g(x)\}dx=\int f(x)dx\pm\int g(x)dx$

- $\int x^ndx={1\over n+1}x^{n+1}+c$  (n은 음이 아닌 정수)

- $\int 1dx=x+c$

## 정적분

$$\int_{a}^{b}f(x)dx=lim_{n\rightarrow \infty}\sum_{k=1}^{n}f(a+{b-a\over n}k){b-a\over n}$$

- 구간을 n등분한다.

- 등분된 구간은 함수값을 가진다.

- 구간$({b-a\over n})$을 곱하면 해당 구간의 넓이가 된다.

- 1부터 n까지의 구간의 넓이의 합을 구하면 전체 구간의 넓이를 구할 수 있다.

- n을 무한으로 보내면 정적분이 된다.

### 다르게 표현
- ${b-a\over n}=\triangle x$

- $x_k=a+{b-a\over n}k=a+k\triangle x$

$$\int_{a}^{b}f(x)dx=lim_{n\rightarrow \infty}\sum_{k=1}^{n}f(x_k)\triangle x$$

## 정적분과 미분의 관계

$${d\over dx}\int_{a}^{x}f(t)dt=f(x)$$

- 증명은 생략하지만 중요한 내용

## 미적분의 기본 정리

$$\int_{a}^{b}f(x)dx=F(b)-F(a)$$


## 정적분의 성질
- 덧셈, 뺄셈, 실수배에 대해서 자유롭다.

- $\int_{a}^{b} kf(x)dx=k\int_{a}^{b} f(x)dx$

- $\int_{a}^{b} \{f(x)\pm g(x)\}dx=\int_{a}^{b} f(x)dx\pm\int_{a}^{b} g(x)dx$

- $\int_{a}^{c} f(x)dx + \int_{c}^{b} f(x)dx=\int_{a}^{b} f(x)dx$
	- ex. $\int_{1}^{3} f(x)dx + \int_{3}^{2} f(x)dx=\int_{1}^{2} f(x)dx$

- $\int_{a}^{a} f(x)dx=0$

- $\int_{a}^{b} f(x)dx=-\int_{b}^{a} f(x)dx$