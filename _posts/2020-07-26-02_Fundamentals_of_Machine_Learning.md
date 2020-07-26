---
title: '02 Fundamentals of Machine Learning'
date: 2020-07-26
permalink: /posts/2020/07/26/02_Fundamentals_of_Machine_Learning
category:
  - posts
---

# Rule-based Learning

<iframe src="https://www.youtube.com/embed/oNTXMgqCv6E"> </iframe>

<iframe src="https://www.youtube.com/embed/gmKvXBBawmk"> </iframe>

- **완벽한 세상**에서만 잘 작동된다.
	1. 관측 에러가 없으며, 일관적이지 않은 관측 또한 없다.
	2. 랜덤(stochastic) 이벤트가 발생하지 않는다.
	3. 모든 경우의 수를 다 설명할 수 있는 수준의 많은 데이터를 확보했다.

# Decision Tree

<iframe src="https://www.youtube.com/embed/dPP60RSEBek"> </iframe>

- error가 있는 데이터에 통계적 기법을 가미해 학습을 할 수 있는 가장 간단한 방법이 Decision Tree

-  기준이 되는 피처를 정해 데이터셋을 나누고, 나눠진 각각에 대해 다시 피처를 정해 데이터셋을 나누는 작업을 반복해 분류 작업을 수행

- 어떤 피처를 선택할지 결정하기 위해 **Entropy, Information Gain** 개념 도입

## Entropy

<iframe src="https://www.youtube.com/embed/kG-IVxyUAUM"> </iframe>

- 확률 변수의 불확실성을 측정하기 위한 지표
	- ex 1) 압정 A를 반복해서 던졌는데, 계속 Head만 나왔다 -> 불확실성이 낮다.
	- ex 2) 압정 B를 반복해서 던졌는데, Head와 Tail이 반씩 나왔다. -> 불확실성이 높다.

- 높은 엔트로피는 그 확률 변수가 높은 불확실성을 지니고 있음을 뜻한다.

- $$H(X)=-\sum_xP(X=x)log_2P(X=x)$$

- 압정 던지기 게임의 경우 $x$는 Head, Tail이 된다.

### Conditional Entropy
$$\begin{matrix}
H(Y|X) &=& -\sum_xP(X=x)log_2H(Y|X=x)\\
	        &=& -\sum_xP(X=x)\{-\sum_yP(Y=y|X=x)log_2P(Y=y|X=x)\}
\end{matrix}$$

## Information Gain

