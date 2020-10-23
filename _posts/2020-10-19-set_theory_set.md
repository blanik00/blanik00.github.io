---
title: '1.2 집합'
date: 2020-10-19
permalink: /lecture/2020/10/19/set_theory_set
category:
  - lecture
tags:
  - 1. 집합론
---

## 집합(set) = collection = family
- 기준을 만족하는 서로 다른 대상을 모아놓은 것

- 집합이 되기 위해서는 T/F를 명확히 구분할 수 있어야 한다.

	- ex. 키가 190 이상인 사람들의 모임 -> 집합 O

	- ex. 잘생긴 사람들의 모임 -> 집합 X

- 영어 대문자로 표기한다.(ex. A, B, C, ...)

- 원소 : 집합을 이루는 개체들

	- 원소는 영어 소문자로 표기한다.(ex. a, b, c)

	- 집합에서 원소들의 순서는 중요하지 않다. $\\{1, 2\\}$나 $\\{2, 1\\}$이나 동일한 집합이다.

	- $a\in A$는 "$a$가 $A$의 원소"라는 뜻

- 집합을 나타내는 방법
	- 원소나열법 : $\\{1,2,3\\}$과 같이 집합에 속하는 원소들을 일일이 나열하는 것. 집합이 커지면 표시하기 어렵기 때문에 잘 사용하지 않는다.

	- 조건제시법 : $\\{x\|1\le x\le3, x\in \mathbb{N}\\}$

- 중복집합 : 중복되는 원소를 허용하는 집합

## Exercise 1
Show that $\sqrt{2}$ is not the rational number.

"$\sqrt{2}$는 유리수이다."라고 가정한 후, 이것이 잘못된 것임을 보임으로써 "$\sqrt{2}$는 유리수가 아니다."라는 것을 증명할 것이다.

rational number(유리수)는 다음과 같이 정의할 수 있다.

$$\mathbb{Q}=\{ {q\over p} |p,q\in Z, p\neq0\}$$

증명을 하기 위해서 가정해야할 것은 ${q\over p}$는 더 이상 약분할 수 없다는 것이다.(약분할 수 있다면 정수가 될 수 있기 때문에)

${q^2\over p^2}=2$

$p^2=2q^2$

$\therefore p^2\;is\;even\Rightarrow p\;is\;even$

$Let\;p=2k$

$4k^2=2q^2$

$2k^2=q^2$

$\therefore q^2\;is\;even\Rightarrow q\;is\;even$

$p, q$ 모두 even이므로 common factor인 2를 포함한다. 이는 ${q\over p}$를 약분할 수 없다는 기존의 가정에 위배된다.

$\therefore \sqrt{2}\;is\;irrational\;number.$

## 합집합($A\cup B$), 교집합($A\cap B$), 여집합($A^c$), 차집합($A-B$)
- $X$ : 전체 집합(Universal Set)

- $Let\;A,B\subset X$

- $A\cup B:\\{x\|x\in A\lor x\in B\\}$

- $A\cap B:\\{x\|x\in A\land x\in B\\}$

- $A^c:\\{x\|x\in U\land x\notin A\\}$

- $A-B$ : $\\{x\|x\in A\land x\notin B\\}$
	- $A\cap B^c$와 같음

## 부분집합($A\subseteq B$)
- $\forall x\in A, x\in B\Rightarrow A\subseteq B$

- 경우에 따라서는 $\subset$으로 표기하기도 함

## 진부분집합($A\subset B$)
- $A\subseteq B\land A\neq B$

- 경우에 따라서는 $\subsetneq$으로 표기하기도 함

- 따라서 집합 간의 관계가 부분집합인지 진부분집합인지는 문맥에 따라 파악해야 한다.

## $A=B$
"집합 $A$와 집합 $B$가 같다."는 $A=B$로 표기한다. 

$$\begin{matrix}
	A=B &\equiv& A\subset B\;and\;B\subset A \\
	&\equiv& x\in A\rightarrow x\in B\land x\in B\rightarrow x\in A \\
\end{matrix}$$

## Power Set(멱집합)
집합 $A$의 부분집합의 모음을 Power Set이라고 하며, 다음과 같이 정의한다.

$$P(A)=\{B|B\subset A\}$$

## Exercise 2
If $A$ has $n$ elements, then show that $P(A)$ has $2^n$ elements.

