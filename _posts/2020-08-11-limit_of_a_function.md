---
title: '함수의 극한'
date: 2020-08-11
permalink: /lecture/2020/08/11/limit_of_a_function
category:
  - lecture
tags:
  - 미적분
---

## 우극한과 좌극한
- 우극한 : $lim_{x\rightarrow a+}f(x)$
	- a보다 큰 쪽에서 a로 다가가는 것

- 좌극한 : $lim_{x\rightarrow a-}f(x)$
	- a보다 작은 쪽에서 a로 다가가는 것

## 함수의 수렴
- $a$에서의 좌극한과 우극한이 동일한 값으로 다가가면 수렴한다고 한다.
	- $lim_{x\rightarrow a+}f(x)=lim_{x\rightarrow a-}f(x)=\alpha$
	- $\alpha$를 극한값이라고 한다.

- $a$의 함수값이 없어도 수렴할 수 있다.

- $a$의 함수값이 수렴하는 값과 다를 수 있다.

## 함수의 극한에 대한 성질
- $lim_{x\rightarrow a}f(x)=\alpha, lim_{x\rightarrow a}g(x)=\beta$

- 실수배, 덧셈, 뺄셈, 곱셈, 나눗셈(분모$\neq 0)$에 대해 자유롭게 연산 가능

- $lim_{x\rightarrow a}cf(x)=c\alpha$

- $lim_{x\rightarrow a}\{f(x)\pm g(x)\}=lim_{x\rightarrow a}f(x)\pm lim_{x\rightarrow a}g(x)=\alpha\pm\beta$

- $lim_{x\rightarrow a}\{f(x)\cdot g(x)\}=lim_{x\rightarrow a}f(x)\cdot lim_{x\rightarrow a}g(x)=\alpha\cdot\beta$

- $lim_{x\rightarrow a}\{ {f(x)\over g(x)} \}={lim_{x\rightarrow a}f(x)\over lim_{x\rightarrow a}g(x)}={\alpha\over\beta}\;\;(\beta\neq0, g(x)\neq0)$

- $f(x)$가 다항함수인 경우 $lim_{x\rightarrow a}f(x)=f(a)$와 같다.
	- $f(x)=c$인 상수함수가 있을 때, $lim_{x\rightarrow a}f(x)=c$이다.
	- $f(x)=x$인 함수가 있을 때, $lim_{x\rightarrow a}f(x)=x$이다.
	- 함수의 극한은 실수배, 덧셈, 뺄셈, 곱셈, 나눗셈(분모$\neq 0)$에 대해 자유롭게 연산 가능하다는 성질을 이용하면, $lim_{x\rightarrow a}x^2+2x+3=a^2+2a+3$과 같이 계산할 수 있다.

## 함수의 극한값 계산
- ${Y\over X}$꼴
	- 인수분해 후 약분
	- 근호를 유리화한 후 ${Y\over X}$로 바꿈

- ${\infty\over\infty}꼴$
	- 분모의 최고차항으로 분모, 분자를 나누어 계산
	- 분모의 차수 == 분자의 차수 : 최고차항의 계수의 비(수렴)
	- 분모의 차수 > 분자의 차수 : 0(수렴)
	- 분모의 차수 < 분자의 차수 : 발산

## 미정계수의 결정
- $lim_{x\rightarrow a}{f(x)\over g(x)}=\alpha, lim_{x\rightarrow a}g(x)=0$이라면 $lim_{x\rightarrow a}f(x)=0$이다.
	- $lim_{x\rightarrow a}{f(x)\over g(x)}g(x)=lim_{x\rightarrow a}{f(x)\over g(x)}lim_{x\rightarrow a}g(x)=lim_{x\rightarrow a}f(x)=\alpha\cdot 0=0$

- $lim_{x\rightarrow a}f(x)=0$은 $f(x)=(x-a)Q_1(x)$로 표현할 수 있음을 뜻한다.

- $lim_{x\rightarrow a}g(x)=0$은 $g(x)=(x-a)Q_2(x)$로 표현할 수 있음을 뜻한다.