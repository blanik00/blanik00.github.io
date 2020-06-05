---
title: 'Exponential Distribution'
date: 2020-06-05
permalink: /posts/2020/06/05/exponential_distribution
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/3C0yKJhMwek"> </iframe>

## Exponential Distribution
- 정규 분포 다음으로 많이 쓰임
- 시간과 관련된 분포
- 지수 분포의 확률 함수(PDF)  
$$f(x)=
\begin{cases}
\lambda e^{-\lambda x} & if\;\;x\ge0\\
0 & if\;\;x<0
\end{cases}$$
- 지수 분포의 누적 확률 함수(CDF)  
$$F(x)=\int_{0}^{x}\lambda e^{-\lambda x}dx=
\begin{cases}
1-e^{-\lambda x} & if\;\;x\ge0\\
0 & if\;\;x<0
\end{cases}$$
- 지수 분포는 포아송 분포에 의해 생성된 두 이벤트 사이의 거리를 모델링한다.
- 파라미터는 $\lambda$이며, 단위 시간 당 발생한 이벤트의 평균 수를 의미한다.

## Exponential Distribution - Mean and Variance
- $E[X]=1/\lambda$
- $E[X^2]=2/\lambda^2$
- $V[X]=1/\lambda^2$

## Exponential Distribution - Example 1
어떤 사람이 통화를 하는 데 걸리는 시간을 X로 두자. 그리고 이 사람의 통화 시간은 $\lambda=1/10$인 지수 분포를 따른다.  
1. 이 사람의 통화 시간이 10분 이상이 될 확률을 구하라.  
$P[X>10]=P[X\le10]=1-F(10)=1-(1-e^{-\lambda 10})=e^{-1}\approx0.368$  
2. 10분에서 20분 통화할 확률을 구하라.  
$P[10< X< 20]$  
$=P[X<20]-P[X-10]$  
$=F(20)-F(10)=$  
$1-(1-e^{-2})-(1-(1-e^{-1}))=$  
$e^{-1}-e^{-2}$  
$\approx=0.233$  

## Exponential Distribution - Example 2
수중 구조 전문팀이 난파선을 찾고 있다. 난파선을 찾는 데 평균적으로 5일이 걸린다면, 1일 이내로 난파선을 찾을 확률은 얼마인가?

$X$ : 난파선의 위치를 알아내는 데 까지 걸리는 시간  

$\lambda=1/5=0.2$  
$P[X<1]=F(1)=1-(1-e^{-\lambda 1})\approx0.181$  

## Exponential Distribution - Memoryless Property
- 기억상실 특성
- $P[X\ge s+t]=P[X\ge s]$
- 즉, 과거에 얼만큼 시간을 보냈든 관계 없이, 앞으로의 확률은 $P[X\ge s]$로 동일하다.

## Exponential Distribution - Memoryless Property - Example
자동차의 배터리는 평균적으로 10,000 마일을 가면 소진된다고 한다. 어떤 사람이 5,000 마일 여행을 하고 싶은데, 배터리 교환 없이 여행을 마칠 수 있는 확률은 얼마인가?

여행 시작 전에 이미 t 마일 만큼의 배터리를 사용했다고 하자.

문제의 조건을 그대로 풀려고 하면 $P[X\ge t+5000\|x\ge 5000]$을 풀어야 한다. 하지만 Memoryless Property에 의해 $P[X\ge 5000]$로 간소화시킬 수 있다.

$\lambda=1/10000$  
$P[X\ge 5000]$  
$=1-(1-e^{-5000/10000})$  
$=e^{-1/2}$  

## Poisson Distribution vs Exponential Distribution
- 포아송 분포는 특정 시간 동안 몇 번의 사건이 발생했는가에 관심을 가진다.
- 지수 분포는 이벤트 사이의 시간 간격(Interarrival time)에 관심을 가진다.
- 콜센터를 예를 들어 이해해보자. 콜센터에 일 분에 3 건의 전화가 온다고 하자. 그렇다면 $\lambda=3$이다.
- s와 t 시간 사이에 걸려온 전화의 횟수는 포아송 분포를 따른다. $X\sim Poisson(3(t-s))$
- $i-1$번째와 $i$번째 전화 사이의 시간은 지수 분포를 따른다. $W_i\sim Exp(3)$

1. $t=0$, $t=2$ 사이에 전화가 걸려오지 않을 확률을 구하라. 전화가 걸려오지 않을 확률이므로 포아송 분포를 따르며, $P[X=0]$을 구하면 된다.  
$X\sim Poisson(6)$  
$P[X=0]=e^{-6}6^0/0!=e^{-6}=0.0025$이다.  
2. 첫 번째 전화가 2분이 지나서 올 확률을 구하라. 시간에 관심을 가지므로 지수 분포를 따르며, $P[X\ge 2]$를 구하면 된다.  
$W_i\sim Exp(3)$  
$P[X\ge 2]=1-P[X\le 2]=1-(1-e^{-6})=e^{-6}=0.0025$  