- 수학적 귀납법을 이용해 증명(Proof by induction)

- Base Case : $n=0$
	- $\|A\|=\emptyset\Rightarrow P(A)=\\{\emptyset\\}\Rightarrow\|P(A)\|=1=2^0$
	- $\therefore$ Base Case is true

- Inductive Hypothesis : $\|A\|=k\Rightarrow\|P(A)\|=2^k$

- Inductive Step : $\|A\|=k+1\Rightarrow\|P(A)\|=2^{k+1}$

Need To Show : $if\;\|A\|=k,\|P(A)\|=2^k,\;then\;\|A\|=k+1,\|P(A)\|=2^{k+1}$

$Let\;S=\\{e_1,e_2,...,e_k\\},A=\\{e_1,e_2,...,e_{k+1}\\}$

Inductive Hypothesis에 의해 $S$는 $2^k$개의 부분집합을 가진다.

$A=S\cup \\{e_{k+1}\\}$이므로 $S$의 모든 부분집합은 $T$의 부분집합이기도 하며, $T$의 부분집합은 $e_{k+1}$이 포함되는 것과 $e_{k+1}$이 포함되지 않는 것으로 나눌 수 있다.

1. $e_{k+1}$을 포함하지 않는 경우  
	$P(S)$와 같다.

2. $e_{k+1}$을 포함하는 경우  
	$P(S)$의 각 원소에 $e_{k+1}$을 추가한 것

$\therefore 2^k+2^k=2^{k+1}$

## 집합족(Family of Sets)
- 집합을 원소로 갖는 집합
	- ex. $\\{\emptyset, \\{1,2\\}\\}$

	- ex. Power set

- 보통 $F$로 표기한다.

## 첨수족(Indexed Family)
- 집합족의 표현을 간단하게 하기 위해 만들어진 것

- 첨수(번호)가 부여된 대상들로 이루어진 집합

- 첨수들의 집합을 첨수집합이라고 하며, $I$로 표기한다.

- 첨수족이 필요한 이유
	- $A=\\{1,2\\}$

	- $A$로 집합족인 $P(A)=\\{\emptyset, \\{1\\}, \\{2\\}, \\{1,2\\}\\}=F$를 만들자.

	- 위 예시에서 $F$를 표시할 때, $A$의 원소의 수가 작아서 표시할 수 있었지 1000개 혹은 10000개가 되면 $P(A)$를 표시하기 어려워진다. 그래서 집합족 $F$의 원소를 효율적으로 표현하기 위한 방법이 필요했다.

	- $F$의 원소의 수는 4이므로 첨수집합 $I=\\{1,2,3,4\\}$를 만든다.

	- 이 첨수집합 $I$와 $F$의 대응관계를 생각해보면 $A_i:I\rightarrow F$이다. 표로 이해하는 것이 쉽다. 즉, 정수와 집합족의 원소들을 대응시키는 것이다.
	
	| $A_i$  | $I$  | $\rightarrow$  | $F$  |
	|:-:|:-:|:-:|:-:|
	| $A_1$  | 1  | $\rightarrow$  | $\emptyset$  |
	| $A_2$  | 2  | $\rightarrow$  | $\\{1\\}$  |
	| $A_3$  | 3  | $\rightarrow$  | $\\{2\\}$  |
	| $A_4$  | 4  | $\rightarrow$  | $\\{1,2\\}$  |

	- 이 대응관계를 적용하여 $F=\\{A_1, A_2, A_3, A_4, \\}$로 표기한다면, 일일이 원소들을 나열할 필요가 없어진다.

	- 보다 더 간단하게, $F=\\{A_i\| i\in I\\}$로 표시할 수 있다.

	- 집합족을 첨수를 사용하여 표현할 때 "첨수화 되었다"라고 말하며, 첨수화된 집합족은 "첨수족"이라고 한다.

## 집합족의 연산
- $\cup F$

$$\begin{matrix}
		\cup F &\equiv& \bigcup\limits_{A\in F} A \\
		&\equiv& A_1\cup A_2\cup\cdots \\
		&\equiv& \{x|\exists A\in F,x\in A\}
\end{matrix}$$

- $\cap F$

$$\begin{matrix}
		\cap F &\equiv& \bigcap\limits_{A\in F} A \\
		&\equiv& A_1\cap A_2\cap\cdots \\
		&\equiv& \{x|\forall A\in F,x\in A\}
