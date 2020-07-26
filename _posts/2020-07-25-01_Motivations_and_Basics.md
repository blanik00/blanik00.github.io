---
title: '01 Motivations and Basics'
date: 2020-07-25
permalink: /posts/2020/07/25/01_Motivations_and_Basics
category:
  - posts
---


<iframe src="https://www.youtube.com/embed/3AwO0O6hWBI"> </iframe>


# Thumbtack Question
- 당신은 백만장자에게 고용되었다. 백만장자는 압정을 던져 앞면이 나오는가 뒷면이 나오는가를 맞추는 도박을 하려고 하는데, 이것을 해도 손해는 보지 않을지 고민이 되어 당신을 고용하였다. 백만장자를 위해 **압정 던지기 게임**과 그와 관련된 **확률 이론**을 공부해보자.

-  압정 던지기 게임에서 이기기 위해서는 앞면, 뒷면이 나올 확률을 정확하게 알아야 한다.  

- 압정은 앞, 뒤가 다르게 생겨 각각이 나올 확률이 p, 1-p이다.  p=0.5가 아니라는 점에서 동전 던지기 게임과는 다르다.

## 1. Tossing

- 이러한 문제를 해결하기 위해 가장 쉽게 떠올릴 수 있는 방법은 압정을 던져보는 것이다.

- 당신은 백만장자 앞에서 압정을 다섯 번 던졌다. 그 결과 앞면이 세 번 나왔고, 뒷면이 두 번 나왔다.(HHTHT)

- 실험의 결과에 따르면, 앞면이 나올 확률은 0.6이고, 뒷면이 나올 확률은 0.4이다.

