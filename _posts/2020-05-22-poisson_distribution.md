---
title: 'Poisson Distribution'
date: 2020-05-22
permalink: /posts/2020/05/22/poisson_distribution
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/HJZ5Ev_p8Uo"> </iframe>  

## 복습
**Sample Space(표본 공간)** : 실험으로 나오는 모든 결과를 담고 있는 집합

**Random Variable(확률 변수)** : sample space의 원소들을 숫자로 바꿔주는 함수

**Probability Function(확률 함수)** : Random Variable을 확률로 변환하는 함수

**Probability Distribution(확률 분포)** : Probability Function으로부터 나온 확률들의 전반적인 패턴

확률 분포는 확률 함수의 input에 따라 두 가지로 나뉜다.

| 확률 함수의 input | 확률 함수 | 확률 분포 |
|:--:|:--:|:--:|:--:|
| discrete | PMF(확률질량함수) | Discrete Probability Distribution(이산형 확률분포) |
| continous | PDF(확률밀도함수) | Continous Probability Distribution(연속형 확률분포) |

확률질량함수에서 나온 확률 분포. 즉, 이산형 확률분포는 다음과 같다.
1. Bernoulli Distribution
2. Binomial Distribution
3. Poisson Distribution
4. Geometric Distribution
5. Negative Binomial Distribution
6. Hypergeometric Distribution

지난 시간에 Bernoulli, Binomial Distribution에 대해 배웠으며, **이번에는 Poisson Distribution에 대해 배운다.** 또한 다음 시간에는 나머지 이산형 확률분포에 대해 배운다.

확률밀도함수에서 나온 확률 분포. 즉, 연속형 확률분포는 다음과 같다.
1. Uniform Distribution
2. Normal Distribution
3. Exponential Distribution
4. Gamma Distribution
5. Beta Distribution
6. Chi-square Distribution

연속형 확률 분포는 나중에 다룬다.

---

지난 시간에 배운 Bernoulli, Binomial Distribution을 복습하자.

### Bernoulli Distribution
> Random Variable X : 0 혹은 1만을 가지는 단순한 확률 변수

0과 1을 확률로 변환하려면 확률 함수(Probability Function)가 필요하다. 여기서 확률 함수의 input은 이산형이므로 Bernoulli Distribution은 이산형 확률 분포가 된다.

확률 함수는 다음과 같다.

$$f_X(x;p)=p^x(1-p)^{1-x}, x=0 \; or \; 1$$

즉, Bernoulli Distribution은 Bernoulli 확률 함수로부터 생성되는 확률들의 분포를 의미한다.

### Binomial Distribution
Binomial Distribution은 Bernoulli Distribution으로부터 나온다.
> Random Variable X : Bernoulli trials를 $n$번 했을 때, 성공 횟수
parameter는 $n$, $p$이다.(parameter는 확률 분포의 모양의 결정할 때 중요한 값)

성공 횟수를 확률로 변환하려면 확률 함수(Probability Function)가 필요하다. 여기서 확률 함수의 input은 이산형이므로 Binomial Distribution은 이산형 확률 분포가 된다.

확률 함수는 다음과 같다.

$$p(x)={n\choose x}p^x(1-p)^{1-x}\quad for \;x=0,1,2,...,n$$

즉, Binomial Distribution은 Binomial 확률 함수로부터 생성되는 확률들의 분포를 의미한다.

## Poisson Distribution
> Random Variable X : 단위 시간 혹은 단위 공간 안에 특정 사건이 몇 번 발생할 것인가

한 번도 발생 안할 수도 있고(0), 1번 발생할 수도 있고, 2번 발생할 수도 있다. 즉, discrete하다.

발생 횟수를 확률로 변환하려면 확률 함수(Probability Function)가 필요하다. 여기서 확률 함수의 input은 이산형이므로 Poisson Distribution은 이산형 확률 분포가 된다.

확률 함수는 다음과 같다.

$$P(X=i)={e^{-\lambda}\lambda^i\over i!}, \quad i=0,1,2,...$$

이것이 확률 함수가 되기 위해서는 더해서 1이 되어야 한다.

$$\sum_{i=0}^{\infty}P(X=i)=e^{-\lambda}\sum_{i=0}^{\infty}{\lambda^i\over i!}=e^{-\lambda}e^{\lambda}=1\; (\sum_{i=0}^{\infty}{\lambda^i\over i!}=e^{\lambda} \; by \; taylor \; series)$$

parameter는 $\lambda$이다.

## Poisson Approximation to Binomial
Binomial Distribution에서 parameter는 $n$과 $p$이다. $n$이 굉장히 크고, $p$가 굉장히 작을 때, Binomial Distribution을 parameter $\lambda=np$인 Poisson Distribution으로 근사할 수 있다. 

