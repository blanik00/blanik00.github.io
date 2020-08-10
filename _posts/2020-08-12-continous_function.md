---
title: '함수의 연속'
date: 2020-08-12
permalink: /lecture/2020/08/12/continous_function
category:
  - lecture
tags:
  - 미적분
---

## 구간
![](https://user-images.githubusercontent.com/26649034/89797417-e2b64f80-db65-11ea-8772-bbe9b4d1f42b.png)

## $x=a$에서 연속
1. 함수값 $f(a)$가 존재해야 한다. 

2. 극한값 $lim_{x\rightarrow a}f(x)$가 존재해야 한다.

3. $lim_{x\rightarrow a}f(x)=f(a)$를 만족해야 한다.
	- $lim_{x\rightarrow a}f(x)$은 극한값
	- $f(a)$은 함숫값

## 구간에서의 연속
- $y=f(x)$가 어떤 구간에 속하는 모든 점에서 **연속**

## 연속함수의 성질
- 실수배, 덧셈, 뺄셈, 곱셈, 나눗셈(분모가 0이 아닌 경우)에 대해 자유롭다.

- $f(x), g(x)$는 연속함수다.

- $cf(x), f(x)\pm g(x), f(x)\cdot g(x), {f(x)\over g(x)}(g(x)\neq0)$ 모두 연속함수다.

- 상수함수도 연속함수다.

- 다항함수도 연속함수이다.
	- 다항함수는 $f(x)=c, g(x)=x$의 조합으로 표현할 수 있다.

- $f(x), g(x)$가 다항함수일 때, $g(x)\neq0$이라는 조건만 만족하면 ${f(x)\over g(x)}$도 다항함수다.

## 극한으로 나타낸 함수의 연속성
- $\|x\|<1, x=1, x=-1, \|x\|>1$ 네 가지로 나누어 계산

### 1. $x^n$
- $\|x\|<1\Rightarrow lim_{x\rightarrow\infty}x^n=0$

- $x=1\Rightarrow lim_{x\rightarrow\infty}1^n=1$

- $\|x\|>1\Rightarrow lim_{x\rightarrow\infty}x^n=발산$

- $x=-1\Rightarrow lim_{x\rightarrow\infty}(-1)^n=발산(진동)$

### 2. $x^{2n}$
- $\|x\|<1\Rightarrow lim_{x\rightarrow\infty}x^{2n}=0$

- $x=1\Rightarrow lim_{x\rightarrow\infty}1^{2n}=1$

- $\|x\|>1\Rightarrow lim_{x\rightarrow\infty}x^{2n}=발산$

- $x=-1\Rightarrow lim_{x\rightarrow\infty}(-1)^{2n}=1$

### 3. $x^{2n-1}$
- $\|x\|<1\Rightarrow lim_{x\rightarrow\infty}x^{2n-1}=0$

- $x=1\Rightarrow lim_{x\rightarrow\infty}1^{2n-1}=1$

- $\|x\|>1\Rightarrow lim_{x\rightarrow\infty}x^{2n-1}=발산$

- $x=-1\Rightarrow lim_{x\rightarrow\infty}(-1)^{2n-1}=-1$

## 최대, 최소의 정리
- 함수 $f(x)$가 $[a,b]$에서 연속일 때, $f(x)$는 $[a,b]$	에서 반드시 최댓값, 최솟값을 가진다.

## 사이값 정리
- 함수 $f(x)$가 $[a,b]$에서 연속이며, $f(a)\neq f(b)$이라면 $f(c)=k$가 적어도 하나 이상 존재한다. ($k$는 $f(a), f(b)$ 사이에 존재)