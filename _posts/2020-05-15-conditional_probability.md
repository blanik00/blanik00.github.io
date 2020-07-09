---
title: 'Conditional Probability'
date: 2020-05-15
permalink: /posts/2020/05/14/conditional_probability
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/Cj25K_leYZw"> </iframe>  

## Conditional Probability  
- $F$라는 이벤트가 일어났다는 조건 하에 이벤트 $E$가 일어날 확률  

- $P(E\|F)={P(EF)\over P(F)}, \quad P(F) > 0$  

- "Probability of E given F" 혹은 "Probability of E conditional on F"  
  

if $E$ and $F$ are mutually exclusive  
$P(E\|F)={P(EF)\over P(F)}={0\over P(F)}=0$  
  
if $F\subset E$  
$P(E\|F)={P(EF)\over P(F)}={P(F)\over P(F)}=1$  
  
## Conditional Probability - Example 1  
한 마을에 있는 인구를 성별과 고용 상태에 따라 나눈 것이다.  
  
| | Employed | Unemployed | Totals |  
|:--:|:--:|:--:|:--:|  
| M | 460 | 40 | 500 |  
| F | 140 | 260 | 400 |  
| Totals | 600 | 300 | 900 |

$P(M\|U)={P(MU)\over P(U)}={40 \over 300}$  

조건부 확률은 조건에 충실하게 풀면 된다.

## Conditional Probability - Example 2 
생략

## Conditional Probability - Example 3
생략
  
## Conditional Probability - Example 4
- $P(E\|F)={P(EF)\over P(F)}$  

- $P(EF)=P(F)P(E\|F)$  

- $P(E\|FG)={P(EFG)\over P(FG)}$  

  
Celine는 French 혹은 Chemistry 수업 중 어떤 것을 들을지 고민하고 있다. 그녀가 French를 수강하고 A학점을 받을 확률은 $1/2$이며, Chemistry를 수강하고 A학점을 받을 확률은 $2/3$이다. 만약 그녀가 동전던지기를 통해 어떤 수업을 들을지 결정한다면, 그녀가 Chemistry 수업을 듣고, A학점을 받게될 확률은 무엇인가?  
  
event C : Chemistry 수업을 수강하는 사건  
event A : A학점을 받는 사건  
  
구하고자 하는 확률은 $P(CA)$이다.  
  
$P(CA)=P(C)P(A\|C)=({1\over 2})({2\over 3})={1\over3}$  
  
## Multiplicative Rules in Probability  
조건부 확률의 정의로부터 다음을 도출할 수 있다.  

- $P(AB)=P(A)P(B\|A)=P(B)P(A\|B)$  

- $P(ABC)=P(AB)P(C\|AB)=P(A)P(B\|A)P(C\|AB)$  

- $P(ABCD)=P(ABC)P(D\|ABC)=P(A)P(B\|A)P(C\|AB)P(D\|ABC)$  
  
이것을 일반화하면 사건 $A_1$, $A_2$, ... $A_k$에 대해 $P(A_1A_2...A_k)=P(A_1)P(A_2\|A_1)P(A_3\|A_1A_2)...P(A_k\|A_1A_2...A_{k-1})$을 만족한다.  
  
**참고** 각 사건이 독립이라는 조건이 있다면 위 연산이 간단해진다.

