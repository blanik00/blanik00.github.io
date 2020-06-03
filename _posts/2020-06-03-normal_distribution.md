---
title: 'Normal Distribution'
date: 2020-06-03
permalink: /posts/2020/06/03/normal_distribution
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/e3ZAl1CS3t8"> </iframe>  

## Normal Distribution
- 정규 확률 변수는 $(-\infty, \infty)$ 범위의 실수를 가진다.
- 확률 함수

$$\mathcal{N}(x;\mu,\sigma)={1\over\sigma\sqrt{2\pi}}exp(-{1\over2}({x-\mu\over \sigma}))$$

![1](https://upload.wikimedia.org/wikipedia/commons/thumb/7/74/Normal_Distribution_PDF.svg/680px-Normal_Distribution_PDF.svg.png)

## Characteristics of Normal Distribution
- 평균을 기준으로 대칭(Symmetric about its mean)
- 확률은 $X=\mu$일 때 최대가 된다.(unimodal)
- 커브의 아랫 부분의 면적은 1이다.

## Normal Distribution - Mean and Variance
- $E[X]=\mu$
- $V[X]=\sigma^2$
- $Std[X]=\sigma$

## Standard Normal Distribution
- 정규분포를 표준화한 것
- 확률 변수 $X$는 정규 분포를 따른다.  

$X\sim \mathcal{N}(\mu, \sigma)$

- 새로운 확률 변수 $Z={X-\mu\over\sigma}$를 만든다.
- $Z$는 평균이 0이고, 표준편차가 1인 정규분포를 따르게 된다. 이것을 표준 정규분포라고 부른다.
- 확률 함수  

$$\varphi(z)={1\over\sqrt{2\pi}}exp(-{1\over2}z^2)$$  

- $Z$의 CDF는 테이블로 정리해놨다.(z table, standard normal table)

$$\Phi(z)=P[Z\le z]$$  

- 종모양이며, 0을 기준으로 대칭이다.

## The Normal Approximation to the Binomial Distribution
- 정규 분포는 연속형 확률 분포, 이항 분포는 이산형 확률 분포
- 이항 분포는 이산형이기 때문에 CDF를 구할 때 계산이 복잡하다. 그래서 연속형 확률 변수인 정규 분포로 근사하면 계산이 간편해진다. **즉, 근사는 이산형 확률 분포의 CDF를 구할 때 좀 더 편리하게 하기 위해 사용한다.**
- 단, 아무때나 쓰일 수 있는 것은 아니고, $n$이 충분히 커야 하며, $p$는 0 혹은 1에 너무 가까우면 안된다.

$$X\sim Bin(n,p)\approx Y\sim\mathcal{N}(np,np(1-p))$$

![2](https://user-images.githubusercontent.com/26649034/83638970-f6cd5600-a5e4-11ea-9ef7-cbd45edb4452.png)

- 이항 분포를 정규 분포에 근사하는 것은 태생적으로 오차를 가지고 있다. 그래서 이것을 계산할 때 그냥 계산하지 말고, $P(X=i)=P(i-0.5 < X < i+0.5)$로 계산하는 것이 낫다.(경험적으로 발견한 것임) 
- 이를 Continuity Correction이라고 한다.

## The Normal Approximation to the Binomial Distribution - Example
- 동전을 100번 던진다 하자. 앞면이 나오는 확률 변수는 $X\sim Bin(100,0.5)$이다. 
- $P(45\le X\le 55)$를 구하라.

이 문제를 이산형 확률 분포를 사용해 해결한다고 하자.

$P(45\le X \le 55)=\sum_{i=45}^{55}{100\choose i}(1/2)^i(1/2)^{100-i}$

이를 계산하는 것은 꽤나 복잡하며, 특히 100이 아니라 10,000 혹은 100,000번 던진다면 계산은 더욱 복잡해진다.

이를 정규 분포로 근사해서 계산해보자.

위에서 배운 Continuity Correction을 적용한다.

$Y\sim\mathcal{N}(50,25)$  
$P(44.5\le Y \le 55.5)$  
$=P({44.5-50\over 5}\le {Y-50\over 5})\le {55.5-50\over 5})$  
$=P(1.1\le Z\le 1.1)$  
$=\Phi(1.1)-\Phi(-1.1)$  
$=0.7286$  