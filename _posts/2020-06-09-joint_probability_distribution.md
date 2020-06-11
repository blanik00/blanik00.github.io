---
title: 'Joint Probability Distribution(1)'
date: 2020-06-09
permalink: /posts/2020/06/09/joint_probability_distribution1
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/niob_ZRZeJs"> </iframe>

## Joint Probability Distribution(결합 확률 분포)
확률 변수 $X, Y$는 표본 공간의 원소를 각각 $a, b$로 매핑시킨다. 결합 확률 함수는 $X, Y$를 동시에 고려해 확률로 바꿔준다. 또한 결합 확률 함수를 통해 나온 확률들의 전반적인 패턴을 결합 확률 분포라고 한다.

- 두 개 이상의 변수들을 고려

- 두 개의 변수를 고려할 때, $f_{XY}(x,y)=P[X=x, Y=y]$로 표기한다. X 확률 변수는 x 값을 가지며, Y 확률 변수는 y 값을 가질 때

## Joint Distribution Function(결합 누적 분포 함수)
$F_{XY}(a,b)=P[X\le a, Y\le b]$

이산형일 때는 $\sum$으로, 연속형일 때는 $\int$으로 해결하면 된다.

## Joint Distribution Function - Example 1
결합 밀도 함수(pdf) $f_{XY}(x,y)$를 다음과 같이 정의하자.

$f_{XY}(x,y)=cxy,\;\;\;0 < x < 1,0 < y < 2$로 정의하자.

이 때 $c$의 값을 구하라.

$f_{XY}(x,y)$가 확률 함수가 되기 위해서는 적분해서 1이 되어야 한다. 즉, $\int_{0}^{2}\int_{0}^{1}cxy\;dxdy=1$이 되어야 한다.

$\int_{0}^{2}\int_{0}^{1}cxy\;dxdy=1$
$=c=1$  

## Joint Distribution Function - Example 2
주사위를 던져 두 가지 실험을 한다고 하자.

>RV A : 주사위가 짝수가 나오면 1, 아니면 0
>RV B : 주사위가 소수(prime)면 1, 아니면 0

|  | 1 | 2 | 3 | 4 | 5 | 6 |
|--|--|--|--|--|--|--|
| A | 0 | 1 | 0 | 1 | 0 | 1 |
| B | 0 | 1 | 1 | 0 | 1 | 0 |

이 때, Joint Probability Mass Function을 구하라.

$P_{AB}(0,0)=1/6$  
$P_{AB}(1,0)=2/6$  
$P_{AB}(0,1)=2/6$  
$P_{AB}(1,1)=1/6$  