## Bayes' Rule  
![1](https://user-images.githubusercontent.com/26649034/82064341-9777d680-9707-11ea-9727-4353740824c2.png) 

- $A_1$, $A_2$, $A_3$은 표본 공간 S의 Partition이다(Mutually Exclusive & Collectively Exhaustive).  

- $B$는 event이다.  

$P(B)=P(A_1B)+P(A_2B)+P(A_3B)$  
$\qquad=P(A_1)P(B\|A_1)+P(A_2)P(B\|A_2)+P(A_3)P(B\|A_3)$  
$\qquad=\sum_{i=1}^{3}P(A_i)P(B\|A_i)$  
  
$P(B)$ 즉, 우리가 관심있는 이벤트에 대한 확률은 **조건부 확률의 합**으로 표현할 수 있다.(Law of Total Probability) 이것이 Bayes' Rule의 시작점이다.  
  
이제 본격적으로 Bayes' Rule에 대해 알아본다.  
  
다음과 같은 확률들을 알고있다고 가정하자.  
- $P(A_1)$, $P(A_2)$, $P(A_3)$  
- $P(B\|A_1)$, $P(B\|A_2)$, $P(B\|A_3)$  
  
이 정보들을 가지고 다음과 같은 확률을 알아내야 한다고 하자.  
  
$P(A_1\|B)$, $P(A_2\|B)$, $P(A_3\|B)$  
  
이 작업을 해내는 것이 Bayes' Rule이다.  
- $$P(A_1|B)={P(A_1)P(B|A_1)\over P(B)}={P(A_1)P(B|A_1)\over P(A_1)P(B|A_1)+P(A_2)P(B|A_2)+P(A_3)P(B|A_3)}$$  

- $$P(A_2|B)={P(A_2)P(B|A_2)\over P(B)}={P(A_2)P(B|A_2)\over P(A_1)P(B|A_1)+P(A_2)P(B|A_2)+P(A_3)P(B|A_3)}$$  

- $$P(A_3|B)={P(A_3)P(B|A_3)\over P(B)}={P(A_3)P(B|A_3)\over P(A_1)P(B|A_1)+P(A_2)P(B|A_2)+P(A_3)P(B|A_3)}$$  
  
### 용어 정리  
![2](https://user-images.githubusercontent.com/26649034/82064328-947ce600-9707-11ea-9271-482fb3a038ac.png) 

### Bayes' Rule 정리  
1. Prior Probability와 Data Probability를 기반으로 Posterior Probability를 구하는 법칙  
2. $P(A_1\|B)$과 $P(A_1)$은 모두 $A_1$에 대한 확률이다. 다만 앞의 것은 $B$가 주어졌을 때의 확률이다. 무엇인가 주어졌다는 것은 정보가 주어졌다는 것이다. 즉, $B$는 정보다. 이 정보 $B$에 의해 업데이트된 것이다. 그래서 $P(A_1)$은 정보를 받기 전이라서 Prior이고, $P(A_1\|B)$은 정보를 받은 후라서 Posterior이다. 정리하자면 Posterior Probability는 Prior Probability의 업데이트된 버전이다.

## Bayes' Rule - Supplier Example
완성차 제조업체 A는 두 타이어 업체로부터 타이어를 공급받는다. 타이어 업체는 1, 2 두 가지가 있으며, 업체 1에서 공급받은 타이어의 10%가 불량품이며, 업체 2에서 공급받은 타이어의 10%가 불량품이다. 현재 A에서 보유하고 있는 타이어 재고의 40%가 1에서 공급받은 것이다. 이 때 불량 타이어가 발견되었을 때, 그것이 업체 1에서 공급받은 타이어일 확률을 구하라.

$P(S_1 \| D)$

우선 Prior Probability와 Data Probability를 알아야 한다.

- $P(S_1)=0.4, P(S_2)=0.6$

- $P(D \| S_1)=0.1, P(D\| S_2)=0.05$

$$\begin{matrix}
P(S_1 | D) &=& {P(S_1 \cap D)\over P(D)} \\
	&=& {P(S_1 \cap D)\over P(S_1 \cap D) + P(S_2 \cap D)} \\
	&=& {P(S_1)P(D|S_1)\over P(S_1)P(D|S_1) + P(S_2)P(D|S_2)} \\
	&=& 0.57
\end{matrix}$$

## Bayes' Rule - Teaching Methods
생략

## Bayes' Rule - Criminal Investigation
경찰관이 수사를 통해 60%의 확신을 가지고 용의자를 추려냈는데, 이 상황에서 새로운 증거가 발견되었다. 그것은 범인이 대머리라는 사실이다. 만약 전체 인구의 20%가 대머리일 때, 대머리인 사람이 범인일 확률을 구하라.

마찬가지로 Prior Probability와 Data Probability를 알아야 하는데, 조금 헷갈리는 부분이 있어 잘 생각해봐야 한다.

- $P(S)$ : 유죄일 확률  

- $P(\sim S)$ : 무죄일 확률  

- $P(B\| S)$ : 유죄이면서 대머리일 확률  

- $P(B\| \sim S)$ : 무죄이면서 대머리일 확률  


- $P(S)=0.6, P(\sim S)=0.4$  

- $P(B\| S)=1, P(B\| \sim S)=0.2$  

처음에는 전체 인구의 20%가 대머리라고 해서 $P(B\| S)$과 $P(B\| \sim S)$의 확률이 모두 0.2이라고 생각했다. 하지만 문제에서 범인이 대머리라는 사실이 밝혀졌으므로 $P(B\| S)=1$이다. 즉, 범인은 반드시 대머리다.

$$\begin{matrix}
P(S|B) &=& {P(S \cap B)\over P(B)} \\
	&=& {P(B|S)P(S)\over P(B|S)P(S) + P(B|\sim S)P(\sim S)} \\
	&=& 0.882
\end{matrix}$$

## Bayes' Rule - Disease Example
전체 인구의 1%가 희귀병에 앓고 있다. A사가 개발한 혈액 테스트는 97%의 확률로 이 희귀병을 진단할 수 있다(희귀병에 걸린 사람에게 희귀병에 걸렸다고 진단). 하지만 건강한 사람이 희귀병을 앓고 있다고 잘못 진단할 확률도 6% 있다.

우선 Prior Probability와 Data Probability를 알아두자.

- $D$ : 희귀병  

- $P$ : 양성  

- $N$ : 음성  

- $P(D)=0.01, P(\sim D)=0.99$  

- $P(P\| D)=0.97, P(N\| D)=0.03$  

- $P(P\| \sim D)=0.06, P(N\| \sim D)=0.94$  


1. $P(P)$  
$P(P)=P(D\cap P) + P(\sim D\cap P)$  
$\qquad=P(D)P(P\|D)+P(\sim D)P(P\|\sim D)$  
$\qquad=0.0691$  

2. $P(D\| P)$  
$P(D\| P)={P(D\cap P)\over P(P)}=0.14$  (위에서 다 구했던 것들임)  

3. $P(\sim D\| N)$  
$P(\sim D\| N)={P(\sim D\cap N)\over P(N)}={P(\sim D)P(N\|\sim D)\over 1-P(P)}=0.999$  