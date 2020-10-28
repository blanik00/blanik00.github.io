---
title: '1.4 함수'
date: 2020-10-21
permalink: /lecture/2020/10/21/set_theory_function
category:
  - lecture
tags:
  - 1. 집합론
---

## 함수
- 관계의 특수한 케이스

- 정의 : 다음을 만족하는 $X$ $Y$로의 관계 $f:X\rightarrow Y$
	1. $\forall x\in X, \exists y\in Y, s.t.\;(x,y)\in f$

	2. $(x,y_1)\in f, (x,y_2)\in f\Rightarrow y_1=y_2$

- $(x,y)\in f$는 $y=f(x)$로도 쓴다.

### 예시
$X=\\{1,2,3\\}, Y=\\{a,b,c\\}$일 때, 다음 관계가 함수인지 확인하라.

1. $f_1=\\{(1,a), (1,b), (2,b), (3,c)\\}$
	- 2번 조건을 위반

2. $f_1=\\{(1,a), (2,b)\\}$
	- 1번 조건을 위반

3. $f_1=\\{(1,a), (2,a), (3,b)\\}$
	- 함수

함수 $f:X\rightarrow Y$에서 $y=f(x)$일 때,
1. $y$를 $f$에 의한 $x$의 상
2. $x$를 $f$에 의한 $y$의 원상
3. $X$를 $f$의 정의역 : $Dom(f)$
4. $Y$를 $f$의 공역
5. $\\{f(x)\| x\in X\\}=f(X)$를 $X$의 치역 : $Rng(f)$
라 한다.

위에서 들었떤 예에서,
- $Dom(f_3)=\\{1,2,3\\}=X$
- $Rng(f_3)=\\{a,b\\}\subset Y$
- 1의 상 : $a$
- a의 원상 : $1,2$

### 함수식이 같아도 정의역이 다르면 다른 함수다.
- $f(x)=x^2, Dom(f)=\mathbb{R}$

- $g(x)=x^2, Dom(g)=\mathbb{C}$

- $f\neq g$

-  참고
   - $\mathbb{N}$ : 자연수

   - $\mathbb{Z}$ : 정수

   - $\mathbb{Q}$ : 유리수

   - $\mathbb{R}$ : 실수

   - $\mathbb{C}$ : 복소수

- 그러므로 정의역을 조절해서(범위 줄이기 혹은 늘리기) 다른 함수를 만드는 것도 얼마든지 가능하다.

- 함수 $f:X\rightarrow Y$에 대하여 $A\subset X$일 때, 
   - $f\|_A$는 $X$를 $A$로 축소한 함수
      - $\\{(x,y)\in f\|x\in A\\}$

- $g=f\|_A$이면 $g$는 $f$의 $A$에서의 확대함수

### 예시
- $A=\\{1,2\\}, B=\\{1,2,3\\}, Y=\\{a,b,c\\}$

- $f=\\{(1,a), (2,b), (3,c)\\}$
   - $f:A\rightarrow Y$

- $g=\\{(1,a), (2,b)\\}$
   - $g:B\rightarrow Y$

- $g=f\|_A$

## 함수의 성질
- 함수 $f:X\rightarrow Y$에 대하여

1. 전사(onto, surjective) : $Rng(f)=Y$

2. 단사(one-to-one, injective) : $x_1\neq x_2\in X\Rightarrow f(x_1)\neq f(x_2)$

3. 전단사(=**일대일대응**) : 전사이고 단사인 함수