\end{matrix}$$

- $F=\\{\\{1,2,3\\}, \\{2,3,4\\}, \\{3,4,5\\}\\}$가 있다고 하자. $\cup F$와 $\cap F$를 구하라.
	- $\cup F=\bigcup\limits_{i=1}^{3}A_i=\bigcup\limits_{i\in I}A_i=\\{1,2,3,4,5\\}$

	- $\cap F=\bigcap\limits_{i=1}^{3}A_i=\bigcap\limits_{i\in I}A_i=\\{3\\}$

- 다양한 표기법을 기억해두자!

- 만약 $I=\emptyset$이라면?
	- $\bigcup\limits_{i\in I}A_i=\emptyset$
		- 직관적으로 당연함. 첨수집합에 원소가 없다는 것은 이에 해당하는 첨수족에도 아무런 원소가 없다는 것. 즉, 공집합이라는 것.

	- $\bigcap\limits_{i\in I}A_i=U$
		- 직관적으로 받아들이기 힘들 수 있음.

		- NTS : $\bigcap\limits_{i\in I}A_i\subseteq U$, $U\subseteq \bigcap\limits_{i\in I}A_i$
		
		- 첫 번째. $U$는 모든 집합을 부분집합으로 가지기 때문에 자명

		- 두 번째  

		$$\begin{matrix}
			U\subseteq \bigcap\limits_{i\in I}A_i &\equiv& \forall x\in U, x\in \bigcap\limits_{i\in I}A_i \\
			&\equiv& \forall x\in U, \forall i\in I, x\in A_i \\
			&\equiv& i\in I\rightarrow x\in A_i \\
		\end{matrix}$$
		
		- $I=\emptyset$이므로 $i\in I$이라는 가정은 거짓이 된다. 즉, 가정이 거짓이므로 항상 참이 된다.	

- 드모르간의 법칙
	- $(\bigcup\limits_{A\in F}A)^c=\bigcap\limits_{A\in F}A^c$  
		
	$$\begin{matrix}
		(\bigcup\limits_{A\in F}A)^c &\equiv& x\in (\bigcup\limits_{i\in I}A_i)^c \\
		&\equiv& \sim(x\in \bigcup\limits_{i\in I}A_i) \\
		&\equiv& \sim(\exists i\in I, x\in A_i) \\
		&\equiv& \forall i\in I, x\notin A_i \\
		&\equiv& \forall i\in I, x\in A_i^c \\
		&\equiv& x\in \bigcap\limits_{i\in I}A_i^c \\
	\end{matrix}$$

	- $(\bigcap\limits_{A\in F}A)^c=\bigcup\limits_{A\in F}A^c$  

	$$\begin{matrix}
		(\bigcap\limits_{A\in F}A)^c &\equiv& x\in (\bigcap\limits_{i\in I}A_i)^c \\
		&\equiv& \sim(x\in \bigcap\limits_{i\in I}A_i) \\
		&\equiv& \sim(\forall i\in I, x\in A_i) \\
		&\equiv& \exists i\in I, x\notin A_i \\
		&\equiv& \exists i\in I, x\in A_i^c \\
		&\equiv& x\in \bigcup\limits_{i\in I}A_i^c \\
	\end{matrix}$$

- 분배법칙
	- $A\cap(\bigcup\limits_{B\in F}B)=\bigcup\limits_{B\in F}(A\cap B)$  

	$$\begin{matrix}
		A\cap(\bigcup\limits_{B\in F}B) &\equiv& x\in A\land x\in \bigcup\limits_{B\in F} B \\
		&\equiv& x\in A\land \exists B\in F, x\in B \\
		&\equiv& \exists B\in F, x\in A\land x\in B \\
		&\equiv& \exists B\in F, x\in (A\cap B) \\
		&\equiv& \bigcup\limits_{B\in F}(A\cap B) \\
	\end{matrix}$$

	- $A\cup(\bigcap\limits_{B\in F}B)=\bigcap\limits_{B\in F}(A\cup B)$  

	$$\begin{matrix}
		A\cup(\bigcap\limits_{B\in F}B) &\equiv& x\in A\lor x\in \bigcap\limits_{B\in F} B \\
		&\equiv& x\in A\lor \forall B\in F, x\in B \\
		&\equiv& \forall B\in F, x\in A\lor x\in B \\
		&\equiv& \forall B\in F, x\in (A\cup B) \\
		&\equiv& \bigcap\limits_{B\in F}(A\cup B) \\
	\end{matrix}$$