![](https://user-images.githubusercontent.com/26649034/88475631-b9de6980-cf6c-11ea-828f-b28eb23260f5.png)

- 먼저 전체 엔트로피를 측정해보자.
	- 위에서 정의한 엔트로피 공식을 그대로 사용하면 된다.

	$$\begin{matrix}
			H(Y) &=& -\sum_{y\in\{+, -\}}P(Y=y)log_2P(Y=y)\\
	        &=& -{307\over307+383}log_2{307\over307+383}-{383\over307+383}log_2{383\over307+383}
\end{matrix}$$

- 이번에는 A1, A9이라는 조건을 주고 엔트로피를 측정해보자.
	- Conditional Entropy 공식을 사용하면 된다.

	- $H(Y\|A_1)=-\sum_{x\in\{a, b, ?\}}\sum_{y\in\{+, -\}}P(A_1=x\|Y=y)log_2{P(A_1=x)\over P(A_1=x\|Y=y)}$

	- $H(Y\|A_9)=-\sum_{x\in\{t,f\}}\sum_{y\in\{+, -\}}P(A_9=x\|Y=y)log_2{P(A_9=x)\over P(A_9=x\|Y=y)}$

- 우리는 각 노드들의 엔트로피를 구할 수 있으며, 이를 통해 불확실성이 얼마나 개선되었는지를 측정할 수 있다.

- $IG(Y, A_i)=H(Y)-H(Y\|A_i)$

- $IG(Y, A_9)>IG(Y, A_1)$ 임을 알 수 있다. 즉, $A_9$를 기준으로 나눌 때 불확실성이 더 많이 개선된다.

## Size of Tree
- 분기 작업을 반복하면 거대한 트리를 만들 수 있다.

- 하지만 트리가 너무 거대해지면 학습 데이터셋에는 잘 작동하지만 테스트 데이터셋에서는 잘 작동하지 않는 오버피팅 문제가 발생한다.

![](https://user-images.githubusercontent.com/26649034/88475630-b8ad3c80-cf6c-11ea-8e6b-778e3f5054d3.png)

- 강의에서는 Decision Tree를 Rule-based 기법의 하나로 소개하며, 오버피팅 문제 때문에 실제 상황에서는 많이 사용하지 않는다고 소개함.

# Linear Regression

<iframe src="https://www.youtube.com/embed/70tDiv30WrM"> </iframe>

- 이제부터 본격적으로 통계를 활용한 머신러닝 기법들이 나옴

- Linear Regression은 많은 머신러닝 기법들에 영향을 미친 중요한 기법

- 강의에서는 주택 가격 예측 데이터셋을 활용한다.

- 가정 : 주택 가격은 feature values의 linearly weighted sum으로 표현할 수 있다.

- $$h:\hat{f}(x;\theta)=\sum_{i=0}^{n}\theta_ix_i$$

- $n$ : feature의 수

- 결국 Linear Regression은 $\theta$를 잘 조정해서 좋은 결과를 내도록 하는 것

- 수식을 행렬로 표현할 수 있다.

	- $$X=\begin{bmatrix}
				1 & \cdots & x_n^1 \\
				\vdots & \ddots & \vdots \\
				1 & \cdots & x_n^D
				\end{bmatrix}, 
			\theta=\begin{bmatrix}
						\theta_0 \\
						\vdots \\
						\theta_n 
						\end{bmatrix}$$
	
	- $$h:\hat{f}=X\theta$$

- $\hat{f}$는 예측값이고, 실제값은 다음과 같이 노이즈를 포함시켜 정의한다.

	- $f=X\theta+e=Y$

- Linear Regression의 목표는 실제값과 예측값의 차이를 최소화하는 것이다.

$$\begin{matrix}
\hat{\theta} &=& argmin_\theta(f-\hat{f})^2 \\
	        &=& argmin_\theta(Y-X\theta)^2 \\
	        &=& argmin_\theta(Y-X\theta)^T(Y-X\theta) \\
	        &=& argmin_\theta (\theta^TX^TX\theta-2\theta^TX^TY+Y^TY) \\
	        &=& argmin_\theta (\theta^TX^TX\theta-2\theta^TX^TY)
\end{matrix}$$

- 미분을 통해 극점을 찾는 방식으로 최적화시킬 것이다.

$$\nabla_\theta(\theta^TX^TX\theta-2\theta^TX^TY)=0$$

$$2X^TX\theta-2X^TY=0$$

$$\theta=(X^TX)^{-1}X^TY$$

- $X, Y$ 모두 아는 값이므로 $\theta$를 구할 수 있다.

- 아래 그림은 feature를 하나만 사용하여 예측을 해본 것이다.

![](https://user-images.githubusercontent.com/26649034/88475629-b814a600-cf6c-11ea-8365-2b819a6c3bfb.png)

### Non-Linearity

- Linear Regression은 선형이라는 한계 때문에 표현할 수 없는 부분이 있다.

- $x$값에 non linearity를 부여해 조금 더 표현력이 높은 모델을 만들 수도 있다.

- $$h:\hat{f}(x;\theta)=\sum_{i=0}^n\sum_{j=1}^m\theta_{i,j}\Phi_j(x_i)$$

 - 위 식에서는 $\Phi$라는 non-linear function을 사용해 $x_i$를 변형시킨다. $\Phi$로 $x^2, x^3, x^4, ...$ 등을 사용할 수 있다.

![](https://user-images.githubusercontent.com/26649034/88475627-b4811f00-cf6c-11ea-80b4-4fbfacf068c6.png)

- 위 그림은 $x^2, x^3, ..., x^9$까지 포함하여 나타낸 것이다.

- 주어진 데이터를 더 잘 표현한 것으로 볼 수도 있으나, Decision Tree에서 주어진 데이터를 잘 표현하기 위해 노드를 늘리는 것이 오버피팅 문제를 일으키듯이, 무작정 non-linearity를 부여하는 것도 오버피팅 문제를 일으킬 수 있다. 