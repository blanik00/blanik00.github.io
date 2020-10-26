---
title: '1.3 관계와 분할'
date: 2020-10-20
permalink: /lecture/2020/10/20/set_theory_relation
category:
  - lecture
tags:
  - 1. 집합론
---

## 관계
- 곱집합 $A\times B$의 부분집합

- $A$를 기준이 되는 대상, $B$를 비교가 되는 대상으로 생각하면 된다.

- "$A$에서 $B$로의 관계 $R$"(relation)은 다음과 같이 정의한다.

$$R=(A,B,P(x,y))$$

- 기준이 되는 대상과 비교가 되는 대상이 같을 경우에, 예를 들어, $A$에서 $A$로의 관계는 "$A$에서의 관계"이다.

- $P(x,y)$는 명제함수이다. 곱집합의 원소 중 이 명제함수를 만족하는 것만이 **관계 $R$의 해집합**이 된다.

$$\{(x,y)|x\in A, y\in B, P(x,y)\;is\;true\}$$

### 관계의 예
- $A=\\{2,3\\}$, $B=\\{4,6\\}$

- $A\times B=\\{(2,4), (2,6), (3,4), (3,6)\\}$

- $P(x,y)$ : $x$는 $y$의 약수이다.

- $R=(A,B,P(x,y))=\\{(2,4), (2,6), (3,6)\\}$

- $(2,4)$는 관계 $R$에 포함되는데, 이를 $(2,4)\in R$ 혹은 $_2R_4$로 표시한다.

### 정의역
- 임의의 $y\in B$에 대하여 $_xR_y$인 모든 $x\in A$의 집합

- $Dom(R)$

- 위에서 봤던 예시에서 정의역은 $Dom(R)=\\{2,3\\}$이다.

### 상
- 임의의 $x\in A$에 대하여 $_xR_y$인 모든 $y\in B$의 집합

- $Im(R)$

- 위에서 봤던 예시에서 상은 $Im(R)=\\{4,6\\}$이다.

## 관계의 성질
- 집합 $X=\\{1,2,3\\}$에서의 관계 $R$에 대하여 

- 반사성(reflexive) : $\forall x\in X, _xR_x$
	- $R_1=\\{(1,1), (2,2)\\}$은 반사적이지 않다.($(3,3)$이 없기 때문)

	- $R_2=\\{(1,1), (2,2), (3,3), (1,3)\\}$은 반사적이다.

	- 반사성을 만족시키기 위한 최소한의 원소(예시에서는 $(1,1), (2,2), (3,3)$)을 대각관계 혹은 항등관계라고 하며, $\Delta_X$라 표시한다.

- 대칭성(symmetric) : $_xR_y\Rightarrow _yR_x$
	- $R_3=\\{(1,1), (1,2), (2,1)\\}$은 대칭적이다.

- 반대칭성(antisymmetric) : $_xR_y\land _yR_x\Rightarrow x=y$
	- $R_3$는 반대칭적이지 않다.($_1R_2\land _2R_1\rightarrow x\neq y$)

- 추이성(transitive) : $_xR_y\land _yR_z\Rightarrow_xR_z$
	- $R_4=\\{(1,1), (1,2), (2,3)\\}$은 추이적이지 않다.($(1,3)$이 없기 때문)

- $R_{5}=\\{(1,1), (1,3), (2,2), (2,3), (3,1), (3,2)\\}$는 대칭성만 만족한다.

## 여러가지 관계
### 역관계($R^{-1}$)  
$$R^{-1}=\{(y,x)|(x,y)\in R\}$$

- 예를 들어, $R=\\{(1,1), (1,2)\\}$이라면, $R^{-1}=\\{(1,1), (2,1)\\}$이다.

### 합성관계  

- 집합 $X$에서의 관계 $G$와 $H$에 대하여

$$H\circ G=\{(x,y)|\exists z,(x,z)\in G\land (z,y)\in H)\}$$

## 역관계와 합성관계에 관한 정리
집합 $X$에서의 관계 $F, G, H$에 대하여 다음이 모두 성립한다.

- $(F^{-1})^{-1}=F$

$$\begin{matrix}
	(x,y)\in (F^{-1})^{-1} &\equiv& (y,x)\in F^{-1} \\
	&\equiv& (x,y)\in F \\
\end{matrix}$$

- $(H\circ G)\circ F=H\circ (G\circ F)$

$$\begin{matrix}
	(x,y)\in (H\circ G)\circ F &\equiv& \exists z,(x,z)\in F\land (z,y)\in (H\circ G) \\
	&\equiv&  \exists z,w,(x,z)\in F\land (z,w)\in G\land (w,y)\in H \\
	&\equiv&  \exists w,(x,w)\in (G\circ F)\land (w,y)\in H \\
	&\equiv&  (x,y)\in H\circ(G\circ F) \\
\end{matrix}$$

- $(G\circ F)^{-1}=F^{-1}\circ G^{-1}$

