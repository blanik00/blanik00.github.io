---
title: 'Naive Bayes Classifier'
date: 2020-07-28
permalink: /posts/2020/07/28/naive_bayes_classifier
category:
  - posts
---


# Optimal Classification

![image](https://user-images.githubusercontent.com/26649034/88505879-a4704a80-d013-11ea-99f7-ccfb65aec413.png)

$X=x_1, x_2, ...$이 주어지고, $x_i$이 $y_1$으로 분류될 확률이 $P(Y=y_1\|X=x_i)$(초록색 선)이고, $y_2$으로 분류될 확률이 $P(Y=y_2\|X=x_i)$(빨간색 선)이다.

$x_i$가 그림의 왼쪽에 위치해 있다고 가정하자. 그렇다면 $P(Y=y_1\|X=x_i)>P(Y=y_2\|X=x_i)$이므로 $x_i$는 $y_1$으로 분류된다.

마찬가지로 $x_i$가 그림의 오른쪽에 위치해 있다고 가정하자. 그렇다면 $P(Y=y_1\|X=x_i)<P(Y=y_2\|X=x_i)$이므로 $x_i$는 $y_2$으로 분류된다.

이처럼 분류를 하기 위해서는 데이터($X$)가 주어졌을 때 target class에 대한 확률을 계산해야 한다.

# Bayes Classifier
bayes classifier는 다음과 같이 정의할 수 있다.

$$f^*=argmin_fP(f(X)\neq Y)$$

즉, 예측치와 관측치가 같지 않을 확률을 최소화하는 $f$를 $f^*$라고 한다.

두 개의 클래스를 분류하는 문제에서는 다음과 같이 표현할 수도 있다.

$$f^*(x)=argmax_{Y=y}P(Y=y|X=x)$$

$x_1$의 클래스가 $y_1$이라고 한다면 위 수식을 통해 $y_1$으로 분류될 확률을 최대화할 수 있다. 즉, $y_2$로 오분류될 확률을 최소화할 수 있다.

# Optimal Classification and Bayes Risk

![image](https://user-images.githubusercontent.com/26649034/88509759-b99da700-d01c-11ea-8249-0a5d434b0f8b.png)

위 그림에는 점선 classifier, 실선 classifier가 있다.

$x_i$에서 점선 classifier의 두 확률값을 더하면 1이 된다. $x_1$이라는 입력값이 들어왔을 때, 이것을 빨간색 혹은 초록색으로 만들어줘야 하기 때문이다. 같은 논리도 $x_i$에서 실선 classifier의 두 확률값을 더해도 1이 된다. classifier가 교차하는 부분(decision boundary)에서의 확률은 0.5이다.

그렇다면 점선 classifier와 실선 classifier 중 어떤 것이 더 나은 classifier일까?

실선이 더 나은 classifier다.

Decision boundary보다 살짝 왼쪽에 있는 $x_j$를 생각해보자. 점선 classifier는 선형이기 때문에 $x_j$가 빨간색인지 초록색인지 명확하게 구분하지 못할 가능성이 있다. 반면 실선 classifier는 점선 classifier보다는 명확하게 둘을 구분한다.

실선이 더 나은 이유를 좀 더 formal하게 설명해 보겠다.

위 그림에서 Decision Boundary의 왼쪽 부분을 보자. 이 부분에서도 분명히 $X$가 빨간 색으로 분류될 확률이 존재한다. 그런데 초록색으로 분류될 확률이 더 높기 때문에 이를 무시하는 것이다. 우리는 이 부분을 **Bayes Risk**라고 한다.

Bayes Risk의 측면에서 봤을 때, 점선 classifier의 risk가 실선 classifier의 risk보다 반달 모양만큼 더 크다. 그러므로 실선 classifier가 더 좋은 classifier다.

우리의 목표는 작은 Bayes Risk를 가지는 classifier를 만드는 것이다.

# Learning the Optimal Classifier
앞서 배웠던 Optimal Classifier는 다음과 같다.

$$f^*(x)=argmax_{Y=y}P(Y=y|X=x)$$

이를 사전확률을 사용할 수 있는 형태로 바꾸면 다음과 같다.

$$f^*(x)=argmax_{Y=y}P(X=x|Y=y)P(Y=y)$$

이 경우 $P(Y=y)$는 경험적으로 알아내거나, 데이터셋에서도 알아낼 수도 있다. 데이터셋 전체에서 $y_1$는 a%, $y_2$는 (1-a)%와 같이 알아낸다.

$P(X=x|Y=y)$도 conditional density를 만들 수 있다. 그런데 이 경우 문제가 되는 것은 X에 여러 개의 Random Variable이 있는 경우이다. 이 때 여러 Random Variable의 상호작용을 고려해 prediction을 해야 하는데, Random Variable의 수가 많아질수록 고려해야 할 상호작용의 수도 많아진다.

이 문제를 해결해주는 것이 Naive Bayes classifier다. Naive Bayes는 Random Variable 간의 상호작용을 무시한다.

# Dataset for Optimal Classifier Learning

![image](https://user-images.githubusercontent.com/26649034/88513569-7c88e300-d023-11ea-9567-516b56a9dcf4.png)

앞서 $f^*(x)=argmax_{Y=y}P(X=x\|Y=y)P(Y=y)$를 구할 때, 고려해야 할 X가 여러개 있을 때의 상황에 대한 문제를 제기를 했었다. 여기서는 그에 부합하는 데이터셋을 소개한다. 

$X=x_1, x_2, x_3, x_4, x_5, x_6$이며, 각각 "Sky", "Temp", "Humid", "Wind", "Water", "Forecst"를 의미한다.

$P(Y=y)$를 구하는 것은 쉽다. 데이터셋을 보면 $P(y=yes)=3/4$, $P(y=yes)=1/4$이다.

반면, P(X=x\|Y=y)를 구하는 것은 까다로운데, 1번 row를 대입해보면 다음과 같아진다.

$$P(x_1=sunny, x_2=warm, x_3=normal, x_4=strong, x_5=warm, x_6=same|y=yes)$$

$x_1, x_2, ...x_d$은 두 개의 값만 가지고, $Y$는 $k$개의 값을 가진다고 가정하면, $(2^d-1)k$개 만큼의 확률값을 알아야 이 문제를 해결할 수 있다.

문제는 고려해야할 확률값의 수가 $X$의 수에 따라 기하급수적으로 증가한다는 점이다.

# Conditional Independence
이 문제를 해결하기 위해 도입한 것이 Conditional Independence다. 다음과 같이 정의할 수 있다.

$$P(x_1,x_2|y)=P(x_1|y)P(x_2|y)$$

이것을 $P(X=< x_1, x_2, ..., x_d >\|Y=y)$에 적용시키면 $\prod_{i}^d P(X=x_i\|Y=y)$으로 바뀐다.

이 때 필요한 확률값의 수는 $(2-1)dk$개이다.

사실 모든 입력 변수들이 서로 독립이라는 조건은 현실적이지 않다. 하지만 모델을 단순화시키고, 연산량을 줄이기 위해 마지못해 하는 것이다.

### Naive Bayes Classifier Function
$$f_{NB}(x)=argmax_{Y=y}P(Y=y)\prod_{1\le i \le d}P(X=x_i|Y=y)$$

# Conditional Independence vs Marginal Independence

![image](https://user-images.githubusercontent.com/26649034/88601092-cf59ad80-d0aa-11ea-908e-b4a37ea62058.png)

Commander가 지시를 내렸는데 Officer A는 그 지시를 잘 듣지 못했다. 그 상황에서 Officer B가 앞으로 전진한다면 Officer A는 지시가 무엇이었는지 잘 알지도 못한 채로 Officer B를 따라 전진할 가능성이 크다. Officer B가 가지고 있는 정보가 Officer A에게 영향을 주는 것이다. 즉, 이 둘은 독립적이지 않다.

반면, Commander의 지시를 명확하게 들었다면 Officer B가 앞으로 가든, 뒤로 가든 상관 없이 들은대로 수행한다. Officer B가 가지고 있는 정보가 Officer A에게 영향을 주지 못하는 것이다. 즉, 이 둘은 독립적이다.

$Y$라는 변수가 Commander이고, $X_1$, $X_2$가 각각 Officer A, B라고 해보자.

$Y$에 대한 관측이 없다면, $X_2$의 정보가 $X_1$에 영향을 미친다. 

$$P(X_1=Go|X_2=Go, Commander=Go)\neq P(X_1=Go, Commander=Go)$$

반면에 $Y$에 대한 관측이 있다면, $X_2$의 정보가 $X_1$에 영향을 미치지 않는다. 

$$P(X_1=Go|X_2=Go, Commander=Go)= P(X_1=Go, Commander=Go)$$

즉, $Y$가 관측되었기 때문에 우리는 Conditional Independence를 정의할 수 있다.

# Problems of Naive Bayes Classifier
1. Naive Assumption
   변수들이 conditionally independence하다는 가정 자체가 현실적이지 않음.
   
2. Incorrect Probability Estimation
   압정을 세 번 던져서 모두 앞면이 나왔다면, 뒤면이 나올 확률은 분명히 존재함에도 $P(뒷면)=0$이 된다(MLE).