---
title: '최대우도추정(MLE, Maximum Likelihood Estimation)'
date: 2020-05-03
permalink: /posts/2020/05/03/maximum_likelihood_estimation
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/XepXtl9YKwc"> </iframe>  

최대우도추정 : 데이터를 가장 잘 설명하는 모델의 모수($\theta$)를 찾는 것  

관측된 데이터 $X_1=x_1$, $X_2=x_2$, ..., $X_n=x_n$이 있다고 할 때 $\theta$의 가능도는 다음과 같다.  

$L(\theta)=P(x_1, x_2, ..., x_n\|\theta)$  

(참고로 여기서 나오는 $P(x_1, x_2, ..., x_n\|\theta)$에서 $\|$는 조건부 확률을 나타내는 기호가 아니다. $\|$ 뒤에 있는 기호들이 모델의 모수라는 것을 강조하기 위해 사용되는 기호에 불과하다. $P(x_1, x_2, ..., x_n;\theta)$으로 표현하기도 한다.)  

이 때 확률변수가 iid(independent and identically distributed)라면 가능도는 다음과 같이 표현할 수도 있다.  

$L(\theta)=\prod_{i=1}^{n}P(x_i\|\theta)$  

가능도를 최대로 만드는 $\theta_{MLE}$는 다음과 같다.  

$\theta_{MLE}=argmax_{\theta}\prod_{i=1}^nP(x_i\|\theta)$  

이 때 확률값은 1보다 작기 때문에 계속 곱하면 그 값이 지나치게 작아져 언더플로우(underflow) 문제가 발생하므로 로그를 취한다. 이 때 로그를 취하더라도 가능도를 최대로 만드는 $\theta$가 전과 동일하다는 보장이 있어야 하는데, 로그는 단조증가(monotonically increasing)한다는 성질이 있기 때문에 로그를 취하더라도 가능도를 최대로 만드는 $\theta$는 변하지 않는다.  

$\theta_{MLE}=argmax_{\theta}\sum_{i=1}^nlogP(x_i\|\theta)$  

## 예시
<iframe src="https://www.youtube.com/embed/Dn6b9fCIUpM"> </iframe>  

## 출처
[StatQuest: Maximum Likelihood, clearly explained!!!](https://www.youtube.com/watch?v=XepXtl9YKwc)  
[Maximum Likelihood For the Normal Distribution, step-by-step!](https://www.youtube.com/watch?v=Dn6b9fCIUpM)  
[최대우도추정(Maximum Likelihood Estimation)](https://ratsgo.github.io/statistics/2017/09/23/MLE/)  
