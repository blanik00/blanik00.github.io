---
title: '1.1 명제'
date: 2020-10-18
permalink: /lecture/2020/10/18/set_theory_proposition
category:
  - lecture
tags:
  - 1. 집합론
---

## 명제
- 명제 : 참, 거짓이 분명히 판단되는 문장

- 단순 명제 : 하나의 명제
	- 지수는 블랙핑크의 멤버이다.

- 합성 명제 : 몇 개의 단순 명제들이 연결사에 의해 결합된 명제
	- 지수는 블랙핑크의 멤버이고, 로제도 블랙핑크의 멤버이다.

- 연결사 : 두 명제 $p$와 $q$에 대해

	| 명칭 | 기호 | 읽는 법 |
	|:-:|:-:|---|
	| 부정 | $\sim p$ | not $p$ |
	| 논리곱 | $p\land q$ | $p$ and $q$ |
	| 논리합 | $p\lor q$ | $p$ or $q$ |
	| 조건 | $p\rightarrow q$ | If $p$, then $q$ |
	| 쌍조건 | $p\leftrightarrow q$ | $p$ if and only if $q$ (iff) |

- 진리집합 : 해당 명제가 참이 되도록 하는 모든 원소의 집합. 명제 $p$의 진리집합은 $P$로,  $q$의 진리집합은 $Q$로 표기한다.
	- $p$ : $\sim$은 블랙핑크의 멤버이다.

	- $P$ : $\\{지수, 로제, 제니, 리사\\}$

	- **명제 $p$가 거짓이라면, 진리집합 $P$는 공집합이 된다.**

- 진리표 : 명제의 진리값을 표로 나타낸 것

	| $p$ | $q$ | $1. \sim p$ | $p\land q$ | $p\lor q$ | $2. p\rightarrow q$ | $3. p\leftrightarrow q$ |
	|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
	| **T** | **T** | F | T | T | T | T |
	| **T** | **F** | F | F | T | F | F |
	| **F** | **T** | T | F | T | T | F |
	| **F** | **F** | T | F | F | T | T |

	- $\sim p$, $p\rightarrow q$, $p\leftrightarrow q$의 경우에 추가 설명이 필요해 번호를 붙여놓았다.

	- 나중에 배울 명제에서는 한 명제 안에서도 여러 개의 명제가 등장하게 되는데, 그 때 연산의 순서는 다음과 같다.
		0. 괄호가 있는 경우에는 괄호를 최우선으로 처리
		1. $\sim p$
		2. $p\land q$ or $p\lor q$
		3. $p\rightarrow q$ or $p\leftrightarrow q$

	1. $\sim  p$  : 진리집합 $P$의 바깥 영역을 의미
		1. 명제 $p$가 참이다 $\rightarrow$ 진리집합 $P$의 내부에 해당한다. $\rightarrow$ 진리집한 $P$의 외부에 해당하지 않는다. $\rightarrow$ $P$의 외부는 공집합이다.

		2. 명제 $p$가 거짓이다 $\rightarrow$ 진리집합 $P$는 공집합이다. $\rightarrow$ 진리집한 $P$의 외부는 전체 집합이다. $\rightarrow$ 어떤 임의의 원소는 당연히 전체 집합에 포함되므로 참이 된다.
		
	2. $p\rightarrow q$
		- 앞의 것들과 다르게 명제가 언급되어지는 순서가 있다. 실제로 $p$와 $q$의 위치가 바뀌면 아예 다른 명제가 된다.

		- $P\subset Q$를 만족하면 참이 된다.

		- **$p$가 거짓이라면, $p\rightarrow q$는 항상 참이다.**($p$가 거짓이라면, $P$는 공집합이고, 공집합은 모든 집합의 부분집합이 된다.)

	3. $p\leftrightarrow q$
		- $P=Q$를 만족하면 참이다.

		- $p$, $q$가 참이어서 영역이 존재하거나, 거짓이어서 공집합이 된다면 참이 된다. 그 이외에는 거짓이 됨.(한 쪽은 참이라 영역이 존재하는데, 다른 한 쪽은 거짓이라 영역이 존재하지 않는 경우)