![image](https://user-images.githubusercontent.com/26649034/97255251-8b19ad00-1853-11eb-9be1-4e441bdcaf05.png)

## 여러가지 함수
### 고등학교 교육과정 내
1. 항등함수 : $\forall x\in X, I_X(x)=x$
      - 관계에서 배운 대각관계가 항등함수다.
2. 상수함수 : $\exists y_0\in Y, f(X)=y_0$

3. **역함수** : **전단사**인 $f:X\rightarrow Y$에 대해 $f^{-1}:Y\rightarrow X$

4. 두 함수 $f:X\rightarrow Y,g:Y\rightarrow Z$일 때, 합성함수 $(g\circ f)(x)=g(f(x))$

### 합성함수의 성질
- $g\circ f\neq f\circ g$

- $(h\circ g)\circ f=h\circ(g\circ f)$

- $f^{-1}\circ f=I_X$

- $f\circ f^{-1}=I_Y$

- $f, g$가 모두 단사$\Rightarrow g\circ f$는 단사

- $g\circ f$는 단사 $\Rightarrow f$는 단사

- $f, g$가 모두 전사$\Rightarrow g\circ f$는 전사

- $g\circ f$는 전사 $\Rightarrow g$는 전사

### 고등학교 교육과정 외
- 집합 $A(\neq\emptyset)$가 $A\subset X$일 때,

1. 포함함수
   - 항등함수의 축소함수($I_X\|_A$)

   - $\forall x\in A, i:A\rightarrow X$가 $i(x)=x(\in A)$

2. 특성함수(characteristic function, indicator function)
   - 하나의 값이 특정 집합에 포함되는지 안되는지를 알려주는 함수

   - $\forall x\in X, \chi_A:X\rightarrow \\{0,1\\}$가 

   $$\chi_A=
   \begin{cases}
   1, & x\in A \\
   0, & x\notin A
   \end{cases}$$

   - 조합론, 확률론, 해석학 등 많은 분야에서 사용된다.

- 선택함수
   - 집합 $X(\neq\emptyset)$의 부분집합들의 집합족을 $\\{A_i\\}$이라할 때, 모든 $i\in I$에 대하여 $f(A_i)\in A_i$로 정의되는 함수 $f:\\{A_i\\}\rightarrow X$

   - 선택공리 배울 때 중요

### 선택함수 예시
- $X=\\{1,2,3,4,5\\}$

- $A_1=\\{1,2,3\\}, A_2=\\{2,3,4\\}, A_3=\\{4,5\\}$

- $f_1=\\{(A_1,2), (A_2, 4), (A_3,5)\\}$
   - 집합족 $A_i$ 모두 함수에 포함되며, $2,\in A_1, 4\in A_4, 5\in A_3$이기 때문에 선택함수가 맞다.

- $f_2=\\{(A_1,1), (A_2, 2), (A_3,3)\\}$
   - 집합족 $A_i$ 모두 함수에 포함되지만, $2,\in A_1, 4\in A_4, 5\notin A_3$이기 때문에 선택함수가 아니다.

## 여러가지 정리
1. 함수 $f$에 대하여 역함수 $f^{-1}$가 존재하면 $f$는 전단사이다.
   - 함수 $f$는 전단사이면 역함수 $f^{-1}$가 존재한다는 사실을 위에서 배웠다. 이번에는 그 반대를 보일 것이다.

   - $f$는 전사
      $$\begin{matrix}
         f^{-1}이\; 존재 &\Rightarrow& \forall y\in Y, \exists x, s.t. (y,x)\in f^{-1} \\
         &\Rightarrow& \forall y\in Y, \exists x, s.t. (x,y)\in f \\
         &\Rightarrow& \forall y\in Rng(f) \\
         &\Rightarrow& Y\subset Rng(f) \\
         &\Rightarrow& Y=Rng(f)(\because Rng(f)\subset Y) \\
      \end{matrix}$$

   - $f$는 단사
      - $f(x_1)=f(x_2)\Rightarrow x_1=x_2$를 보이고, 그 대우($x_1\neq x_2\Rightarrow f(x_1)\neq f(x_2)$) 또한 참임을 통해 증명

   $$\begin{matrix}
      f(x_1)=f(x_2)=y &\Rightarrow& (x_1,y)\in f\land  (x_2,y)\in f \\
      &\Rightarrow& (y, x_1)\in f^{-1}\land  (y, x_2)\in f^{-1} \\
      &\Rightarrow& x_1=x_2
   \end{matrix}$$

2. 합성함수 $g\circ f$가 단사이면 $f$는 단사이다.
   - $f:X\rightarrow Y, g:Y\rightarrow Z$

   - $x_1, x_2\in X, f(x_1)=f(x_2)$라 하자.

   $$\begin{matrix}
      &\Rightarrow& g(f(x_1))=g(f(x_2)) \\
      &\Rightarrow& (g\circ f)(x_1)=(g\circ f)(x_2) \\
      &\Rightarrow& x_1=x_2(\because g\circ f\;is\; one-to-one;)
   \end{matrix}$$

   - 즉, $f(x_1)=f(x_2)\Rightarrow x_1=x_2$이므로 $f$는 단사이다.

3. 함성함수 $g\circ f$가 전사이면 $g$는 전사이다.
   - $f:X\rightarrow Y, g:Y\rightarrow Z$

   $$\begin{matrix}
      &\Rightarrow& \forall z\in Z, \exists x\in X s.t.\;(g\circ f)(x)=z \\
      &\Rightarrow& \forall z\in Z, \exists f(x)\in Y s.t.\;g(f((x))=z \\
      &\Rightarrow& g\;is\;onto
   \end{matrix}$$

4. 정수집합 $\mathbb{Z}$과 자연수집합 $\mathbb{N}$ 사이에는 일대일 대응이 존재한다.
   - 일대일 대응을 만들기 위한 함수 $f$를 어떻게 설정하는지가 중요. 특히나 이 경우에는 정의역은 양의 정수, 0, 음의 정수를 포함하고 있기 때문에 어떻게 해야 양의 정수와 일대일 대응을 만들지 고민해야 한다.

   - 이를 위해 $f:\mathbb{Z}\rightarrow \mathbb{N}$를 $$f(x)=\begin{cases}2x+1, & x\ge 0 \\ -2x, & x< 0\end{cases}$$이라 하자.

   1. $f$는 단사이다.
      - Case 1) 
      $$\begin{matrix}
         f(x_1)=f(x_2) &\Rightarrow& 2x_1+1=2x_2+1 \\
         &\Rightarrow& x_1=x_2 \\
      \end{matrix}$$

      - Case 2) 
      $$\begin{matrix}
         f(x_1)=f(x_2) &\Rightarrow& -2x_1=-2x_2 \\
         &\Rightarrow& x_1=x_2 \\
      \end{matrix}$$

   2. $f$는 전사이다.
      - $\mathbb{N}_e$ : 양의 짝수 집합

      - $\mathbb{N}_o$ : 양의 홀수 집합

      - $\\{\mathbb{N}_e, \mathbb{N}_o\\}$는 $\mathbb{N}$의 분할이다.

      - Case 1) $\forall 2n+1 \in \mathbb{N}_o, \exists n\in \mathbb{Z}\;s.t.\;f(n)=2n+1$

      - Case 2) $\forall -2m \in \mathbb{N}_e, \exists m\in \mathbb{Z}\;s.t.\;f(m)=-2n$