$$\begin{matrix}
	(x,y)\in (G\circ F)^{-1} &\equiv& (y,x)\in (G\circ F) \\
	&\equiv&  \exists z, (y,z)\in F\land (z,x)\in G \\
	&\equiv&  \exists z, (z,y)\in F^{-1}\land (x,z)\in G^{-1} \\
	&\equiv&  \exists z, (x,z)\in G^{-1}\land (z,y)\in F^{-1} \\
	&\equiv&  (x,y)\in F^{-1}\circ G^{-1} \\
\end{matrix}$$

## **동치관계(Equivalence Relation)**
- $E$로 표기함

- 반사적, 대칭적, 추이적 관계

### 예시
- 우리가 알고있는 수체계에서 "$=$"는 동치관계를 만족한다.
	- 반사성 : $a=a$

	- 대칭성 : $a=b\Rightarrow b=a$

	- 추이성 : $a=b\land b=c\Rightarrow a=c$

- 명제의 모든 논리적 가능성이 같음을 나타내는 "$\equiv$"도 동치관계를 만족한다.
	- 반사성 : $p\equiv p$

	- 대칭성 : $p\equiv q\Rightarrow q\equiv p$

	- 추이성 : $p\equiv q\land q\equiv r\Rightarrow p\equiv r$

- 도형의 합동도 동치관계를 만족한다.

- 집합 $X$에서 만들 수 있는 동치관계 중 가장 큰 것은 $X^2$이고, 가장 작은 것은 대각관계(항등관계)이다.

## 순서관계
- 반사적, 반대칭적, 추이적 관계

- 나중에 자세히 배움

## 분할

- 분할 : 집합 $X$에 대하여 다음 세 조건을 만족하는 집합족 $P=\\{A\|A\subset X\\}$
	1. 공집합을 원소로 하지 않는다.
		- $\forall A\in P, A\neq\emptyset$
	2. $X$를 덮는다.
		- $\bigcup P=X$
	3. 서로소 집합족이다.
		- $\forall A_1, A_2\in P, A_1\cap A_2=\emptyset \lor A_1=A_2$

- 동치관계를 만들어내기 위해 분할이 사용된다.

- 동치와 분할의 관계는 뒤에서 살펴본다.

### 분할의 예시
- $X=\\{1,2,3,4,5\\}$

- $P=\\{\\{1,2\\},\\{3,4\\},\\{5\\}\\}$

## 동치류
- 집합 $X$ 상의 하나의 동치관계를 $E$라고 할 때, 동치류 $E_x=\\{y\in X\| _xR_y \\}$이다.

- 수학 시험 결과 "상엽"과 같은 시험 점수를 받은 학생이 "지수", "제니"라면 $E_{상엽}=\\{지수, 제니\\}$이다.

## 상집합
- 집합 $X$에서의 모든 동치류의 집합

- $X / E=\\{E_x\|x\in X\\}$

- $X/E=\\{\\{상엽, 지수, 제니\\}, \\{떡고릴라, 사나, 나연\\}\\}$이 될 수 있다.

## 동치류와 상집합의 예시
- $X=\\{1,2,3,4,5\\}$

- $E=\\{(1,1), (2,2), (3,3), (4,4), (5,5), (1,3), (3,1), (2,4), (4,2)\\}$

	- $E_1=\\{1,3\\}=E_3$

	- $E_2=\\{2,4\\}=E_4$

	- $E_5=\\{5\\}$

	- $\therefore X/E=\\{\\{1,3\\},\\{2,4\\},\\{5\\}\\}$

- 우리는 동치관계 $E$에 대한 상집합을 구했다. 그런데 우리가 만들어낸 상집합이 분할이기도 한 점을 확인할 수 있다. 즉, 우리는 **동치관계로부터 분할을 만들어냈다.**

## $R_P(X/P)$
- 분할 $P$에 의한 관계

- 위에서 배운 상집합과 표기가 비슷한데, / 뒤에 관계가 오면 집합족을 의미($X/E$)하고, 집합족이 오면 관계를 의미($X/P$)하는 것이다. 

$$\{(x,y)|\exists A\in P, x,y\in A\}$$

## $X/E$와 $X/P$ 정리

|  | $X/E$ | $X/P$ |
|:--:|:--:|:--:|
| X 뒤에 오는 것 | 관계 | 분할(집합족) |
| 정의 | $\\{E_x\|x\in X\\}$ | $\\{(x,y)\|\exists A\in P,(x,y)\in A\\}$ |
| 의미 | 집합 X에서의 모든 동치류의 집합(**집합족**) | 분할 P에 의한 **관계** |


### 예시
- $X=\\{1,2,3,4,5\\}$

- $P=\\{A_1, A_2, A_3\\}=\\{\\{1,2\\},\\{3,4\\},\\{5\\}\\}$

- $A_1$으로 만들어낼 수 있는 순서쌍 : $\\{(1,1), (1,2), (2,1), (2,2)\\}$

- $A_2$으로 만들어낼 수 있는 순서쌍 : $\\{(3,3), (3,4), (4,3), (4,4)\\}$