- 자주 쓰이는 명제들
	- $\equiv$는 왼쪽과 오른쪽 명제가 모든 논리적 가능성에 대해서 진리값이 같다.
	- 아래 내용들은 진리표를 그려 쉽게 증명할 수 있다.

	1. $p\rightarrow q\equiv\; \sim p\lor q$

	2. 드모르간의 법칙  
		- $\sim(p\land q)\equiv\; \sim p\lor \sim q$  

		- $\sim(p\lor q)\equiv\; \sim p\land \sim q$

	3. 대우법칙
		- $p\rightarrow q\equiv\; \sim q\rightarrow \sim p$

	4. 결합법칙
		- $(p\lor q)\lor r\equiv\; p\lor (q\lor r)$

		- $(p\land q)\land r\equiv\; p\land (q\land r)$

	5. 분배법칙	
		- $p\lor (q\land r)\equiv\; (p\lor q)\land(p\lor r)$

		- $p\land (q\lor r)\equiv\; (p\land q)\lor(p\land r)$

## 명제함수
### 명제함수와 한정기호
- 명제함수 : 변수 $x$가 결정되어야만 참, 거짓을 판단할 수 있는 문장
	- $p(x), q(x), ...$ 등으로 표현

	- ex) $p(x)$ : 블랙핑크의 멤버 수는 $x$명이다.

	- 명제에는 그 대상이 있고, 그 대상에는 범위가 존재한다. 예를 들어, 위에서 예로 든 $p(x)$에서 우리는 $x$에 자연수가 들어갈 것으로 예상한다. 범위가 잘못 주어지면  그 명제는 의미가 없어진다. 예를 들어, "블랙핑크의 멤버 수는 책상이다."라는 명제는 의미가 없다.

	- $x$의 범위를 "대상영역(Domain)" 혹은 "모집단(Universal)"이라고 한다. Universal의 앞글자를 다 $U$로 표현한다.

- 한정기호 : 대상영역에 대해서 **모두를 대상**으로 하거나 **일부를 대상**으로 하고 싶을 때 사용
	- 전칭기호($\forall$) : for every

	- 존재기호($\exists$) : for some

		- $U$ : 1반 학생

		- $p(x)$ : $x$는 블랙핑크의 팬이다.

		- $\forall x, p(x)$ : 1반 학생 전원은 블랙핑크의 팬이다.

		- $\exists x, p(x)$ : 1반 학생 블랙핑크의 팬인 사람이 적어도 한 명 있다.

## 명제의 부정
1. $\forall\rightleftharpoons\exists$

2. $\land\rightleftharpoons\lor$

3. $p\rightleftharpoons\sim p$

4. $<\rightleftharpoons\ge$

### 예시 1
- $\forall x, p(x)\rightleftharpoons \exists x, \sim p(x)$
	- $\forall x, p(x)$ : 1반 학생 전원은 블랙핑크의 팬이다.

	- $\exists x, \sim p(x)$ : 1반 학생 중 어떤 학생들은 블랙핑크의 팬이 아니다.

### 예시 2
- $U$ : 모든 사람

- $p(x)$ : $x$는 공부를 잘한다.

- $\forall x, p(x)\rightarrow 성공\land 행복$ 을 부정해보자.

	$$\begin{matrix}
	\forall x, p(x)\rightarrow 성공\land 행복 &\equiv& \forall x, \sim p(x)\lor (성공\land 행복) \\
			&\rightleftharpoons& \exists x, \sim(\sim p(x)\lor (성공\land 행복)) \\
			&\equiv& \exists x, p(x)\land \sim(성공\land 행복)) \\
			&\equiv& \exists x, p(x)\land (\sim성공\lor \sim행복)) \\
	\end{matrix}$$
	
### Exercise
다음 명제들을 부정하라.

1. $\forall x, x^2-2x+1\ge 0$

	$$\begin{matrix}
	\forall x, x^2-2x+1\ge 0 &\rightleftharpoons& \exists x, x^2-2x+1< 0 \\
	\end{matrix}$$

