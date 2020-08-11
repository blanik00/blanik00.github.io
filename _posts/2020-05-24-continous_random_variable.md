---
title: 'Continous Random Variable, Distrubution'
date: 2020-05-24
permalink: /posts/2020/05/24/continous_random_variable
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/d58jRlAcUkg"> </iframe>  

## Continous Random Variable
- 이산형 확률 변수와 크게 다르지 않음. 차이점은 아래와 같다.
	- 모든 summation($\sum$)은 integral($\int$)이 된다.
	- 확률 변수가 가질 수 있는 값이 연속형이다.

![1](https://user-images.githubusercontent.com/26649034/82829633-b12ad200-9eee-11ea-917e-19e9100ee16b.png)

- 연속 확률 변수의 예
	1. 대한민국 국민들의 소득
	2. 대학생들의 키
	3. 다우존스 지수

## Probability Density Function
- 입력이 연속형 실수이며, 출력이 [0, 1]인  확률 함수
- 연속형 확률 함수 $X$가 가질 수 있는 값들을 $x$라고 한다.
- 이 PDF의 분포를 Continous Probability Distribution이라고 한다.

조금 더 자세히 알아보자.

- 이산형 확률 변수의 경우, PMF는 다음과 같았다.  
$$P(a\le X\le b)=\sum_{a\le x \le b}P(X=x)$$
- 연속형 확률 변수의 경우, 확률 변수 $X$의 PDF는 다음 수식의 $f(x)$이다.
$$P(a\le X\le b)=\int_{a}^{b}f(x)\;dx$$
- 즉, 연속형 확률 변수에서 확률은 특정 구간의 PDF 아래 부분의 면적이다.

## Properties of PDF
1. $f(x)\ge 0, \;\;\forall x$
2. $\int_{-\infty}^{\infty}f(x)\; dx=1$
3. $P[X=a]P[a\le X \le a]=\int_{a}^{a}f(x)\; dx=0$
	- 연속형 확률 함수에서 특정 값에 대한 확률은 0이다.
4. $P[a-{\epsilon\over 2}\le X\le a+{\epsilon\over 2}]=\int_{a-{\epsilon\over 2}}^{a+{\epsilon\over 2}}f(x)\; dx \approx \epsilon f(a)$
	- $\epsilon$은 아주 작은 실수
	- $f(a)$는 확률 변수 $X$가 $a$ 근처에서 얼마나 발생하는지를 나타내는 측도
5. 다음 확률들은 모두 동일하다. 특정 값에서의 확률은 0이기 때문에 연속형 확률 변수의 확률을 구할 때는 등호의 포함 여부는 영향을 미치지 못한다.
	- $P(a\le X\le b)$
	- $P(a< X\le b)$
	- $P(a\le X< b)$
	- $P(a< X< b)$

## Example of PDF
컴퓨터가 고장나기 까지의 시간은 연속형 확률 변수 $X$를 따른다고 한다. $X$의 PDF는 다음과 같이 정의된다.

$$f(x)=
\begin{cases}
\lambda e^{-x\over 100} \qquad x\ge 0 \\
0 \qquad\;\;\;\;\;\; x<0
\end{cases}$$

1.  $\lambda$는 무엇인가?
이 문제는 PDF가 가진 성질을 활용해 풀어야 한다.(적분하면 1)  
$1=\int_{0}^{\infty}f(x)\;dx$  
$=\lambda[-100e^{-x/100}]_{0}^{\infty}$  (지수함수의 적분)  
$=-100\lambda(0-1)$  
$=100\lambda$  

$\therefore \lambda=1/100$  
2. 컴퓨터가 50시간에서 150시간 정도 고장 없이 동작할 확률은 얼마인가?
$P(50\le X\le 150)$  
$=\int_{50}^{150}f(x)\;dx$  
$=1/100[-100e^{-x/100}]^{150}_{150}$  
$=-e^{-150/100}-(-e^{-50/100})$  
$=-e^{-3/2}-(-e^{-1/2})$  
$\approx 0.384$  

## Cumulative Density Function(누적 분포 함수)
- PDF는 $f(x)$였고, 이번에 배울 CDF는 $F(x)$이다.
- 확률 변수가 특정한 값 $x$보다 작을 확률을 뜻한다.

$$F(x)=P(X\le x)=\int_{-\infty}^{x}f(t)\; dt$$

- 즉, PDF를 적분한 것이 CDF이고, CDF를 적분한 것이 PDF이다.

## Probabilities of CDF
1. $0\le F(x)\le 1, \;\; \forall x$
2. if $b\ge a$, then $F(b)\ge F(a)$이다. 이런 함수를 단조 증가 함수(monotonic increasing function)라고 한다.
3. $\bigstar \;\;F(b)-F(a)=P[a\le X\le b]\;\;\;\;\;$    중요!
$\begin{matrix}
P[a\le X\le b] 
&=& \int_{b}^{a}f(x)\;dx \\\
&=& \int_{-\infty}^{b}f(x)\;dx - \int_{-\infty}^{a}f(x)\;dx \\\
&=& F(b)-F(a) \\\
\end{matrix}$

## Example of CDF
> RV X : 라디오 튜브의 수명

$$f_X(x)=
\begin{cases}
{100 \over x^2} \qquad x\ge 100 \\
0 \qquad\;\;\;\;\;\; else
\end{cases}$$

$F(150)=?$

### 풀이 1 

$\begin{matrix}
F(150)
&=& P[X<10] \\\
&=& \int_{-\infty}^{150}f(x)\;dx \\\
&=& \int_{100}^{150}f(x)\;dx \\\
&=& 100\int_{100}^{150}x^{-2}\;dx \\\
&=& [-100/x]_{100}^{150} \\\
&=& -100/150+100/100 \\\
&=& 1/3 \\\
\end{matrix}$

### 풀이 2
$\begin{matrix}
F(x)
&=& P[X < x] \\\
&=& \int_{100}^{x}f(x)\;dx \\\
&=& [-100/x]_{100}^{x} \\\
&=& -100/x+1 \\\
\end{matrix}$

$\therefore F(150)=1/3$

## Expectation of Continous Random Variable
- $E[X]=\int_{-\infty}^{\infty} xf(x)\; dx$
- 확률 변수에 대한 함수의 기대값

$E[g(x)] = \int_{-\infty}^{\infty} g(x) f(x) \; dx$


### 예제
길이가 1인 막대기를 두 개로 잘랐다($U$를 기준으로, $U$는 uniformly distributed over (0,1)). 또한 0과 1 사이에는 포인트 $p$가 있다고 하자. 포인트 $p$가 포함된 막대의 길이의 기대값은 얼마인가?

$$L_{P(U)}=
\begin{cases}
1-u \qquad 0 < U < p \\\
u \qquad\;\;\;\;\;\; 1 > U > p
\end{cases}$$

$\begin{matrix}
E[L_{P(U)}]
&=& \int_{0}^{p}(1-u)\;du + \int_{p}^{1}u\;du \\\
&=& 1/2-p^2+p \\\
\end{matrix}$