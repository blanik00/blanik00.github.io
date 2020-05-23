---
title: 'Geometric, Negative Binomial, Hypergeometric distribution'
date: 2020-05-23
permalink: /posts/2020/05/23/geo_neg_hyp
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/IYJFMjYRMgM"> </iframe>  

## Geometric Distribution(기하 분포)
> Random Variable X : 첫 번째 성공이 일어날 때 까지 필요한 시행 횟수

- 베르누이 시행 활용
- 예를 들어, 다섯 번째 시행에서 첫 성공이 일어났다면, 확률은 $(1-p)^4p$이다.
- $P(X=n)=(1-p)^{n-1}p, \;\;n=1,2,3,...$
- 기하 확률 함수의 합은 1이 될까?

$\sum_{n=1}^{\infty}P(X=n)=p\sum_{n=1}^{\infty}(1-p)^{n-1}={p\over1-(1-p)}=1$

## Mean and Variance of Geometric Distribution
- $E[X]=1/p,\;\;V[X]=(1-p)/p^2$
- $E[X]$  
$=\sum_{i=1}^{\infty}i(1-p)^{i-1}p$  
$=p\sum_{i=1}^{\infty}i(1-p)^{i-1}$  
$Let\;\; 1-p=k$  
$=p\sum_{i=1}^{\infty}ik^{i-1}$  
$=p\sum_{i=1}^{\infty}{d\over dk}k^i$  
$=p{d\over dk}\sum_{i=1}^{\infty}k^i$  
$=p{d\over dk}{k\over 1-k}$  
$=p{1-k+k\over (1-k)^2}$  
$=p{1\over p^2}$  
$={1\over p}$  
- $E[X^2]={2-p\over p^2}$  
- $V[X]=E[X^2]-E[X]^2={1-p\over p^2}$  

## Geometric Distribution - Example
- 항아리에 $N$개의 흰공과 $M$개의 검은공이 있다. 검은공을 뽑을 때 까지 반복해서 뽑는 작업을 한다. (공을 뽑고 나면 다시 항아리에 넣어야 한다)

> RV X : 검은 공을 뽑을 때 까지 뽑기를 한 횟수

- $P(W)={N\over N+M}$
- $P(B)={M\over N+M}$

1. $P(X=n)$
$=P(W)^{n-1}P(B)=({N\over N+M})^{n-1}{M\over N+M}={MN^{n-1}\over (N+M)^{n}}$  
2. 검은공이 뽑힐 때 까지 적어도 $k$번의 시행이 필요할 확률
$P(X\ge k)$  
$={M\over N+M}\sum_{n=k}^{\infty}({N\over N+M})^{n-1}$  
$={M\over N+M}({N\over N+M})^{k-1}/(1-{N\over N+M})$  
$=({N\over N+M})^{k-1}$  

즉, "k-1번 동안 흰공만 뽑는 확률"과 "검은공을 처음으로 뽑은 것이 k번째인 확률"은 동일하다.

## Negative Binomial Distribution(음이항 분포)
- 기하 분포를 일반화 시킨 분포
- 확률 함수가 이항 분포와 유사해 이렇게 이름을 지은 것으로 보임

> Random Variable X : $r$번째 성공을 보기 위해 베르누이 시행을 몇 번 해야 하는가?

- 예를 들어, 5번째 베르누이 시행에서 3번째 성공을 볼 확률은, 앞의 네 번 동안 2번의 성공이 있어야 하며, 마지막인 다섯 번째 시행에서 성공하면 된다. ${4 \choose 2}p^2(1-p)^2p={4 \choose 2}p^3(1-p)^2$
- parameter는 $r$과 성공 확률인 $p$이다.
- $P(X=n)={n-1 \choose r-1}p^r(1-p)^{n-r},\;\; n=r,r+1,r+2,...$
- $r=1$이면 앞에서 배운 기하분포와 같다.
- $E[X]={r\over p}$
- $V[X]={r(1-p)\over p^2}$