## 곱집합(Product Set)
- Cartesian Product 혹은 Descartes Product라고 불리기도 한다.

- 위에서 배운 집합족은 집합을 원소로 갖는 집합이었다면, **곱집합은 순서쌍(튜플)을 원소로 갖는 집합**이다.

- 곱집합을 배우기 전에 곱집합을 이루는 순서쌍에 대해 좀 더 자세히 알아야 한다.

- 순서쌍 (a, b)는 a와 b의 순서가 중요하다. 그래서 "순서쌍이 같다"고 말하기 위해서는 원소가 같을 뿐만 아니라, 그들의 순서도 같아야 한다. 

- 하지만 집합이라는 것은 원소들 간의 순서가 무의미하다.

- 그렇기 때문에 순서가 중요한 순서쌍과 순서가 무의미한 집합을 함께 사용하는 것은 힘들다. 그래서 우리는 순서쌍을 집합의 영역역에 끌어들이기 위해 순서쌍을 집합으로 재정의해보는 과정이 필요했다.

- 두 개의 집합 $A,B$가 있을 때, 곱집합은 다음과 같이 정의한다.

$$A\times B=\{(a,b)|a\in A\land b\in B\}$$

- $\mathbb{R}\times \mathbb{R}=\mathbb{R}^2$는 데카르트 평면 혹은 카테시안 평면이라고 한다. 이는 우리가 아는 좌표 평면을 의미한다.

## 곱집합의 연산
- $A\times\emptyset=\emptyset\times A=\emptyset$

- $A\times(B\cap C)=(A\times B)\cap(A\times C)$  

$$\begin{matrix}
	A\times(B\cap C) &\equiv& (x,y)\in A\times(B\cap C) \\
	&\equiv& x\in A\land y\in(B\cap C) \\
	&\equiv& x\in A\land y\in B\land y\in C \\
	&\equiv& (x\in A\land y\in B)\land (x\in A\land y\in C) \\
	&\equiv& ((x,y)\in A\times B)\land ((x,y)\in A\times C) \\
	&\equiv& (x,y)\in (A\times B)\cap (A\times C) \\
\end{matrix}$$

- $A\times(B\cup C)=(A\times B)\cup(A\times C)$  

$$\begin{matrix}
	A\times(B\cup C) &\equiv& (x,y)\in A\times(B\cup C) \\
	&\equiv& x\in A\land y\in(B\cup C) \\
	&\equiv& x\in A\land y\in B\lor y\in C \\
	&\equiv& (x\in A\land y\in B)\lor (x\in A\land y\in C) \\
	&\equiv& ((x,y)\in A\times B)\lor ((x,y)\in A\times C) \\
	&\equiv& (x,y)\in (A\times B)\cup (A\times C) \\
\end{matrix}$$

- $A\times(B-C)=(A\times B)-(A\times C)$  

$$\begin{matrix}
	A\times(B-C) &\equiv& A\times(B\cap C^c) \\
	&\equiv& (A\times B)\cap (A\times C)^c \\
	&\equiv& (A\times B)- (A\times C) \\
\end{matrix}$$

## 집합족의 곱집합
- 임의의 집합족 $F$가 첨수집합 $I$에 의해서 첨수화된 첨수족 $\\{A_i\|i\in I\\}$의 곱집합 $\prod A_i$는 

$$\begin{matrix}
	\prod A_i &\equiv& A_1\times A_2\times\cdots \\
	&\equiv& \{(a_i)_{i\in I}|\forall i\in I, a_i\in A_i\} \\
\end{matrix}$$

- 예를 들어보자.
	- $I=\\{1,2\\},F=\\{\\{a,b\\},\\{c,d\\}\\}$라고 할 때, $\prod F$를 구하라.

$$\begin{matrix}
	\prod F &\equiv& A_1\times A_2 \\
	&\equiv& \{(a,c), (a,d), (b,c), (b,d)\} \\
	&\equiv& \{(\alpha_1, \alpha_2)|\alpha_1\in A_1, \alpha_2\in A_2\} \\
\end{matrix}$$

- 이 예제를 일반화 시킨 것이 위에 있는 식이다.

## 출처
1. 이상엽Math
2. 수학의 즐거움, Enjoying Math