## 집합의 함수
- 우리는 지금까지 정의역 $X$의 원소를 대응시키는 함수를 봐왔다.

- 지금부터는 정의역 $X$의 부분집합을 대응시키는 함수를 배운다.

- 함수 $f:X\rightarrow Y$에서 $A\subset X$이고, $B\subset Y$일 때 다음이 성립한다.
   1. $f$에 대한 $A$의 상
      - $f(A)=\\{f(x)\in Y\| x\in A\\}\subset Y$
      
   2. $f$에 대한 $B$의 역상
      - $f^{-1}(B)=\\{x\in X\| f(x) \in B\\}\subset X$

### Example
- $f:\mathbb{R}\rightarrow \mathbb{R}$가 $f(x)=x^2$이라 하자.

- $A=\\{-1,0,1,2\\}\Rightarrow f(A)=\\{0,1,4\\}$

- $B=\\{0,1,4\\}\Rightarrow f^{-1}(B)=\\{-2,-1, 0,1,2\\}$

- $A$의 상은 $\\{0,1,4\\}$이다. 이것은 $B$와 같다. 그 $B$에 대해 역상을 만든 결과 $\\{-2,-1, 0,1,2\\}$이 나왔다. 그런데 $A$와 $f^{-1}(B)$의 관계를 보면 $A\subset f^{-1}(B)$임을 알 수 있다.(일반적으로 상의 원소의 갯수는 원래 집합보다 작아지고, 역상의 원소의 갯수는 원래 집합보다 커지기 때문이다.)

- 그렇다면 $A=f^{-1}(B)$를 만족하려면 추가적으로 어떤 조건이 필요할까? 뒤에서 배운다.

