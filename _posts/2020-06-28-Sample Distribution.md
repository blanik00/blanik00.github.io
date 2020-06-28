---
title: 'Sample Distribution'
date: 2020-06-28
permalink: /posts/2020/06/27/sample_distribution
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/EjQq2s9C9Sc"> </iframe>

## Population, Sample
- Population : 전체(모집단)

- Sample : 부분(모집단의 부분집합, 표본)

## Sampling
모집단에서 표본을 추출하는 작업을 의미

### 표기

|  | Mean | Variance |
|:--:|:--:|:--:|
| Population | $\mu$ | $\sigma^2$ |
| Sample | $\bar{X}$ | $S^2$ |

## Statistic(통계량)
- Statistic : 샘플들의 함수

- 통계량의 복수형인 Statistics를 통계학을 의미하는 Statistics와 혼동하기 쉽다. 문맥을 보고 파악하면 된다.

- 통계학에서 배우는 가장 중요한 함수가 세 가지 있다.
	- 확률 변수(Random Variable)
	- 확률 함수(Probability Function)
	- 통계량(Statistic)

- 대표적인 통계량은 다음과 같다.
	- $\bar{X}=(x_1+x_2+...+x_n)/n$
	- $S^2={1\over n-1}\sum_{i=1}^{n}(x_1-\bar{X})^2$

## Sampling Distribution
- Sampling Distribution : 통계량의 분포

- 그렇다면 Sampling Distribution은 $\bar{X}$, $S^2$의 분포를 말한다.

- 여기서 Sampling된 것들은 서로 독립이다.

## Sampling Distribution of Sample Mean
- $\bar{X}=(x_1+x_2+...+x_n)/n$

- 그렇다면 $\bar{X}$의 기댓값은 얼마일까  

$E[\bar{X}]=E[(x_1+x_2+...+x_n)/n]$  

$=E[x_1]/n+E[x_2]/n+...+E[x_n]/n$  

$=\mu/n+\mu/n+...+\mu/n$  

$=n(\mu/n)=\mu$  

- 또한 $\bar{X}$의 분산은 얼마일까  

$V[\bar{X}]=V[(x_1+x_2+...+x_n)/n]$  

$=V[x_1]/n^2+V[x_2]/n^2+...+V[x_n]/n^2$  

$=\sigma^2/n^2+\sigma^2/n^2+...+\sigma^2/n^2$  

$=n(\sigma^2/n^2)=\sigma^2/n$  

### 정규 분포를 예로 들어보자.
모집단이 $N(\mu, \sigma^2)$를 따른다고 하자. 여기서 iid인 샘플 n개를 추출했다.($X_1$, $X_2$, ..., $X_n$) 그렇다면 $\bar{X}$는 $N(\mu, \sigma^2/n)$를 따른다. 표준정규분포로 바꾸려면 $Z=(\bar{X}-\mu)/(\sigma/\sqrt{n})$로 두면 된다.

## Central Limit Theorem(중심극한정리)
- 평균이 $\mu$이고 분산이 $\sigma^2$인 임의의 모집단에서 표본의 크기인 $n$이 충분히 크면($n\ge 30$), 표본 평균 $\bar{X}$는 근사적으로 정규분포 $N(\mu, \sigma^2/n)$를 따른다. (여기서 n은 한 표본 안에 들어있는 원소의 수를 뜻한다.)

## Sampling Distribution of Sample Mean - Two Population
- 두 개의 독립적인 모집단의 평균의 차이를 알고 싶다. 하지만 모집단을 모두 파악하는 것은 불가능하다.

- 두 개의 모집단(어떤 분포를 따르든 상관 없다.)으로부터 샘플을 추출해 비교하는 방법을 취한다.
	- Pop1. ($\mu_1$, $\sigma_1^2$) $\rightarrow$ $n_1$개 샘플링 $\rightarrow$ $\bar{X_1}$

	- Pop2. ($\mu_2$, $\sigma_2^2$) $\rightarrow$ $n_2$개 샘플링 $\rightarrow$ $\bar{X_2}$

- $\bar{X_1}-\bar{X_2}$의 기댓값과 분산을 보고 두 모집단의 차이를 확인할 수 있다.
	- $E[\bar{X_1}-\bar{X_2}]=E[\bar{X_1}]-E[\bar{X_2}]=\mu_1-\mu_2$
	- $V[\bar{X_1}-\bar{X_2}]=V[\bar{X_1}]+V[\bar{X_2}]=\sigma_1^2/n_1+\sigma_2^2/n_2$

즉, $\bar{X_1}-\bar{X_2}$는 $N(\mu_1-\mu_2, \sigma_1^2/n_1+\sigma_2^2/n_2)$를 따른다.