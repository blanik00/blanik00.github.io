---
title: 'Independence'
date: 2020-05-16
permalink: /posts/2020/05/16/independence
category:
  - posts
---

<iframe src="https://www.youtube.com/embed/dHTkIna_hFk"> </iframe>  

## Independence
$A$, $B$ 사건이 다음과 같은 조건을 만족하면 독립이라고 한다.

$$P(B|A)=P(B)$$

이 수식을 해석하면, "사건 $B$가 발생할 확률은 $A$의 발생 여부에 영향을 받지 않는다"이다.

식을 다시 써보면 다음과 같다.

$$P(AB)=P(A)P(B|A)=P(A)P(B)$$

즉, 조건부 확률에 해당하는 부분을 없앨 수 있다.

이를 응용하면 [Conditional Probability](https://blanik00.github.io/posts/2020/05/14/conditional_probability)에서 봤던 Multiplicative Rules in Probability을 단순화시킬 수 있다.

$P(A_1A_2...A_n)$  
$=P(A_1)P(A_2\|A_1)P(A_3\|A_1A_2)...P(A_n\|A_1A_2...A_{n-1})$  
$=P(A_1)P(A_2)...P(A_n)$  

## Independence Events - Example 1
A마을에는 소방차 한 대와 구급차 한 대가 있다. 소방차가 필요할 때 소방차를 사용할 수 있는 확률은 0.98이고, 구급차가 필요할 때 구급차를 사용할 수 있는 확률은 0.92이다. 이 둘을 동시에 호출했을 때 둘 다 사용할 수 있는 확률은 얼마인가?(두 사건은 독립이다)

A: 소방차  
B: 앰뷸런스  

$P(AB)=P(A)P(B)=0.9016$

## Independence Events - Example 2
두 개의 주사위를 던진다.  
$E_1= \\{ sum\; is\; 6 \\} = \\{ (1,5),(2,4),(3,3),(4,2),(5,1) \\} $  
$E_2= \\{ sum\; is\; 7 \\} = \\{ (1,6),(2,5),(3,4),(4,3),(5,2),(6,1) \\} $  
$E_3= \\{ first\; dice\; is\;4 \\} = \\{ (4,1),(4,2),(4,3),(4,4),(4,5),(4,6) \\} $  

1. $E_1$과 $E_2$는 독립인가?  
$E_1$과 $E_2$는 mutually exclusive하기 때문에 $P(E_1E_2)=0$이다.  
$P(E_1E_2)\neq P(E_1)P(E_2)$  
mutually exclusive와 independence가 다르다는 점을 주의해야 한다.  
2. $E_1$과 $E_3$는 독립인가? dependent  
3. $E_2$과 $E_3$는 독립인가? independent  

---

또한 사건 $E$, $F$가 독립이라면, $E$, $F^C$ 또한 독립이다.

$P(E)=P(EF)+P(EF^C)$  
$=P(E)P(F)+P(EF^C)$  

$P(EF^C)=P(E)(1-P(F))$  
$=P(E)P(F^C)$  

즉, $E$, $F$가 독립이라면, $E$가 발생할 확률은 $F$의 발생 여부에 영향을 받지 않는다.

---

세 개의 사건 $E$, $F$, $G$가 독립이기 위해서는 다음 조건을 만족해야 한다.

$P(EFG)=P(E)P(F)P(G)$  
$P(EF)=P(E)P(F)$  
$P(EG)=P(E)P(G)$  
$P(FG)=P(F)P(G)$  

세 사건이 독립이라면, $E$는 $F$와 $G$를 어떻게 조합해도 그 조합한 것과 독립이다. 예를 들어, $E$는 $F\cup G$과 독립이다.

$P[E(F\cup G)]=P(EF\cup EG)$  
$=P(EF)+P(EG)-P(EFG)$  
$=P(E)P(F)+P(E)P(G)-P(E)P(FG)$  
$=P(E)[P(F)+P(G)-P(FG)]$  
$=P(E)P(F\cup G)$  