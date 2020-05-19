---
title: '기대값, 분산(Expectation, Variance)'
date: 2020-05-17
permalink: /posts/2020/05/19/expectation_variance
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/1YDBHTM-e_I"> </iframe>  

## Center - Expectation of Discrete Random Variable
다음 수들의 평균을 구해보자.
> 1, 2, 3, 4, 5

정답은 3이다. 평균을 구하는 공식에 의해 ${1+2+3+4+5\over 5}=3$이 된다. 하지만 여기에는 각각의 숫자가 나올 확률이 동일하다는 가정이 숨어있다.

확률 분포의 기대값(=평균)을 구하기 위해서는 각각의 값에 그 값이 나올 확률을 곱해 더하면 된다.

$$E[X]=\sum_{i}x_if_X(x_i)$$

즉, 산술 평균은 모든 값이 나올 확률이 동일하다는 가정을 가진 기대값의 특수한 케이스라고 할 수 있다.

### 예제
게임에서 이기면 100을 벌고, 지면 100,000을 잃는다. 게임에서 이길 확률을 0.99라고 할 때, $X$를 게임에서 벌거나 잃는 돈이라고 하자. $E[X]$는 얼마인가?

$E[X]=100\times 0.99+100000\times 0.01=-901$

## Expectation of Discrete Random Variable - Coin Example 1
RV X : 동전을 두 개 던져 나오는 앞면의 수
앞 면이 나올 확률은 1/2

$p(0)={1\over 4}, p(1)={1\over 2}, p(2)={1\over 4}$  

$E[X]=(0)({1\over 4})+(1)({1\over 2})+(2)({1\over 4})=1$

## Expectation of Discrete Random Variable - Coin Example 2
RV X : 동전을 두 개 던져 나오는 앞면의 수  
앞 면이 나올 확률은 $p$

$P(X=0)=P(t,t)=(1-p)^2$  
$P(1)=P(h,t)+P(t,h)=2p(1-p)$  
$P(2)=P(h,h)=p^2$  

$E[X]=(0)((1-p)^2)+(1)(2p(1-p))+(2)(p^2)=1$

## Expectation of a Function of a Random Variable
- 지금까지 배웠던 것은 확률변수의 기대값
- 이번에 배울 것은 확률변수의 함수의 기대값
- 별 다를건 없음
- function of X를 g(X)라고 하자.
- $g(x_i)$와 그것이 발생할 확률을 곱해 모두 더하면 된다.

$$E[g(X)]=\sum_ig(x_i)p(x_i)$$

## Expectation of a Function of a Random Variable - Example
RV X : 동전을 두 개 던져 나오는 앞면의 수
앞 면이 나올 확률은 1/2

$p(0)={1\over 4}, p(1)={1\over 2}, p(2)={1\over 4}$  

$g(x)={3\over x+1}$  

$E[g(x)]=E[{3\over x+1}]=({3\over 0+1})({1\over 4})+({3\over 1+1})({1\over 2})+({3\over 2+1})({1\over 4})={7\over 4}$  

## Expectation of a Function of a Random Variable
- $c, d$는 상수
- $E[c]=\sum cp(x)=c\sum p(x)=c\cdot 1=c$  
- $E[cX]=\sum cxp(x)=c\sum xp(x)=c\cdot E[X]$  
- $E[cX+d]=\sum(cx+d)p(x)=c\sum xp(x)+d\sum p(x)=cE[X]+d$  
- 그렇다면 $E[X^n]$은 무엇일까?

$$E[X^n]=\sum_xx^np(x)$$

- $E[X^n]$를 확률 변수 X의 "n차 적률(nth moment)"이라고 한다.
- $E[X]$는 first moment이고, $E[X^2]$는 second moment이다.

## Expected Value of Sums of Random Variables
확률 변수 $X_1, X_2, ..., X_n$은 다음 수식을 만족한다.  
$$E[\sum_{i=1}^{n}X_i]=\sum_{i=1}^{n}E[X_i]$$
$$E[X_1+X_2+...+X_n]=E[X_1]+E[X_2]+...+E[X_n]$$

## Expected Value of Sums of Random Variables - Example
RV X : 주사위를 $N$번 던졌을 때 값들의 합  
$E[X_i]=\sum_{i=1}^{6}i\cdot({1\over 6})=3.5$  
$E[X]=E[\sum_{i=1}^{N}X_i]=\sum_{i=1}^{N}E[X_i]=3.5n$  

## Variability - Variance
RV $X$가 있고, $X$의 기대값이 $E[X]$일 때, $X$의 분산은 다음과 같이 정의한다.  
$$V(X)=E[(X-E[X])^2]$$
- 평균을 기점으로 얼마만큼 떨어져있는지를 제곱의 스케일로 표현한 측도
- 음수가 될 수 없다.

$V(X)=E[(X-E[X])^2]$  
$=E(X^2)-{E[X]}^2$ (이 형태가 많이 쓰임)

## Variance - Example
RV X : 동전을 두 개 던져 나오는 앞면의 수
앞 면이 나올 확률은 1/2

$p(0)={1\over 4}, p(1)={1\over 2}, p(2)={1\over 4}$  

$E[X^2]=\sum x^2p(x)=3/2$  
$V(X)=E(X^2)-{E[X]}^2=3/2-1^2=1/2$  

### Variance of a Function of a Random Variable
$$V(g(X))=E[(g(X)-\mu_{g(X)})^2]$$
- $c, d$는 상수
- $V(c)=E[(c-E[c])^2]=E[(c-c)^2]=0$
- $V(cX)=E[(cX-cE[X])^2]=c^2E[(X-E[X])^2]=c^2V(X)$
- $V(cX+d)=E[(cX+d-E[cX+d])^2]=E[(cX+d-cE[X]-d)^2]=c^2E[(X-E[X])^2]=c^2V(X)$

## Standard Deviation
분산의 제곱근  
$$SD[X]=\sqrt{V[X]}$$