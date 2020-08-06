---
title: 'Linear Regression'
date: 2020-08-10
permalink: /posts/2020/08/10/linear_regression
category:
  - posts
---

## 변수 사이의 관계
- 확정적 관계 : X변수만으로 Y를 100% 표현(오차항 없음)
   - 힘=f(질량, 가속도), 주행거리=f(속도, 시간)

- 확률적 관계 : X변수와 오차항이 Y를 표현(오차항 있음)
   - 반도체 수율=f(설비 파라미터들의 상태, 온도, 습도)+$\epsilon$
   - 포도주 가격 = f(강우량, 온도, 포도품종) + $\epsilon$

## 선형회귀모델
- 출력변수 Y를 입력변수 X들의 **선형결합**으로 표현한 모델
   - 예 : $y=\beta_0+\beta_1x_1+\epsilon$
   - $\beta_0$는 y절편이고, $\beta_1$은 기울기이다.

- 선형회귀모델에서 $y$는 $x$로 설명할 수 있는 부분($\beta_0+\beta_1x_1$)과 $x$로 설명할 수 없는 부분($\epsilon$)으로 나뉘어진다.

## 선형회귀모델의 목적
1. X변수와 Y변수 사이의 관계를 수치로 **설명**
2. 미래의 반응변수 (Y)값을 **예측**