- $A_3$으로 만들어낼 수 있는 순서쌍 : $\\{(5,5)\\}$

- $\therefore R_P=\\{(1,1), (1,2), (2,1), (2,2), (3,3), (3,4), (4,3), (4,4), (5,5)\\}$

- $R_P$는 동치관계임을 알 수 있다.

- 우리는 집합 $X$의 **분할로부터 동치관계를 만들어냈다.**

- 앞선 예시에서는 동치관계로부터 분할을 만들어냈고, 이번 예시에서는 분할로부터 동치관계를 만들어냈다. 이 둘 사이에 밀접한 관계가 있음을 알 수 있다.

## 여러가지 정리
- 공집합이 아닌 집합 $X$ 위의 동치관계 $E$에 대하여 다음이 모두 성립한다.
	- $E_x\neq\emptyset$
		- $X\neq\emptyset\Rightarrow\exists x\in X$

		- $E\;\;is\;\;reflexive\Rightarrow _xR_x$

		- $x\in E_x$

		- $\therefore E_x\neq\emptyset$

	- $E_x=E_y\Leftrightarrow_xR_y$
		- $E_x=E_y\rightarrow_xR_y$
			- $x\in E_x(\because reflexive)\Rightarrow x\in E_y(\because E_x=E_y)\Leftrightarrow _yR_x\Rightarrow _xR_y$

		- $_xR_y\rightarrow E_x=E_y$
			- NTS : $E_x\subset E_y, E_y\subset E_x$
				1. $z\in E_x\Leftrightarrow_xR_z\Rightarrow _yR_z(\because _yR_x\land_xR_z\Rightarrow_yR_z)\Leftrightarrow z\in E_y$

				2. $z\in E_y\Leftrightarrow_yE_z\Rightarrow_xE_z(\because _xR_y\land_yR_z\Rightarrow_xR_z)\Leftrightarrow z\in E_x$

	- $E_x\cap E_y\neq\emptyset\Leftrightarrow _xR_y$
		1. $$\begin{matrix}
				E_x\cap E_y\neq\emptyset &\Leftrightarrow& \exists z,z\in E_x\land z\in E_y \\
				&\Leftrightarrow&  \exists z,  _xR_z\land _yR_z \\
				&\Rightarrow& \exists z, _xR_z\land _zR_y \\
				&\Rightarrow& _xR_y(\because transitive) \\
			\end{matrix}$$

		2. $$\begin{matrix}
				_xR_y &\Rightarrow& E_x=E_y (\because 위에서 증명함)\\
				&\Rightarrow&  E_x\cap E_y\neq\emptyset \\
			\end{matrix}$$

## 동치와 분할이 사실 같은 것임을 증명
- $X$ : 공집합이 아닌 집합 

- $E$ : $X$ 위의 동치관계

### $X/E$는 $X$의 분할이다.

- 분할임을 증명하기 위해서는 아래 세 가지 조건을 만족하면 된다.

1. $X/E$는 공집합을 원소로 갖지 않는다.
	- 동치류는 공집합을 가지지 않는다.($\because reflexive and\;X\;is\;not\;empty$)

	- $\emptyset\notin X/E$

2. $X/E$는 서로소 집합족이다.
	- $if\;E_x\cap E_y\neq\emptyset \Rightarrow _xR_y \Rightarrow E_x=E_y$

	- $if\;E_x\neq E_y \Rightarrow E_x\cap E_y=\emptyset$(대우)

3. $\bigcup X/E=X$
	- NTS : $\bigcup X/E\subset X, X\subset \bigcup X/E$
		1. $\bigcup X/E\subset X$(자명함)

		2. $\forall x\in X,\exists E_x\in X/E, s.t.\;x\in E_x$  
			($X$의 모든 원소 $x$는 $X/E$의 어떤 원소에 반드시 포함된다.)
			$\therefore X\subseteq X/E$

- $X$ : 공집합이 아닌 집합 

- $P$ : 분할

### $R_P(X/P)$는 $X$ 상의 동치관계이다.

- 동치관계임을 증명하기 위해서는 아래 세 가지 조건을 만족하면 된다.

1. $R_P$는 반사적이다.
	- $\forall x\in X, \exists A\in P\;s.t.\;x\in A$($\because$ $P$는 $X$를 덮는다)

	- $\therefore _x{R_P}_x$

2. $R_P$는 대칭적이다.
	- $(x,y)\in R_P\Rightarrow\exists A\in P\;s.t.\;x,y\in A$

	- $\therefore (y,x)\in R_P$

3. $R_P$는 추이적이다.
	- $\forall x,y,z\in X, _xR_y\land _yR_z$

	- $\Rightarrow \exists A,B\in P,\;s.t.\; x,y\in A, y,z\in B$

	- $A=B$(분할은 서로소 집합이므로, $A, B$ 모두 $y$를 원소로 갖는다면, $A=B$이다)

	- $_xR_z$


## 출처
1. 이상엽Math
2. 수학의 즐거움, Enjoying Math