즉, $Binomial(i;n,p)\approx Poisson(i;\lambda), \quad \lambda = np, p={\lambda \over n}$

$P(X=i)={n!\over(n-i)!i!}p^i(1-p)^{n-i}\approx e^{-\lambda} {\lambda^i\over i!}$
$={n!\over(n-i)!i!}({\lambda \over n})^i(1-{\lambda \over n})^{n-i}$
$={n(n-1)...(n-i+1)\over n^i}{\lambda^i\over i!}{(1-{\lambda \over n})^{n}\over (1-{\lambda \over n})^{i}}$

마지막 식을 세 부분으로 나누어 푼다. $n$이 아주 크다고 했으므로 $n$을 무한대로 보내보자.

1. ${n(n-1)...(n-i+1)\over n^i}$  
$\lim_{n \to \infty}{n(n-1)...(n-i+1)\over n^i}=1$
2. $(1-{\lambda \over n})^{i}$  
$\lim_{n \to \infty}(1-{\lambda \over n})^{i}=1$
3. $(1-{\lambda \over n})^{n}$  
$\lim_{n \to \infty}(1-{\lambda \over n})^{n}=\lim_{n \to \infty}((1-{\lambda \over n})^{n\over \lambda})^{\lambda}=\lim_{n \to \infty}(e^{-1})^{\lambda}=\lim_{n \to \infty}(e^{-\lambda})$

결과를 대입해보면 ${e^{-\lambda}\lambda^i\over i!}$가 나오며, 이는 포아송 분포의 확률 함수와 같다.

## Example of Poisson Random Variable
Poisson 분포는 단위 시간 혹은 단위 공간 내에 특정 사건이 몇 번 발생했는지를 나타낸다고 했는데, 조금 더 추가하자면 특정 사건은 자주 발생하는 것이 아니라 드물게 발생해야 포아송 분포로 모델링하기 좋다.
- 어떤 마을에서 100세 이상까지 사는 사람의 수
- 책의 한 페이지에서 오타의 개수
- 하룻동안 잘못 전화를 건 횟수

## Mean and Variance of Poisson Distribution
> $E[X]=V[X]=\lambda$

$E[X]=\sum_{i=0}^{\infty}{ie^{-\lambda}\lambda^{i}\over i!}$  
$=\lambda\sum_{i=1}^{\infty}{e^{-\lambda}\lambda^{i-1}\over (i-1)!}$  
$Let \;\;k=i-1$  
$=\lambda\sum_{k=0}^{\infty}{e^{-\lambda}\lambda^{k}\over k!}$  
$=\lambda e^{-\lambda}\sum_{k=0}^{\infty}{\lambda^{k}\over k!}$  
$=\lambda e^{-\lambda}e^{\lambda}$  
$=\lambda$  

아래도 비슷하게 풀 수 있다.  
$E[X^2]=\lambda(\lambda+1)$  
$V[X]=E[X^2]-\{E[X]\}^2=\lambda^2 + \lambda - \lambda^2=\lambda$  

## Poisson Distribution - Quality Example
유리 제조사의 품질 관리자가 유리에 결함이 있는지 검사하고 있다. 유리에 있는 결함의 수를 $\lambda=0.5$인 Poisson Distribution으로  가정했을 때, 유리에 결함이 하나도 없을 확률은 얼마인가?

> Random Variable X : Number of imperfections in a glass

우리는 확률을 구해야 하니 확률 함수를 이용해야 한다. 즉, 이 문제는 $P(X=0)$을 구하고자 하는 것이다.

$P(X=0)={e^{-0.5}0.5^0\over 0!}=e^{-0.5}=0.607$

## Poisson Distribution - Radioactive Particle Example
방사선 입자는 ms(millisecond) 동안 4개가 나온다. 2.5ms 동안 나오는 방사선 입자의 개수가 15일 확률을 구하라.

> Random Variable X : Number of Radioactive Particle over 2.5ms period

우리는 확률을 구해야 하니 확률 함수를 이용해야 한다. 즉, 이 문제는 $P(X=15)$을 구하고자 하는 것이다.

우리가 알고 있는 것은 ms 동안 4개의 입자가 나온다는 것이다. 이를 2.5ms로 바꾸면 10개의 입자가 나온다는 것이 된다. 즉, $\lambda=\lambda't=4\times 2.5=10$이다.(보통 Poisson Distribution 문제를 풀 때 단위 시간을 1로 주는데 이 문제는 1이 아니라는 점을 주의해야 한다)

$P(X=15)=f(15;10)={e^{-10}10^{15}\over 15!}=0.0348$