---
title: 'Moment Functions'
date: 2020-06-27
permalink: /posts/2020/06/27/moment_functions
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/V6a3MPrv0dM"> </iframe>

## Moment Functions
- 확률 변수 X의 Moment Function(적률 함수)은 다음과 같이 정의된다.

$$E[X^r]=
\begin{cases}
\sum_{x}X^rp(x) & if\;X\;is\;discrete\\
\int_{-\infty}^{\infty}X^rf(x)dx  & if\;X\;is\;continuous
\end{cases}$$

$r$의 값에 따라 적률 함수의 성격이 달라진다.

| moment\(r\) | Moment Function | 전처리한 결과 | 전처리한 결과 |
|:--:|:--:|:--:|:--:|
| 1 | $E[X]$ | $E[X]$ | 기댓값(평균) |
| 2 | $E[X^2]$ | $E[(x-\mu)^2]$ | 분산 |
| 3 | $E[X^3]$ | $E[(x-\mu)^3]/\sigma^3$ | 왜도(Skewness) |
| 4 | $E[X^4]$ | $E[(x-\mu)^3]/\sigma^4$ | 첨도(Kurtosis) |

* $r=2$부터는 mean centering 전처리를 한 결과이다.

* 왜도 - 얼마나 기울여져 있는가

* 첨도 - 분포가 얼마나 뾰족한가

## Moment Generating Function(MGF)
- 바로 앞에서 배운 Moment Function을 생성하는 함수

$$M_X(t)=E[e^{tX}]=
\begin{cases}
\sum_{x}e^{tX}p(x) & if\;X\;is\;discrete\\
\int_{-\infty}^{\infty}e^{tX}f(x)dx  & if\;X\;is\;continuous
\end{cases}$$

- **MGF가 생성하는 분포는 unique하다. 즉, 두 개의 확률 변수가 같은 확률 변수를 가지고 있다면, 이 둘은 같은 확률 분포를 가진다. 즉, MGF와 확률 분포는 일대일 대응. 중요**

- MGF를 t에 대해 한 번 미분해서 $t=0$을 대입하면 첫 번째 모멘트이고, t에 대해 두 번 미분해서 $t=0$을 대입하면 두 번째 모멘트이다. 일반화 시켜보면 t에 대해 n번 미분해서 $t=0$을 대입하면 n 번째 모멘트이다.

### 첫 번째 모멘트를 구해보자.  

$E[e^{tx}]=M_X(t)$  

$M_X'(t)={d\over dt}E[e^{tx}]=E[{d\over dt}e^{tx}]=E[xe^{tx}]$  

$M_X'(t=0)=E[x]$  

### 두 번째 모멘트를 구해보자.  
$M_X''(t)={d\over dt}M_X'(t)={d\over dt}E[xe^{tx}]=E[{d\over dt}xe^{tx}]=E[x^2e^{tx}]$  

$M_X''(t=0)=E[x^2]$  

### n 번째 모멘트를 구해보자.  
$M_X^{(n)}(t)={d^n\over dt^n}M_X(t)=E[x^ne^{tx}]$  

$M_X^{(0)}(t=0)=E[x^n]$  

### 그렇다면 왜 MGF를 n번 미분하면 n번째 모멘트가 나올까?
$e^x=1+x+{x^2\over2!}+{x^3\over3!}+...+{x^n\over n!}$  

$e^{tx}=1+tx+{(tx)^2\over2!}+{(tx)^3\over3!}+...+{(tx)^n\over n!}$  

$E[e^{tx}]=E(1+tx+{(tx)^2\over2!}+{(tx)^3\over3!}+...+{(tx)^n\over n!})$  

$=E[1]+tE[x]+{t^2\over2!}E[x^2]+{t^3\over3!}E[x^3]+...+{t^n\over n!}E[x^n]$  

${d\over dt}E[e^{tx}]={d\over dt}(E[1]+tE[x]+{t^2\over2!}E[x^2]+{t^3\over3!}E[x^3]+...+{t^n\over n!}E[x^n])$  

$t=0$  

${d\over dt}E[e^{tx}]=E[x]$  

## Moment Generating Functions - Binomial
$M_X(t)=E[e^{tx}]$  

$=\sum_{x=0}^{n}e^{tx}{n\choose x}p^x(1-p)^{n-x}$  

$=\sum_{x=0}^{n}{n\choose x}(pe^t)^x(1-p)^{n-x}$  

$=(pe^t+1-p)^n(\because 이항정리)$  

### 첫 번째 모멘트
$M'_X(t)=n(pe^t+1-p)pe^t$  

$M'_X(t=0)=n(p+1-p)p=np$  

Binomial Distribution에서 배웠던 기댓값과 같다는 것을 확인해볼 수 있다.

두 번째 모멘트 또한 같은 방법으로 구할 수 있다.

## Moment Generating Functions - Poisson
$M_X(t)=E[e^{tx}]$  

$=\sum_{x=0}^{\infty}e^{tx}(e^{-\lambda}\lambda^x/x!)$  

$=e^{-\lambda}\sum_{x=0}^{\infty}((\lambda e^t)^x/x!)$  

$=e^{-\lambda}(e^{\lambda})^{e^t}(\because Taylor\;Series)$  

### 첫 번째 모멘트
$M'_X(t)=e^{-\lambda}\lambda e^t(e^{\lambda})^{e^t}$  

$M'_X(t=0)=e^{-\lambda}\lambda e^{\lambda}=\lambda$  

## Moment Generating Functions - Geometric
## Moment Generating Functions - Exponential
$M_X(t)=E[e^{tx}]$  

$=\int_{x=0}^{\infty}e^{tx}\lambda e^{-\lambda x}dx$  

$=\lambda\int_{x=0}^{\infty}e^{-(\lambda-t)}dx$  

$=\lambda/\lambda-t\quad(\lambda>t)$  

### 첫 번째 모멘트
$M'_X(t)=-\lambda (-1)/(\lambda-t)^2=\lambda/(\lambda-t)^2$  

$M'_X(t=0)=1/\lambda$  