## 여러가지 정리
- 함수 $f:X\rightarrow Y$에서 $A\subset X$이고 $B\subset Y$일 때, 다음이 성립한다.

1. $f(\emptyset_X)=\emptyset_Y$
   - 귀류법

   - $f(\emptyset_X)\neq\emptyset_Y$이라 하자.

   - $\forall y\in f(\emptyset_X), \exists x\in\emptyset_X\;s.t.\;f(x)=y$를 만족해야 한다. 하지만 $x\in \emptyset_X$를 만족할 수 없으므로 모순됨.

2. $\forall x\in X, f(\\{x\\})=\\{f(x)\\}$

3. $f^{-1}(f(A))=A\Leftrightarrow f는\;단사$
	- $f^{-1}(f(A))=A\Rightarrow f는\;단사$
		- $f$가 단사라는 것을 보이면 되므로, $f(x_1)=f(x_2)\Rightarrow x_1=x_2$임을 보이면 된다.

	      $$\begin{matrix}
	         A=\{x_1\} &\Rightarrow& f^{-1}(f(\{x_1\})) \\
	         &\Rightarrow& f^{-1}(\{f(x_1)\}) &(\because (2)) \\
	         &\Rightarrow& f^{-1}(\{f(x_2)\}) \\
	         &\Rightarrow& f^{-1}(f(\{x_2\})) \\
	         &\Rightarrow& \{x_2\} & (\because f^{-1}(f(A))=A) \\
	      \end{matrix}$$

	- $f^{-1}(f(A))=A\Leftarrow f는\;단사$
		- $f$는 단사라는 조건을 활용해 $f^{-1}(f(A))\subset A, A\subset f^{-1}(f(A))$임을 보이면 된다.

		- $A$ 집합이 $B$ 집합의 부분집합이 된다는 것을 증명하기 위해서는 $A$의 모든 원소들이 $B$에도 표함된다는 것을 보이면 된다.

			1. $f^{-1}(f(A))\subset A$
			$$\begin{matrix}
		         \forall x\in f^{-1}(f(A)) &\Rightarrow& f(x)\in f(A) & (\because x\in A) \\
		         &\Rightarrow& \exists x'\in A\;s.t.\;f(x)=f(x')\\
		         &\Rightarrow& x=x' & (\because f는\;단사) \\
		         &\Rightarrow& x\in A
		      \end{matrix}$$

			2. $A\subset f^{-1}(f(A))$
			$$\begin{matrix}
		         &\Rightarrow& \forall x\in A,f(x)\in f(A) & (\because x\in A) \\
		         &\Rightarrow& x\in f^{-1}(f(A)) & (\because A\subset f^{-1}(f(A)))\\
		      \end{matrix}$$

4. $f(f^{-1}(B))=B\Leftrightarrow g는\;전사$
	- $f(f^{-1}(B))=B\Rightarrow g는\;전사$
		- $g$가 단사라는 것을 보이면 되므로 치역과 공역이 같음을 보여야 한다.즉, $f(X)=Y$를 만족해야 한다.

	      $$\begin{matrix}
	         Y=f(f^{-1}(Y)) &\Rightarrow& Y=f(X)&(\because f^{-1}(Y)=X) \\
	      \end{matrix}$$

	- $f(f^{-1}(B))=B\Leftarrow g는\;전사$
		- $g$는 전사라는 조건을 활용해 $f(f^{-1}(B))\subset B, B\subset f(f^{-1}(B))$임을 보이면 된다.

			1. $f(f^{-1}(B))\subset B$
			$$\begin{matrix}
		          &\Rightarrow& \forall y\in f(f^{-1}(B)), \exists x\in f^{-1}(B)\;s.t.\;f(x)=y\\
		          &\Rightarrow& y\in B&(\because f(x)=y\land f(x)\in B) \\
		      \end{matrix}$$

			2. $B\subset f(f^{-1}(B))$
			$$\begin{matrix}
		         &\Rightarrow& \forall y\in B, \exists x\in f^{-1}(B)\;s.t.\;f(x)=y \\
		         &\Rightarrow& f(x)\in f(f^{-1}(B)) \\
		         &\Rightarrow& y\in f(f^{-1}(B)) \\
		      \end{matrix}$$