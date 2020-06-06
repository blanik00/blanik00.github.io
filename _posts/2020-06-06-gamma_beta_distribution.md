---
title: 'Gamma & Beta Distribution'
date: 2020-06-06
permalink: /posts/2020/06/06/gamma_beta_distribution
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/RNkT4YG8B3A"> </iframe>

## Gamma Distribution
- 지수 분포를 일반화시킨 개념

> Random Variable X : $k$개의 이벤트가 발생할 때 까지 걸린 시간

- $$f(n)=
\begin{cases}
{\lambda^{\alpha}\over \Gamma(\alpha)}x^{\alpha-1}e^{-\lambda x} & for\;\;x > 0 \\
0 & otherwise 
\end{cases}$$

- 감마 분포를 설명하기 위해서는 감마 함수를 알아야 한다.
- $\Gamma(a)=\int_{0}^{\infty}x^{a-1}e^{-x}\;dx$
- $\Gamma(1)=\int_{0}^{\infty}x^{1-1}e^{-x}\;dx=\int_{0}^{\infty}e^{-x}\;dx=1$
- $\Gamma(1/2)=\sqrt{\pi}$
- $\Gamma(\alpha)=(\alpha-1)\Gamma(\alpha-1)\quad(for\;\;\alpha > 1)$
- $\Gamma(n)=(n-1)!\quad(if\;n\;is\;a\;positive\;integer)$

- Gamma Distribution은 두 개의 파라미터를 가지고 있다. $\alpha$는 shape parameter(형상 모수)라고 하며, $\lambda$는 rate(scale) paramtere(척도 모수)라고 한다.

![1](https://user-images.githubusercontent.com/26649034/83935919-19d05380-a7f9-11ea-9c2b-57335997eaa8.png)

## Gamma Distribution - Expectation and Variance
- $E[X]={\alpha\over\lambda}$
- $V[X]={\alpha\over\lambda^2}$

## More about Gamma Distribution
### 감마 분포는 지수 분포를 일반화한 형태다.
- $Gamma(1,\lambda)=Exponential(\lambda)$

- $X\sim\Gamma(1,\lambda)$
- $f_X(x)={\lambda\over \Gamma(1)}x^{1-1}e^{-\lambda x}=\lambda e^{-\lambda x}$

### 감마 분포는 지수 분포의 합이다.
$X_1, X_2, ..., X_{\alpha}$이 파라미터 $\lambda$를 가지며, 서로 독립적이며 동일한 분포(iid)를 따른다. 이 때 $X=X_1+X_2+...+X_{\alpha}$는 파라미터가 $\alpha, \lambda$인 감마 분포를 따른다.

## Gamma Distribution - Example 1
어떤 학생은 30분에 한 마리의 물고기를 잡는다. 이 학생이 네 마리를 잡을 때 까지 걸리는 시간이 2시간에서 4시간 사이일 확률은 얼마인가?

> RV X : 물고기 네 마리 잡을 때 까지 걸리는 시간

$X\sim Gamma(4,2)$

$P[2\le X\le4]=\int_{2}^{4}{2^{4}\over \Gamma(2)}x^{4-1}e^{-2 x}\;\;dx=0.39$

## Gamma Distribution - Example 2
> RV X : 20개의 철판을 배송할 때 걸리는 시간

$X$는 다음과 같은 분포를 따른다고 하자.  

$X\sim Gamma(20,1.6)$

이 때 15분 이내에 배송할 수 있을 확률을 구하라.

$P[X<15]=\int_{0}^{15}{1.6^{20	}\over \Gamma(20)}x^{20-1}e^{-1.6 x}\;\;dx=0.82$

## Beta Distribution
- 비율을 다룰 때 사용
- 불순률, 작동률, 불량률 등

- $$f(x)=
\begin{cases}
{1\over B(\alpha, \beta)}x^{\alpha-1}(1-x)^{\beta-1} & for\;\;0\le x \le 1 \\
0 & otherwise 
\end{cases}$$

- 베타 분포를 설명하기 위해서는 베타 함수를 알아야 한다.
- $B(\alpha, \beta)={\Gamma(\alpha)\Gamma(\beta)\over \Gamma(\alpha+\beta)}$
- $B(\alpha, \beta)=B(\beta, \alpha)$
- $B(1, \beta)=1/\beta$
- $B(\alpha+1, \beta)={\alpha\over\alpha+\beta}B(\alpha, \beta)$

## Beta Distribution - Expectation and Variance
- $E[X]={\alpha\over\alpha+\beta}$
- $V[X]={\alpha\beta\over(\alpha+\beta)^2(\alpha+\beta+1)}$

## Beta Distribution - Parameter
- $\alpha, \beta$ 두 개의 파라미터를 가진다.
- $\alpha=\beta$라면 분포는 대칭이다.
- $\alpha=\beta<1$은 수명 분포(고장률 등)을 모델링하는 데 사용된다.

![2](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f3/Beta_distribution_pdf.svg/650px-Beta_distribution_pdf.svg.png)

## Beta Distribution - Example 1

DVD를 배송할 때 불량률이 $\alpha=2, \beta=5$인 베타 분포를 따른다. 불량률이 20~30%일 확률을 구하라.

> RV X : 배송시 발생하는 불량률

$X\sim B(2,5)$

$P[0.2\le X\le 0.3]=\int_{0.2}^{0.3}{1\over B(2, 5)}x^{2-1}(1-x)^{5-1}\;\;dx=0.235$


## Beta Distribution - Example 2
여왕벌이 새로운 벌집을 찾아 나섰다. 일벌들이 여왕벌을 따라 나섰다. 따라가는 일벌들의 비율을 베타 분포로 모델링할 수 있다. $\alpha=2, \beta=4.8$인 베타 분포를 따른다고 할 때 50% 이상의 일벌들이 여왕벌을 따라갈 확률을 구하라.

> RV X : 여왕벌을 따라가는 일벌들의 비율

$X\sim B(2,4.8)$

$P[X\ge0.5]=\int_{0.5}^{1}{1\over B(2, 4.8)}x^{2-1}(1-x)^{4.8-1}\;\;dx=0.122$