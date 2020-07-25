---
title: 'Random Variables'
date: 2020-05-17
permalink: /posts/2020/05/17/random_variables
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/GqDy0sInGJ0"> </iframe>  

## Random Variables
- 표본 공간의 원소들(실험의 결과들)을 입력으로 받아 실수로 바꿔주는 함수
- $Real \;Number=f(Elements \;of \;the \;sample \;space)$

### Random Variables - Coin Example  
- tossing 3 coins
- Sample Space = {(HHH),(HHT),(HTH),(THH),(HTT),(THT),(TTH),(TTT)}
- Random Variable Y : Number of heads
- Y={0,1,2,3}

![1](https://user-images.githubusercontent.com/26649034/82135062-78796180-9839-11ea-8b4b-12e0951ffe58.png)

우리가 일반적으로 사용하는 데이터는 다음과 같은 형태를 가지고 있다. 

![2](https://user-images.githubusercontent.com/26649034/82135114-d4dc8100-9839-11ea-9fda-00abf4f23c29.png)

이것을 확률 변수의 개념을 적용하면 "샘플들이 $X_1$이라는 확률 변수를 만나면 $x_{11},x_{21},...x_{n1}$이라는 실수로 바뀌고, $X_p$이라는 확률 변수를 만나면 $x_{1p},x_{2p},...x_{np}$이라는 실수로 바뀐다."고 볼 수 있다.

## Discrete / Continous Random Variables
- Random Variable의 결과는 실수인데, 실수는 두 가지 종류가 있다.
- Discrete(이산형) : 셀 수 있다(동전을 세 개 던졌을 때 앞면이 나온 경우의 수, 코로나 바이러스 확진자 수)
- Continous(연속형) : 셀 수 없다(시간과 돈이 대표적인 연속형 데이터. 서울 주민들의 평균 연봉)

## Probability Function
- 확률 변수로부터 나온 실수를 입력으로 받아 확률로 바꿔주는 함수
- $p=f(Real \; Number)$
- Random Variables의 결과가 Discrete, Continous 두 가지가 있다고 했다. 이것인 즉슨 Probability Function의 입력도 Discrete, Continous 두 가지가 있다는 것이다. 이 때문에 Probability Function은 입력의 종류에 따라 두 가지로 나뉘게 된다.
- 입력이 Discrete한 경우 : Probability Mass Function(PMF, 확률질량함수)
- 입력이 Continous한 경우 : Probability Density Function(PDF, 확률밀도함수)

## Probability Mass Function
- Discrete Random Variable $X$을 입력으로 받음
- $x$를 $X$의 원소라고 하자.
- 이산형 실수인 $x$에 대해 확률이 부여됨
- $p(x)=P[X=x]$

![3](https://user-images.githubusercontent.com/26649034/82135065-7adbbb80-9839-11ea-9f09-7649b020585a.png)

- X축에 있는 것은 $X$라는 확률 변수가 가질 수 있는 이산형 값들이 되며, 거기에 해당하는 확률이며, 이를 막대 그래프로 표현한 것이다.
- $0\le p(x) \le 1$   for all $x$
- $\sum_xp(x)=1$

## Probability Mass Function - Coin Example
- tossing 2 coins
- Sample Space S={(HH), (HT), (TH), (TT)}
- Random Variable X = Number of heads
- Possible values of X = {0, 1, 2}
- What is probability mass function?
- 1. $P(X=0)=1/4$
	2. $P(X=1)=1/2$
	3. $P(X=2)=1/4$

## Probability Mass Function - Accident Example
- 한 공장에서는 매년 낙상 사고가 일어난다.
- Random Variable X : 일 년 동안 일어나는 낙상 사고의 수
- $X=0,1,2,3,...$
- $P(X=x)={1\over 2^{x+1}}$

이 때, $P(X=x)$는 Probability Mass Function이라고 할 수 있는가?
1. 확률 변수 X는 셀 수 있으므로 이산형이 맞다.
2. $0\le p(x)\le 1$  
$P(X=0)=1/2$  
$P(X=1)=1/2^2$  
$P(X=2)=1/2^3$  
...이므로 모든 확률은 0과 1 사이에 있다.
3. $\sum_{x}P(X=x)=1$  
$1/2+1/2^2+1/2^3+...={1/2 \over 1-{1/2}}=1$

모든 조건을 만족하므로 Probability Mass Function이라고 할 수 있다.

## Probability Mass Function - Coin Example 2
- 동전을 던져 앞면이 나오거나 던진 횟수가 $n$이 되면 동전 던지기를 멈춘다고 하자.
- $P(head)=p$
- Random Variable $X$ : 동전을 던진 횟수

1. $X$는 Random Variable이 될 수 있는가?  
X={1,2,3,...n}  
x=1 => 동전 던지기 한 번에 앞 면이 나옴  
x=2 => 동전 던지기 첫 번째에는 뒷 면이 나오고, 두 번째에는 앞 면이 나옴.  
x=3 => 동전 던지기 두 번째까지 뒷 면이 나오고, 세 번째에는 앞 면이 나옴.  
x=n => 동전 던지기 (n-1)까지 뒷 면이 나오고, n 번째에는 앞 면이든 상관없다.(어차피 멈춰야 함)  
원소들을 실수로 바꿨으므로 확률변수라고 할 수 있다.
2. X의 원소를 확률에 대응시켜라  
$P(X=1)=p(H)=p$  
$P(X=2)=p(TH)=(1-p)p$  
$P(X=3)=p(TTH)=(1-p)^2p$  
$P(X=n-1)=(1-p)^{n-2}p$  
$P(X=n)=(1-p)^{n-1}p+(1-p)^{n-1}(1-p)$   이 부분 주의해야 함  
3. $\sum_{i=1}^{n}P(X=i)=1$을 만족하는지 확인하라  
$\sum_{i=1}^{n-1}P(X=i)+P(X=n)$  
$=\sum_{i=1}^{n-1}(1-p)^{i-1}p+(1-p)^{n-1}$  
$=p{1-(1-p)^{n-1}\over 1-(1-p)}+(1-p)^{n-1}$  
$=1$  

## Probability Mass Function with Infinitely Many Possible Values
PMF : $p(X=i)=c\lambda^i/i!, \;\; i=0,1,2,..., \;\; \lambda는 양수$  
1. $c$를 구하라.  
$\sum_{i=1}^{\infty}P(X=i)=c\sum_{i=1}^{\infty}{\lambda^i\over i!}=c(1+\lambda+{\lambda^2\over 2!}+{\lambda^3\over 3!}+...)=ce^\lambda=1$  
$c=e^{-\lambda}$  
2. $P(X=0)$  
$P(X=0)=e^{-\lambda}\lambda^0/0!=e^{-\lambda}$  
3. $P(X>2)$  
$=1-P(X\le 2)$  
$=1-(P(X=0)+P(X=1)+P(X=2))$  
$=e^{-\lambda}+e^{-\lambda}\lambda^1/1!+e^{-\lambda}\lambda^2/2!$  