2. $\exists x, x^2=1\rightarrow x=3$

	$$\begin{matrix}
	\exists x, x^2=1\rightarrow x=3 &\equiv& \exists x, \sim(x^2=1)\lor (x=3) \\
	&\rightleftharpoons& \forall x, \sim(\sim(x^2=1)\lor (x=3)) \\
	&\equiv& \forall x, (x^2=1)\land (x\neq3)) \\
	\end{matrix}$$

3. $\exists x, \forall y, (p(x)\lor q(y))$

	$$\begin{matrix}
	\exists x, \forall y, (p(x)\lor q(y)) &\rightleftharpoons& \forall x, \exists y, \sim p(x)\land \sim q(y) \\
	\end{matrix}$$

4. $(\forall x, p(x))\land(\exists y, q(y))$

	$$\begin{matrix}
	(\forall x, p(x))\land(\exists y, q(y)) &\rightleftharpoons& (\exists x, \sim p(x))\lor(\forall y, \sim q(y)) \\
	\end{matrix}$$

## 함의와 동치
### 함진명제와 모순명제
- 항진명제($t$) : 모든 논리적 가능성의 진리값들이 참인 명제

- 모순명제($c$) : 모든 논리적 가능성의 진리값들이 거짓인 명제

- 항진명제의 진리집합은 $U$이며, 모순명제의 진리집합은 $\emptyset$이다.

### 함진명제와 모순명제의 성질
- 임의의 명제 $p$에 대해서
	- $p\lor \sim p\equiv t$

	- $p\land \sim p\equiv c$

	- $t\lor p\equiv t$

	- $t\land p\equiv p$
	
	- $c\lor p\equiv p$

	- $c\land p\equiv c$

### Exercise
1. $\sim p\rightarrow c\equiv p$

	$$\begin{matrix}
			\sim p\rightarrow c &\equiv& p\lor c \\
			&\equiv& p
	\end{matrix}$$

2. $(p\rightarrow q)\land(q\rightarrow r)\rightarrow(p\rightarrow r)\equiv t$

	$$\begin{matrix}
			(p\rightarrow q)\land(q\rightarrow r)\rightarrow(p\rightarrow r) &\equiv& (\sim p\lor q)\land(\sim q\lor r)\rightarrow(\sim p\lor r) \\
			&\equiv& \sim(\sim p\lor r)\rightarrow \sim((\sim p\lor q)\land(\sim q\lor r)) \\
			&\equiv& (p\land\sim r)\rightarrow (p\land \sim q)\lor(q\land \sim r) \\
			&\equiv& \sim(p\land\sim r)\lor (p\land \sim q)\lor(q\land \sim r) \\
			&\equiv& \sim p\lor r\lor (p\land \sim q)\lor(q\land \sim r) \\
			&\equiv& (\sim p\lor (p\land \sim q)) \lor (r\lor (q\land \sim r)) \\
			&\equiv& ((\sim p\lor p)\land (\sim p \lor \sim q)) \lor ((r\lor q)\land (r\lor \sim r)) \\
			&\equiv& (\sim p \lor \sim q) \lor (r\lor q) \\
			&\equiv& (\sim q \lor q) \lor (\sim p\lor r) \\
			&\equiv& t \\
	\end{matrix}$$

### 함의와 동치
- 함의 : 항진인 조건문 $p\rightarrow q$를 논리적 함의라 하고, $p\Rightarrow q$로 나타내며, $p$는 $q$의 충분조건, $q$는 $p$의 필요조건이다.
	- $인간\Rightarrow 동물$

	- 어떤 것이 인간이라 함은 그것은 동물이기도 하다. 따라서 인간이라고 하는 것은 동물로 분류되기에 충분한 조건이다.

	- 어떤 것이 동물이라 함은 그것은 인간으로 분류되기 위해 우선적으로 필요한 조건이다.

	- 못외우겠으면, 한글 알파벳 순서로 외우면 된다. 충분의 "ㅊ"이 필요의 "ㅍ"에 우선한다.($p\Rightarrow q$의 순서와 같음)