- 결과는 다음 두 이론을 바탕으로 하고 있다.
	1.  [Binomial Distribution](https://blanik00.github.io/posts/2020/05/21/bern_bin)
	2. [MLE(Maximum Likelihood Estimation)](https://blanik00.github.io/posts/2020/05/03/maximum_likelihood_estimation)
	
	우리는 압정 던지기 게임의 결과가 Binomial Distribution을 따른다는 것을 가정한다. 이 때, 압정의 특이한 모양에 의해 형성된 앞면이 나올 확률을 $\theta$라고 하자.

	$$P(HHTHT)=\theta\theta(1-\theta)\theta(1-\theta)=\theta^3(1-\theta)^2$$
	
	이를 일반화 시켜 확률 $\theta$가 주어졌을 때 데이터 $D$가 나올 확률은 다음과 같다.
	
	$$P(D|\theta)=\theta^{a_H}(1-\theta)^{a_T}$$

	- $a_H$ : $D$에서 앞면이 나온 횟수
	- $a_T$ : $D$에서 뒷면이 나온 횟수

	우리는 앞서 압정 던지기 게임의 결과가 Binomial Distribution을 따른다는 것을 가정했다. 그렇다면 어떻게 하면 이 가정을 더 강화할 수 있을까?

## 2. MLE

우리는 가정을 강화하기 위해  데이터의 분포를 가장 잘 설명하는 $\theta$를 찾는 것에 집중할 것이다. 

이 목적을 위해 고려할 수 있는 방법이 MLE이다. 이 방법은 관측된 데이터가 등장할 확률을 최대화하는 $\hat{\theta}$를 찾는다. 수식으로 표현하면 다음과 같다.

$$\begin{matrix}
\hat{\theta} &=& argmax_{\theta}P(D|\theta) \\
       &=& argmax_{\theta}\theta^{a_H}(1-\theta)^{a_T} \\
       &=& argmax_{\theta}ln\{\theta^{a_H}(1-\theta)^{a_T}\} \\
       &=& argmax_{\theta}\{a_Hln\theta+a_Tln(1-\theta)\} \\
\end{matrix}$$

$${d\over d\theta}\{a_Hln\theta+a_Tln(1-\theta)\}=0$$

$${a_H\over\theta}-{a_T\over 1-\theta}=0$$

$$\theta={a_H\over a_T+a_H}$$

$$\hat{\theta}={a_H\over a_T+a_H}$$
	
## 3. More Tossing
- 당신이 이 내용을 백만장자에게 설명하는 동안 백만장자는 압정을 50번 더 던졌다. 그 결과 앞면이 30번, 뒷면이 20번 나왔다. 호기심이 많은 백만장자는 5번을 던져서 3번 앞면이 나온 것과 50번을 던져서 30번 앞면이 나온 것이 동일한 것인지 물어봤다.

- 우리가 MLE를 통해서 한 것은 결국 모수인 $\theta$를 추정하는 $\hat{\theta}$을 구한 것이다. 추정값은 어쩔 수 없이 오차를 가지고 있는데, 여러 번 실험을 해보는 백만장자의 시도로 추정의 오차를 줄일 수 있다.

- 오차를 측정하는 방법으로 Hoeffding's Inequaility를 사용한다.

- Hoeffding's Inequaility
	- $P(\|\hat{\theta}-\theta^\* \|\ge \epsilon)\le2e^{-2N\epsilon^2}$

	- 즉, 추정값과 실제값의 차이가 $\epsilon$보다 작을 확률은 $2e^{-2N\epsilon^2}$보다 작거나 같다. 

	- 수식에 영향을 미치는 변수는 두 가지가 있다.
		
		1. $\epsilon$ : error bound인 $\epsilon$이 커지면 우변의 값이 작아져 추정값과 실제값의 차이가 error bound보다 커질 확률은 적어진다. 당연한 얘기다.

		2. $N$ : 마찬가지로 시행 횟수인 $N$이 커지면 우변의 값이 작아져 추정값과 실제값의 차이가 error bound보다 커질 확률은 적어진다.

	- 이 원리를 이용하면 error bound를 0.1로 잡았을 때, 몇 번의 시행을 해야 에러가 발생할 확률이 0.01% 이하로 떨어지는가? 등과 같은 계산을 할 수 있다. (error bound를 0.1로 고정시키고 우변이 0.01 이하로 떨어질 때 까지 $N$을 늘리면 된다)

	- 이러한 것을 PAC(Probably Approximate Correct) learning이라고 한다.

- 그렇기 때문에 시행 횟수인 $N$을 늘린 백만장자의 시도는 에러가 발생할 확률을 줄여준다.

<iframe src="https://www.youtube.com/embed/LbYCQxKAv2E"> </iframe>

## 4. Bayes
- Bayes라는 사람이 찾아왔다.

- 그는 지금까지의 실험을 보며 앞면이 나올 확률이 정말로 60%일 것인지 의심해봐야 한다고 주장했다. 

- 그러면서 앞면과 뒷면이 나올 확률이 동등하게 0.5가 아닐까하며 백만장자를 설득했다.

- 백만장자는 처음엔 0.5일 것이라고 생각은 했었는데, 실험을 해보니 그게 아니었다고 말한다.

- 베이즈는 때를 놓치지 않고 백만장자의 사전 정보(앞뒤 확률이 같을 것이라는 것)를 파라미터를 추정하는 과정에 반영시킬 수 있다고 말한다.

- 베이즈는 다음과 같은 공식을 제안했다.

$$P(\theta|D)={P(D|\theta)P(\theta) \over P(D)}$$

- 다음과 같이  표현할 수도 있다.

$$Posterior={Likelihood \times Prior\;Knowledge \over Normalizing\;Constant}$$

- 앞과 뒤가 나올 확률이 나올 확률이 0.5로 동일할 것이라는 백만장자의 생각은 Prior Knowledge에 들어간다.

- $P(D\|\theta)=\theta^{a_H}(1-\theta)^{a_T}$로 이미 구해두었으며, Prior Knowledge는 사전 지식이므로 $P(\theta\|D)$를 바로 계산할 수 있다.

- 사실 $P(D)$는 이미 주어진 사실이므로, 이것이 발생할 확률은 정해져 있다. 즉, $\theta$에 영향을 받지 않는다. 그래서 보통 $P(D)$를 빼고 다음과 같은 식을 계산한다.

$$P(D)\propto P(D|\theta)P(\theta)$$

$$P(D|\theta)=\theta^{a_H}(1-\theta)^{a_T}$$

$$P(\theta)=???$$

- 그렇다면 $P(\theta)$는 어떻게 표현할 수 있을까? 
	- $P(D\|\theta)$는 Binomial Distribution을 따른다고 가정하고 계산했다.

	- 이처럼 $P(\theta)$도 특정 분포를 따른다고 가정하고 계산해야 한다.

	- 여러가지 방법이 있는데 베이즈는 베타 분포를 제안했다.

	- 베타 분포는 특정 범위에 있는 값을 0과 1 사이의 실수로 만들어 주기 때문에 확률로 사용하기 좋다.

	- 베타 분포에 따르면 $P(\theta)$는 다음과 같이 표현할 수 있다.

$$P(\theta)={\theta^{\alpha-1}(1-\theta)^{\beta-1} \over B(\alpha, \beta)}$$

$$B(\alpha, \beta)={\Gamma(\alpha)\Gamma(\beta)\over \Gamma(\alpha+\beta)}$$

$$\Gamma(\alpha)=(\alpha-1)!$$

$$P(D)\propto P(D|\theta)P(\theta)\propto \theta^{a_H}(1-\theta)^{a_T}\theta^{\alpha-1}(1-\theta)^{\beta-1}$$

($P(\theta\|D)={P(D\|\theta)P(\theta) \over P(D)}$의 $P(D)$, $P(\theta)={\theta^{\alpha-1}(1-\theta)^{\beta-1} \over B(\alpha, \beta)}$의 $B(\alpha, \beta)$는 $\theta$에 영향을 받는 요소가 아니라서 제거하였다.)

$$=\theta^{a_T\alpha-1}(1-\theta)^{a_T+\beta-1}$$

- MLE에서는 $\hat{\theta}=argmax_{\theta}P(D\|\theta)$를 찾는 것이 문제였다.

- 이번에 할 것은 MAP이며, $\hat{\theta}=argmax_{\theta}P(\theta\|D)$를 구하는 문제이다.

- 앞에서 $P(D)\propto \theta^{a_H}(1-\theta)^{a_T}\theta^{\alpha-1}(1-\theta)^{\beta-1}$인 것을 배웠다.

- MLE에서 최적값을 구했던 것과 같은 방법으로 구해보면 $\hat{\theta}$은 다음과 같다.

$$\hat{\theta}={a_H+\alpha-1\over a_H+\alpha+a_T+\beta-2}$$

- 문제를 바라보는 관점에서 차이가 있는 것이다.

## MLE vs MAP
- 그렇다면 어떤 방법이 더 좋은 것일까?

- 사실 두 방법은 시행 횟수가 아주 많을 때 같아진다. MAP에 있는 $\alpha$, $\beta$는 $a_T$, $a_H$가 커짐에 따라 그 영향력이 작아지기 때문이다.

- 반대로 시행 횟수가 적은 상황에서는 사전 정보가 중요한 영향을 미치게 된다. 사전 정보인 $\alpha$, $\beta$을 어떻게 설정하느냐에 따라 MAP의 성능이 MLE보다 좋을 수도 있고, 나쁠 수도 있다.