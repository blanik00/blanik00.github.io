---
title: 'Variance, Covariance, Correlation'
date: 2020-06-21
permalink: /posts/2020/06/21/var_cov_cor
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/dpnDuSPM1XU"> </iframe>

## 기댓값 복습
- X가 이산형
$E[X]=\sum_ix_if_X(x_i)$  
$E[g(x)]=\sum_ig(x_i)p(x_i)$  

- X가 연속형
$E[X]=\int xf(x)\;dx$  
$E[X]=\int g(x)f(x)\;dx$  

기대값으로부터 유도되는 것들도 있는데, 대표적으로 Variance가 있다.

$V[X]=E[(X-E[X])^2]$  

## 기댓값의 특성 - Independence
- 독립인 확률 변수 X, Y가 있고, 임의의 함수 h, g가 있을 때, 다음을 만족한다.
$$E[g(X)h(Y)]=E[g(X)]E[h(Y)]$$

- 증명  
$E[g(X)h(Y)]$  
$=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}g(x)h(y)f_{X,Y}(x,y)dxdy$  
$=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}g(x)h(y)f_{X}(x)f_{Y}(y)dxdy$  
$=\int_{-\infty}^{\infty}g(x)f_{X}(x)dx\int_{-\infty}^{\infty}h(y)f_{Y}(y)dy$  
$=E[g(X)]E[h(Y)]$  

## Covariance, Variance of Sums, and Correlation
- 두 확률 변수의 Covariance(공분산)은 두 확률 변수의 관계를 알려준다.
$$Cov(X,Y)=E[(X-E[X])(Y-E[Y])]$$

- 식에서 볼 수 있듯이 Covariance도 Expectation으로부터 나온 것임

- 식을 한번 풀어보자.  
$Cov(X,Y)$  
$=E[(X-E[X])(Y-E[Y])]$  
$=E[XY-XE[Y]-YE[X]+E[X]E[Y]]$  
$=E[XY]-E[X]E[Y]-E[Y]E[X]+E[X]E[Y]$  
$=E[XY]-E[X]E[Y]$  

즉, $Cov(X,Y)=E[XY]-E[X]E[Y]$로 표현할 수 있다. 앞으로는 이 공식을 사용할 것이다.

## Properties of Covariance
- 두 확률 변수 X, Y가 독립이라면, $Cov(X, Y)=0$이다.
- 하지만 $Cov(X, Y)=0$이라고 해서 두 확률 변수 X, Y가 독립인 것은 아니다.
- $Cov(X,Y)=Cov(Y,X)$
- $Cov(X,X)=Var(X)$
- $Cov(aX,Y)=aCov(X,Y)$
- $Cov(\sum_{i=1}^{n}X_i+\sum_{j=1}^{m}Y_i)=\sum_{i=1}^{n}\sum_{j=1}^{m}Cov(X_i, Y_j)$

## Variance of a Sum of Random Variables
확률 변수 $X_1, X_2, ..., X_n$의 합의 분산은 다음과 같다.

$Var(\sum_{i=1}^nX_i)$  
$=Cov(\sum_{i=1}^nX_i, \sum_{j=1}^nX_j)$  
$=\sum_{i=1}^n\sum_{j=1}^nCov(X_i, X_j)$  
$=\sum_{i=1}^nVar(X_i)+\sum_{i\neq j}Cov(X_i, X_j)$  
$=\sum_{i=1}^nVar(X_i)+2\sum_{i< j}Cov(X_i, X_j)$  
$(\because Cov(X_i, X_j)=Cov(X_j, X_i))$  

여기서 본것처럼 논문 등에서도 $\sum_{i\neq j}$를 $2\sum_{i< j}$로 많이 표기한다.

## Variance of a Sum of Random Variables - Example
$Var(X_1+X_2)$  
$=Cov(X_1+X_2, X_1+X_2)$  
$=Cov(X_1+X_2, X_1)+Cov(X_1+X_2, X_2)$  
$=Cov(X_1, X_1)+Cov(X_1, X_2)+Cov(X_1, X_2)+Cov(X_2, X_2)$  
$=Var(X_1)+2Cov(X_1,X_2)+Var(X_2)$  

## Variance of a Sum of Random Variables - Independence
만약 $X_1, X_2, ..., X_n$이 pairwise independent($i\neq j$일 때 $X_i, X_j$는 독립)라면 다음을 만족한다.

$Var(\sum_{i=1}^nX_i)=Var(X_1)+Var(X_2)+...+Var(X_n)$  

## Variance of a Sum of Random Variables - Sample Variance
$X_1, X_2, ..., X_n$을 평균이 $\mu$이고, 분산이 $\sigma^2$이며, iid인 확률 변수라고 하자. sample의 평균을 $\bar{X}={1\over n}\sum_{i=1}^nX_i$이라고 할 수 있으며, $X_i-\bar{X}$를 deviation이라고 부른다.

이 때, 확률 변수 $S^2=\sum_{i=1}^n{(X_i-\bar{X})^2\over n-1}$을 sample variance라고 한다.

## Variance of a Sum of Random Variables - Examle 1
파라미터 n과 p를 가지는 이항 분포의 분산을 구하라.

X는 파라미터 p를 가지는 n개의 독립인 베르누이 확률 변수의 합으로 두자. 즉, $X=X_1+X_2+...+X_n$이다.

$Var(X)$  
$=Var(X_1)+Var(X_2)+...+Var(X_n)$  
$=p(1-p)+p(1-p)+...+p(1-p)$  
$np(1-p)$  

## Variance of a Sum of Random Variables - Examle 2
$X_1, X_2, ..., X_n$을 iid이며, 분산이 $\sigma^2$이라고 하자. $Cov(X_i-\bar{X}, \bar{X})=0$임을 보여라.

$Cov(X_i-\bar{X}, \bar{X})$  
$=Cov(X_i, \bar{X})-Cov(\bar{X},\bar{X})$  
$=Cov(X_i, {1\over n}\sum_{j=1}^nX_j)-Var(\bar{X})$  
$={1\over n}\sum_{j=1}^nCov(X_i, X_j)-{\sigma^2\over n}$  
$={1\over n}Cov(X_i, X_i)-{\sigma^2\over n}$  
$={1\over n}\sigma^2-{\sigma^2\over n}$  
$=0$  

## Correlation
- 상관계수
- 두 확률 변수 X, Y의 상관계수 $\rho(X, Y)$는 다음과 같이 정의된다.

$$\rho(X, Y)={Cov(X, Y)\over \sqrt{Var(X)Var(Y)}}, \quad -1\le \rho(X, Y)\le 1$$

- Covariance와 비슷한 개념으로 생각하면 됨. 다만 Correlation은 -1과 1 사이에 떨어지도록 설계한 값. 즉, Scaled version of Covariance

- Covariance가 10이라고 한다면 그것이 큰 것인지 작은 것인지 알 수 없으나, Correlation이 0.9라고 한다면 이것은 명백하게 큰 것이다.