## 선형회귀모델 분류
![image](https://user-images.githubusercontent.com/26649034/89372557-6cf35380-d721-11ea-96e4-fbee46bb6a3b.png)

![](https://user-images.githubusercontent.com/26649034/89550459-98bb2a00-d844-11ea-8ea1-23cba28af765.png)

## 선형회귀 모델의 가정
- 아래 조건을 만족하지 못하면 선형회귀 모델의 신빙성이 떨어짐

- 확률오차 가정
   - 오차항 $\epsilon$은 평균이 0이고, 분산이 $\sigma^2$인 정규분포를 따른다.
   - $\epsilon\sim N(0,\sigma^2)$
   - $Y_i=\beta_0+\beta_1x_1+\epsilon$인데, $\epsilon$이 정규 분포를 따르므로 $Y_i$ 또한 어떤 분포를 따르게 된다. 즉, $Y_i$도 확률 변수다.
   - $Y_i$가 어떤 확률 변수인지 파악하기 위해 평균과 분산을 구해보자.
   - $E[Y_i]=E[\beta_0+\beta_1x_1]+E[\epsilon]=\beta_0+\beta_1x_1(\because \beta_0+\beta_1x_1\;is\;constant, E[\epsilon]=0)$
   - $V[Y_i]=V[\beta_0+\beta_1x_1]+V[\epsilon]=\sigma^2(\because \beta_0+\beta_1x_1\;is\;constant, V[\beta_0+\beta_1x_1]=0)$ 
   - 즉, $Y_i\sim N(\beta_0+\beta_1x_i, \sigma^2)$
   
   ![image](https://user-images.githubusercontent.com/26649034/89374522-8e0a7300-d726-11ea-9723-495acf1edfe1.png)

- 엄밀히 정의하자면, 선형회귀는 입력변수 X와 출력변수 Y의 평균과의 관계를 설명하는 선형식을 찾는 것이다.
   - $Y=\beta_0+\beta_1x_1+\beta_2x_2+...+\beta_px_p+\epsilon$
   - $E[Y]=\beta_0+\beta_1x_1+\beta_2x_2+...+\beta_px_p$

## 파라미터 추정
- $C(\beta_0, \beta_1)=\sum_{i=1}^{n}(Y_i-(\beta_0+\beta_1x_i))^2$을 최소화하는 파라미터 $\beta_0,\beta_1$을 찾으면 된다.

## 파라미터 추정 알고리즘
- 만약 cost function이 convex하다면, 전역 최적해가 존재한다. 선형회귀 모델의 cost function은 convex하다.

- 이 때는 미분값이 0이 되는 지점을 찾으면 된다.
   - ${\partial C(\beta_0, \beta_1)\over \partial\beta_0}-2\sum_{i=1}^{n}Y_i-(\beta_0+ \beta_1x_i)=0$

   - ${\partial C(\beta_0, \beta_1)\over \partial\beta_1}-2\sum_{i=1}^{n}Y_i-(\beta_0+ \beta_1x_i)x_i=0$

   - $\hat{\beta_0}=\bar{Y}-\hat{\beta_1}\bar{X}$

   - $\hat{\beta_1}={\sigma_{i=1}^{n}(X_i-\bar{X})(Y_i-\bar{Y})\over \sum_{i=1}^{n}(X_i-\bar{X})^2}$

- $f(X)=\hat{Y}=\hat{\beta_0}+\hat{\beta_1}X$

## 잔차(Residual)
![image](https://user-images.githubusercontent.com/26649034/89378545-f8271600-d72e-11ea-9579-96dafeacaf94.png)

- 최소 제곱법으로 구해진 직선과 실제 y값의 차이를 잔차라고 한다.(왼쪽 그림)

- 확률 오차와는 다른 개념이다.(오른쪽 그림)

- 확률 오차는 확정되기 이전의 직선을 기반으로 한다. 그렇기 때문에 확률 오차는 확률 분포를 따른다. 반면 잔차는 확률 분포가 아니라 정해진 값이다.

- 즉, 잔차 $e$는 확률 오차 $\epsilon$이 실제로 구현된 값이라고 볼 수 있다.

# 추정
## Least Square Estimator

- $\hat{\beta_0}=\bar{Y}-\hat{\beta_1}\bar{X}$

- $\hat{\beta_1}={\sigma_{i=1}^{n}(X_i-\bar{X})(Y_i-\bar{Y})\over \sum_{i=1}^{n}(X_i-\bar{X})^2}$

- Estimator(추정량) : 샘플의 함수(a function of the samples)

- 추정량의 용도 : 알려지지 않은 파라미터를 추정($\beta_0, \beta_1$)

- 추정량의 종류
   1. 점추정(point estimator)
   2. 구간추정(interval estimator)

## Least Square Estimator의 성질
- Gauss-Markov Theorem에 따르면 Least Square Estimator는 best linear unbiased estimator(BLUE)이다.

- BLUE를 만족하려면 다음 조건을 만족해야 한다.
   1. 불편 추정량(unbiased estimator)이다.
   2. 우리가 구한 불편 추정량이 다른 추정량보다 작은 분산을 가지고 있다.

1. unbiased estimator
	- 불편추정량 : 추정량의 기대값이 모수와 같아진다면 이 추정량을 불편추정량이라고 한다.
   - $E[\hat{\beta_0}]=\beta_0$
   - $E[\hat{\beta_1}]=\beta_1$

2. smallest variance estimator
   - $\hat{\theta}$ : any other unbiased estimators
   - $V[a\hat{\beta_0}]\le V[b\hat{\theta}]$
   - $V[a\hat{\beta_1}]\le V[b\hat{\theta}]$

## 파라미터에 대한 점추정
- 점추정은 우리가 이미 한 것이다.

- $Y_i=\beta_0+\beta_1x_1+\epsilon$

- $\epsilon\sim N(0,\sigma^2)$

- $\beta_0$에 대한 점추정 식 : $\hat{\beta_0}=\bar{Y}-\hat{\beta_1}\bar{X}$

- $\beta_1$에 대한 점추정 식 : $\hat{\beta_1}={\sigma_{i=1}^{n}(X_i-\bar{X})(Y_i-\bar{Y})\over \sum_{i=1}^{n}(X_i-\bar{X})^2}$

- $\sigma^2$에 대한 점추정 식 : $\sigma^2=({1\over n-2})\sum_{i=1}^{n}e_i^2$($n$ : 샘플의 수, $e_i$: 잔차)

## 파라미터에 대한 구간추정
- 앞에서 배운 점추정은 알려지지 않은 파라미터를 추정할 때 하나의 값으로 추정하는 방법이다.

- 구간추정은 하나의 값으로 추정하는 것이 아니라 lower bound와 upper bound를 가지는 구간으로 추정하기 때문에 보다 유연한 정보를 제공할 수 있다.

- $\theta$(파라미터)에 대한 구간추정의 기본 형태
   - $\hat{\theta}-상수값\cdot \hat{\theta}의 표준편차\le\theta\le\hat{\theta}+상수값\cdot \hat{\theta}의 표준편차$
   - 즉, 점추정량, 점추정량의 표준편차, 상수값을 알아야 한다.

## 기울기에 대한 신뢰구간
- $\beta_1$에 대한 $100(1-\alpha)\%$의 신뢰구간을 구하자. (신뢰구간을 구하자=구간 추정을 해보자)

- $n$ : 관측치 수

$$\hat{\beta}_1-t_{ {\alpha\over 2},n-2}\cdot sd\{\hat{\beta}_1\}\le\beta_1\le \hat{\beta}_1+t_{ {\alpha\over 2},n-2}\cdot sd\{\hat{\beta}_1\}$$

- $\hat{\beta_1}={\sigma_{i=1}^{n}(X_i-\bar{X})(Y_i-\bar{Y})\over \sum_{i=1}^{n}(X_i-\bar{X})^2}$
   - $\beta_1$의 점추정량

- $t_{ {\alpha\over 2},n-2}$ : 유의수준 $1-\alpha$ 하에서 자유도가 $n-2$인 t분포의 값

- $sd\{\hat{\beta}_1\}=\sqrt{ {\hat{\sigma} }^2\over \sum_{i=1}^{n}(X_i-\bar{X})^2}$ : $\hat{\beta}_1$의 표준편차

## Y절편에 대한 신뢰구간
![image](https://user-images.githubusercontent.com/26649034/89478449-f90d8580-d7ca-11ea-91a0-789b593170d0.png)

# 가설 검정
## 기울기에 대한 가설검정
- 가설검정 : 알려지지 않은 파라미터에 대한 가설을 세우고 이를 검정

- 선형회귀에서는 기울기에 대한 가설검정이 중요

- $H_0:\beta_0=0\;\;vs\;\;H_1:\beta_1\neq0$
   - 귀무가설 : $\beta_0=0$이다.
   - 대립가설 : $\beta_0\neq0$이다.
	
- 이 가설에 대한 검정이 중요한 이유는 기울기가 0이라면 X변수와 Y변수는 서로 관계가 없는 것이기 때문이다.

## 결정계수(Coefficient of Determination: $R^2$)
![image](https://user-images.githubusercontent.com/26649034/89480745-19404300-d7d1-11ea-8d9a-b8f843967f03.png)

- $SST=\sum_{i=1}^{n}(Y_i-\bar{Y})^2$, Y의 총 변동량

- $SSR=\sum_{i=1}^{n}(\hat{Y_i}-\bar{Y})^2$, X변수에 의해 설명된 양

- $SST=\sum_{i=1}^{n}(Y_i-\hat{Y_i})^2$, 에러에 의해 설명된 양

- $SST=SSR+SSE$

- ${SSR\over SST}=1$ : 직선 위에 모든 점이 있다. 에러가 없다. 확정적인 관계이다. (ex. $f=ma$)

- ${SSR\over SST}=0$ : 직선 위에 점이 하나도 없다. $Y$의 평균으로 예측한 것과 비교해서 $X$에 대한 정보를 추가해도 변한 것이 아무것도 없다.(현재 가지고 있는 X변수는 Y의 예측에 아무런 도움이 되지 않는다.)

$$R^2={SSR\over SST}=1-{SSE\over SST}$$

- 결정 계수는 다음과 같이 해석할 수 있다.
   - 사용하고 있는 X변수가 Y변수의 분산을 얼마나 줄였는지 정도를 나타낸다. 예를 들어, 결정계수가 1이라면 분산을 100% 줄인 것이며, 0.2라면 20% 줄인 것이다.

   - 단순히 Y의 평균값을 사용했을 때 대비 X 정보를 사용함으로써 얻는 성능 향상 정도

   - 사용하고 있는 X변수의 품질

## 수정 결정계수(Adjusted $R^2$)
- 결정계수는 유의하지 않은 변수가 추가되어도 항상 증가한다는 문제점이 있다.

$$R^2_{adj}=1-[{n-1\over n-(p+1)}]{SSE\over SST}$$

- $n$ : 관측치의 수

- $p$ : 변수의 수

- 수정 결정계수는 앞에 특정 계수를 곱해줌으로써 보정한다. 즉, 유의하지 않은 변수가 추가될 경우 값이 증가되지 않게 한다.

- 설명변수가 서로 다른 회귀모형의 설명력을 비교할 때 사용한다.

- 그러므로 수정 결정계수는 결정계수보다 작거나 같다. 즉, $R_{adj}^{2}\le R^2$를 만족한다.

## 선형회귀모델에서의 분산 분석
- 분산분석 : Analysis of Variance(ANOVA)

- 분산 정보를 이용하여 분석

- 궁극적으로는 가설 검정을 행하는 용도로 사용됨

- 앞에서 배웠던 SST, SSR, SSE는 모두 분산이다. 예를 들어, SST는 평균을 기준으로 $Y_i$가 얼마나 퍼져있는가를 보여준다.

- 이 세가지를 활용해 분석하는 것이 분산 분석이다.

$${SSR\over SSE}$$

- ${SSR\over SSE}>1$
   - X변수에 의해 설명된 양 > 에러에 의해 설명된 양
   - X변수가 Y설명(예측)에 유의미한 영향
   - X변수의 계수(기울기)가 0이 아님

- $0\le {SSR\over SSE}\le1$
   - X변수에 의해 설명된 양 < 에러에 의해 설명된 양
   - X변수가 Y설명(예측)에 영향을 끼치지 못함
   - X변수의 계수(기울기)가 0이라고 할 수 있다

- 이 값이 얼마나 커야 큰 값일까? 값의 분포를 알면 통계적으로 판단할 수 있다. 안타깝게도 직접적으로 분포를 정의할 수는 없다. 하지만 SSR과 SSE는 각각 카이제곱 분포를 따른다. 그러므로 값이 F분포를 따른다는 것을 알 수 있다.

- 단순선형회귀모델의 경우, $SSR\sim\chi^2(v_1=1), SSE\sim\chi^2(v_2=n-2)$

- $F^*={SSR/1\over SSE/n-2}={MSR\over MSE}\sim F(1,n-2)$

- $P-value=P(Y\ge F^*)$로 정의할 수 있으며 $Y\sim F(1,n-2)$이다.

- X변수에 의해 설명된 양이 에러에 의해 설명된 양보다 통계적으로 충분히 크면 $F^*$의 값은 커지게 되고, P-value는 작아진다. 이 값이 0에 가까우면 귀무가설을 기각하고, X 변수는 중요하므로 기울기가 0이 아니게 된다.


# 출처
1. [회귀 모델의 종류와 특징](https://danbi-ncsoft.github.io/study/2018/05/04/study-regression_model_summary.html)
2. [선형회귀모델](https://www.youtube.com/watch?v=4Yo297HQyAk&list=PLpIPLT0Pf7IoTxTCi2MEQ94MZnHaxrP0j&index=23)