- 동치 : 항진인 쌍조건문 $p\leftrightarrow q$를 동치라 하고, $p\Leftrightarrow q$로 나타내며, $p$와 $q$는 서로의 필요충분조건이다.

- 앞서봤던 $\equiv$는 $\Leftrightarrow$와 같다.

### Exercise
두 명제함수 $p(x)$, $q(x)$의 진리집합을 각각 $P$, $Q$라 할 때, 다음 각 명제를 증명해보자.

- $p(x)\Rightarrow q(x)\equiv P\subseteq Q$

	$$\begin{matrix}
			p(x)\Rightarrow q(x)&\equiv&\forall x, p(x)\rightarrow q(x) \\
			&\equiv&\forall x, \sim p(x)\lor q(x) \\
			&\equiv&\forall x\in U, x\in P^c\lor x\in Q \\
			&\equiv&\forall x\in U, x\in P^c\cup Q \\
			&\equiv&U\subseteq (P^c\cup Q) \\
			&\equiv&U= (P^c\cup Q) \\
			&\equiv&(P^c\cup Q)^c=\emptyset \\
			&\equiv&(P\cap Q^c)=\emptyset \\
			&\equiv&(P-Q)=\emptyset \\
			&\equiv&P\subseteq Q \\
	\end{matrix}$$

- $p(x)\Leftrightarrow q(x)\equiv P= Q$

	- $p(x)\Rightarrow q(x)\equiv P\subseteq Q$
	
	- $q(x)\Rightarrow p(x)\equiv Q\subseteq P$

## Homework
1. 다음 각 명제를 증명하시오.
	1. $c\Rightarrow p\Rightarrow t$

		 위에서 본 Exercise에서 $p(x)\Rightarrow q(x)\equiv P\subseteq Q$이 성립함을 확인했다. 그렇기 때문에 $\emptyset\subseteq P \subseteq U$를 만족한다면 $c\Rightarrow p\Rightarrow t$가 된다. 

		$\emptyset$은 모든 집합의 부분집합이기에 $P$의 부분집합이며, 모든 집합은 $U$의 부분집합이기 때문에 $P$ 또한 $U$의 부분집합이다. 그러므로 $\emptyset\subseteq P \subseteq U$를 만족한다.

	2. $p\rightarrow q\equiv\sim(p\land\sim q)$

		$p\rightarrow q\equiv\sim p\lor q\equiv \sim(p\land\sim q)$

	3. $p\rightarrow(q\land r)\equiv(p\rightarrow q)\land(p\rightarrow r)$
		
		$p\rightarrow(q\land r)\equiv\sim p\lor(q\land r)\equiv(\sim p\lor q)\land(\sim p\lor r)\equiv(p\rightarrow q)\land(p\rightarrow r)$

	4. $p\rightarrow q\equiv (p\land\sim q)\rightarrow(q\land \sim q)$

		$(p\land\sim q)\rightarrow(q\land \sim q)\equiv(p\land\sim q)\rightarrow c=\sim(p\land\sim q)\lor c\equiv\sim(p\land\sim q)\equiv\sim p\lor q\equiv p\rightarrow q$

2. $\\{1,2,3\\}$이 대상영역일 때, 다음 각 명제를 부정하고 진리값을 말하시오.
	1. $\forall x,x+2<3\rightleftharpoons \exists x,x+2\ge 3$  
		
		$True(\because x=1)$
	
	2. $\exists x,\forall y, x^2+y^2\ge12 \rightleftharpoons\forall x, \exists y, x^2+y^2<12$  
		
		$True(\because x=3, y=1)$
	
	3. $\forall x, \forall y, \exists z, x^2+y^2\ge2z^2\rightleftharpoons\exists x, \exists y, \forall z, x^2+y^2<2z^2$  
		
		$False(\because z=1)$

## 출처
1. 이상엽Math
2. 수학의 즐거움, Enjoying Math