**확률 변수의 기대값과 분산은 확률 함수의 파라미터의 함수 꼴로 표현된다.**  

## Negative Binomial Distribution - Example
주사위를 6이 세 번 나올 때 까지 던진다고 하자. 5번째 시행에서 세 번째 6이 나올 확률은 얼마인가?

> RV X : 6이 세 번 나올 때 까지 주사위를 던진 횟수($x\ge3$)

4번 중 2번은 6이 나와야 하고, 2번은 6이 나오면 안된다. 마지막인 다섯 번째 시행에서는 6이 나와야 한다.

$P(X=5)$  
$={4\choose 2}(1/6)^2(5/6)^{4-2}(1/6)$  
$={4\choose 2}(1/6)^3(5/6)^{4-2}$  
$={4\choose 2}(1/6)^3(5/6)^{4-2}$  

## Negative Binomial Distribution - Hiring Example
- 회사에서 직원을 3명 고용하려고 한다. 지원자와 인터뷰를 해서 합격시킬 확률이 0.6이라고 할 때, 몇 번의 인터뷰가 필요한가?

> RV X : 3명을 뽑을 때 까지 필요한 인터뷰 횟수($x \ge 3$)

1. $P(X=6)={5\choose 2}0.6^30.4^3=0.138$  
2. 회사가 6명을 인터뷰할 예산만 가지고 있을 때, 6번 인터뷰 동안 3명을 고용할 수 있는 확률을 구하라.
$P(X\le 6)=P(X=3)+P(X=4)+P(X=5)+P(X=6)$  

## Hypergeometric Distribution(초기하 분포)
- 주머니에 $N$개의 공이 있는데, $m$개는 흰 공이고, $N-m$개는 빨간 공이다. 주머니에서 $n$개를 비복원 추출로 뽑는다. 이 때 흰색 공의 갯수가 몇 개인지 나타내는 것이 초기하 분포이다.

> RV X : 샘플링한 $n$개 중 흰색 공의 갯수(X=0,1,2,...n)

- $P(X=i)={m\choose i}{N-m\choose n-i} / {N \choose n},\;\;i=0,1,2,...n$
- 분모 - $N$개 중 $n$개를 뽑는다.
- 분자 - $m$개 중 $i$개가 흰색 공이고, $N-m$개 중 $n-i$가 빨간 공이다.
- 파라미터는 $N$, $n$, $m$이다.

## Mean and Variance of Hypergeometric Distribution
- $E[X]=nm/N$
- $V[X]=n{m\over N}{(N-m)\over N}{N-n\over N-1}$
- 기대값과 분선은 파라미터의 함수인 것을 확인할 수 있다.

## Hypergeometric Distribution - Bad Unit Example
- 공장에서는 제품을 30개씩 제조한다. 여기에 5개의 불량품이 포함되어 있다고 하자. 30개 중 4개를 추출하여 품질 테스트를 수행한다.
> RV X : 4개의 샘플 중 불량품의 갯수

1. 불량품이 2개일 확률은 얼마인가?  
$P(X=2)={5\choose 2}{30-5\choose 4-2} / {30\choose 4}$  
2. 불량품이 2개 미만일 확률은 얼마인가?  
$P(X<2)=P(X=0)+P(X=1)$  

## Hypergeometric Distribution - Lot Defect Example
- 한 소비자가 물건을 사려고 한다. 이 소비자는 사려고 하는 10개의 물건 중 3개를 추출하여 이들이 모두 불량품이 아니라면 구매한다. 물건의 30%는 10개 중 4개의 불량이 있고, 70%는 10개 중 1개의 불량이 있다. 소비자가 물건을 구매하지 않을 확률을 구하라.  
- 구매할 확률을 구해 1에서 빼주는 것이 계산하기 편하다.

> RV X : 3개 중 불량품의 갯수

$P(X=0)=P(defective=4)P(X=0\|defective=4)+P(defective=1)P(X=0\|defective=1)$  
$=54/100$  
$\therefore 1-P(X=0)=46/100$  