---
title: '1.5 집합의 크기'
date: 2020-10-22
permalink: /lecture/2020/10/22/set_theory_cardinality
category:
  - lecture
tags:
  - 1. 집합론
---

## Intro
- 집합의 크기를 탐구함에 있어서, 대상이 되는 집합의 크기를 파악하는 것은 기초 중의 기초

- 집합의 크기를 파악할 때 함수의 전사, 단사, 전단사를 유용하게 사용

## 유한, 무한집합
- 무한집합이 수학사에서 조명을 받은 것은 비교적 최근의 일이다. 기존의 상식에서는 "전체는 그것의 부분 보다는 크다"는 것이 있었다. 하지만 "긴 선분에 포함된 점의 갯수가 결코 짧은 선분에 포함된 점의 갯수보다 많다고 할 수 없다"는 의문이 제시되었다. 이처럼 무한집합은 갯수를 파악해서 집합의 크기를 논한다는 것이 비효과적이다. 그 후로 수학자들은 집합의 크기를 갯수를 세는 방법 말고 어떻게 표현할 것인가를 고민하기 시작했다. 200년이 지난 후, 수학자 데데킨트에 의해 전단사 함수를 이용한 집합의 크기 측정 방법이 제시되었다. 

- $f:X\rightarrow Y$가 전단사 함수

   - 집합 $X,Y$는 유한집합 : 집합 $X,Y$의 원소의 갯수가 같다. 

   - 집합 $X,Y$는 무한집합 : 집합 $X,Y$의 집합의 크기가 같다. 

### 1. 동등(Equipotent)
- 두 집합 $X$, $Y$에 대하여 전단사함수 $f:X\rightarrow Y$가 존재하면 $X$와 $Y$는 동등이다.

- $X\approx Y$ 또는 $f:X\approx Y$

- 동등은 동치 관계의 특수한 케이스

- 유한집합에서 동등은 원소의 갯수가 같다고, 무한집합에서는 집합의 크기가 같다고 해석할 수 있다.

### 2. 유한, 무한집합
- 집합 $X$의 적당한 진부분집합 $Y$가 $X$와 동등하다면 $X$는 무한집합이다.

- 그리고 무한집합이 아닌 집합을 유한집합이라고 한다.

### 예시
- $(0,1)\approx \mathbb{R}$

- 두 단계에 거쳐 증명할 수 있다.

1. $(0,1)\approx(-1,1)$
   $$f:(0,1)\rightarrow(-1,1), f(x)=2x-1$$

   - 함수 $f$는 전단사(동등하다)

2. $(-1,1)\approx\mathbb{R}$
   $$f:(-1,1)\rightarrow\mathbb{R}, f(x)={x\over 1-x^2}$$

- -1을 대입하면 음의 무한대로, 1을 대입하면 양의 무한대로 발산한다.

### 여러가지 정리
1. 공집합 $\emptyset$은 유한집합이다.
   - 무한집합은 진부분집합이 있어야 만들 수 있는데, 공집합은 진부분집합이 없다.

2. 무한집합을 포함하는 집합은 무한집합이다.

3. 유한집합의 모든 부분집합은 유한집합이다.

4. 전단사함수 $f:X\rightarrow Y$에 대하여(동등)
   - $X$가 무한함수이면 $Y$도 무한함수이다.

   - $X$가 유한함수이면 $Y$도 유한함수이다.

5. 무한집합 $X$의 부분집합 $Y$가 유한하면, $X-Y$는 무한집합이다.

## 가부번, 비가부번집합
- 무한집합에서도 급이 있는데, 이 내용은 집합의 급을 나누는 첫 번째 기준이다.

1. 가부번집합(denumerable set)
   - 가(가능하다), 부(붙이다), 번(번호)

   - 집합 $X$가 $X\approx \mathbb{N}$일 때, $X$를 가부번집합이라고 한다.

   - 즉, 번호를 붙일 수 있는 집합

   - $\mathbb{N}$(자연수)가 대표적인 가부번집합이다.

   - 자연수는 원소들에 숫자를 부여할 수 있다.($1\rightarrow1, 2\rightarrow2, 3\rightarrow3$)

2. 비가부번집합(nondenumerable set)
   - 집합 $X$가 $X\approx \mathbb{R}$일 때, $X$를 비가부번집합이라고 한다.

   - 번호를 붙일 수 없는 집합

   - $\mathbb{R}$(실수)가 대표적인 비가부번집합이다.

   - 실수는 원소들에 숫자를 부여할 수 없다. 예를 들어, 1.0에 1이라는 숫자를 부여한다면 2라는 숫자는 어떤 숫자에게 부여할 수 있을까? 어떤 숫자에 2를 부여하든, 1.0과 그 숫자 사이에 다른 실수가 있기 때문에 숫자를 부여하는 작업이 불가능하다.

3. 가산집합(countable set)
- 유한집합이나 가부번집합

### 여러가지 정리
1. 가산집합의 부분집합은 가산집합이다.

2. 가부번집합의 합집합은 가부번집합이다.

3. $\mathbb{N}\times\mathbb{N}$은 가부번집합이다.
   - $f:\mathbb{N}\times\mathbb{N}\rightarrow\mathbb{N}, f(n,m)=2^n3^m((n,m)\in \mathbb{N}\times\mathbb{N})$

   - $f$가 전단사이면 $\mathbb{N}\times\mathbb{N}$과 $\mathbb{N}$는 동등하다.

   - $f$는 단사이다.
      $$\begin{matrix}
         f(n_1,m_1)=f(n_2,m_2) &\Rightarrow& 2^{n_1}3^{m_1}=2^{n_2}3^{m_2} \\
         &\Rightarrow& 2^{n_1-n_2}=3^{m_2-m_1} \\
         &\Rightarrow& n_1-n_2=m_2-m_1=0 \\
         &\Rightarrow& n_1=n_2\land m_1=m_2 \\
         &\Rightarrow& (n_1,m_1)=(n_2,m_2) \\
      \end{matrix}$$

   - $f$는 전사이다.

4. $\mathbb{Q}$는 가부번집합이다.

5. $\mathbb{R}$의 부분집합 $(0,1)$은 비가부번집합이다.
   - 귀류법을 이용해서 증명한다. (가부번집합이라고 가정했다가, 이것이 모순이 있음을 밝혀 증명)

   - $(0,1)$이 가부번집합이라 하자.

   - $f:\mathbb{N}\rightarrow(0,1),f(n)=0.a_{n1}a_{n2}a_{n3}a_{n4}\cdots(a_{nm}\in\\{0,1,2,...9\\},m\in \mathbb{N})$

   - 즉, $f(1)$은 $0.a_{11}a_{12}a_{13}\cdots$이라는 소수에 대응되며, $f(2)$은 $0.a_{21}a_{22}a_{23}\cdots$이라는 소수에 대응된다. 

   - 우리는 $f$에 대응되지 않는 것이 존재한다는 것을 보일 것이다.

   - Let $z\in(0,1), z=0.z_1z_2z_3\cdots with\;z_k\neq a_{kk}, \forall k\in \mathbb{N}$ (즉, $z_k\neq a_{kk}, \forall k\in \mathbb{N}$가 되도록 $z$를 잡는다. 예를 들면, $k=1$일 때는 $z_1\neq a_{11}$이기 때문에 $z\neq f(1)$이고, $z_2\neq a_{22}$이기 때문에 $z\neq f(2)$이다.)

   - $\forall k\in\mathbb{N},f(k)\neq z$

   - $z\notin \mathbb{N}$

6. 모든 무리수 집합($\mathbb{I}$)은 비가부번집합이다.
   - $\mathbb{R}=\mathbb{Q}\cup\mathbb{I}$인데, $\mathbb{R}$은 비가부번집합이고, $\mathbb{Q}$는 가부번집합이다. 그러므로 $\mathbb{I}$는 비가부번집합이어야 한다.

7. $\mathbb{C}$는 비가부번집합이다.
   - $\mathbb{R}\subset\mathbb{C}$인데, $\mathbb{R}$이 비가부번집합이므로 $\mathbb{C}$도 비가부번집합이다.

8. 자연수, 정수, 유리수 집합은 가부번집합이고, 실수, 무리수, 복소수 집합은 비가부번집합이다. 가부번집합과 가부번집합의 연산 결과는 대부분 가부번집합이다.(여기서 대부분이라고 말하는 이유는 예외가 있기 때문) 하지만 비가부번집합이 그 연산에 끼어들면 비가부번집합이 된다.

## 기수
- 우리는 집합의 크기에 대해 다루고 있다. 지금까지는 우리가 이미 알고 있는 집합 $\mathbb{N}, \mathbb{R}$과 동등한가 동등하지 않은가를 기준으로 간접적으로 집합의 크기를 가늠해봤다. 하지만 집합의 크기를 기호 혹은 숫자로 표현하고자 하는 욕구가 사라지는 것은 아니다. 유한집합에서는 집합의 크기를 그 집합에 포함된 원소의 갯수로 나타낼 수 있다. 즉, 자연수에 대응시킬 수 있다. 무한집합도 그렇게 할 수 있지 않을까라는 발상에서 이 개념이 생겨났다. 그렇다고 무한집합에서만 쓰이는 것은 아니고, 유한집합과 무한집합 모두에서 사용할 수 있다.

- 기수 : 집합의 크기를 나타내는 기호 혹은 숫자

- $card\;A$ 또는 $\\#A$

### 기수의 성질
1. 각 집합 $A$에 대하여 $\\#A$는 유일하다.

2. $\\#A$에 해당하는 집합 $A$는 항상 있다.

3. $A=\emptyset\Leftrightarrow\\#A=0$

4. $A\approx\\{1,2,3,\cdots\\}\Rightarrow\\#A=k(k\in \mathbb{N})$

5. $A\approx B\Leftrightarrow \\#A=\\#B$

## 유한기수와 초한기수
- 유한기수 : 유한집합의 기수

- 무한기수 : 무한집합의 기수

### 대표적인 초한기수
- $\\#\mathbb{N}=\aleph_0$ : 가부번집합의 기수

- $\\#\mathbb{R}=\varsigma$ : 연속체의 기수

## $\\#A<\\#B$
- $A$는 $B$의 한 부분집합과 동등이고, $B$는 $A$의 어떠한 부분집합과도 동등이지 않다.

- 이는 임의의 두 초한기수의 순서에 대한 정의와도 같다(???)

1. $\\#A\le\\#A$

2. **$\star$칸토어 번슈타인 정리$\star$**
   - $A$가 $B$의 부분집합과 동등이고, $B$가 $A$의 부분집합과 동등이면 $A$와 $B$는 동등이다.($\\#A=\\#B$)

   - 즉, $\\#A\le\\#B\land\\#A\ge\\#B\Rightarrow\\#A=\\#B$

3. $\\#A\le\\#B$이고 $\\#B\le\\#C$이면 $\\#A\le\\#C$이다.

## 기수의 연산
- 기수와 자연수는 닮은 점이 있어 자연수를 연산하듯이 기수를 연산하는 것이 어느정도 가능하다.

### 기수 합
-  서로소인 두 집합 $A,B$의 기수를 각각 $a,b$라고 할 때, $a+b=\\#(A\cup B)$

### 기수 곱
- 집합 $A,B$의 기수를 각각 $a,b$라고 할 때, $ab=\\#(A\times B)$

### 연산법칙
- 임의의 기수 $x,y,z$에 대하여 다음이 성립한다.

1. 교환법칙
   - $x+y=y+x$

   - $xy=yx$

2. 결합법칙
   - $(x+y)+z=x+(y+z)$

   - $(xy)z=x(yz)$

3. 분배법칙
   - $x(y+z)=xy+xz$

## 여러가지 정리
1. $\aleph_0+\aleph_0=\aleph_0$
   - 첫 번째 $\aleph_0$에 해당하는 집합을 $\mathbb{N}_e$로 잡고, 두 번째 $\aleph_0$에 해당하는 집합을 $\mathbb{N}_o$로 잡으면 이 둘은 서로소이고, 기수의 합에 의해 $\mathbb{N}_e\cup\mathbb{N}_o$의 기수는 $\mathbb{N}$의 기수와 같다. $\mathbb{N}$의 기수는 $\aleph_0$이다.

2. $\varsigma+\varsigma=\varsigma$
   1. $\varsigma+\varsigma\le\varsigma$
      - $(0,1)\cup(1,2)\subseteq(0,2)$

      - $(0,2)\approx(0,1)$

   2. $\varsigma+\varsigma\ge\varsigma$
      - 자명

3. $\aleph_0+\varsigma=\varsigma$
   1. $\aleph_0+\varsigma\le\varsigma$
      -  $\aleph_0$에 해당하는 집합을 $\mathbb{N}$로 잡고, $\varsigma$에 해당하는 집합을 $(0,1)$로 잡으면, 이 둘은 서로소이고, 합집합을 하면 $\mathbb{N}\cup(0,1)\subseteq \mathbb{R}$이다. $\mathbb{R}\approx (0,1)$이므로 위 수식은 참이다.

   2. $\aleph_0+\varsigma\ge\varsigma$
      - 자명

4. $\aleph_0\aleph_0=\aleph_0$

5. $\varsigma\varsigma=\varsigma$
   1. $\varsigma\varsigma\le\varsigma$
      - $f:(0,1)\times(0,1)\rightarrow(0,1)$

      - $f(0.x_1x_2x_3\cdots,0,y_1y_2y_3\dots)=0.x_1y_1x_2y_2x_3y_3\cdots$

      - $\Rightarrow f는\;단사$

      - $\therefore(0,1)\times(0,1)\subseteq(0,1)$

   2. $\varsigma\le\varsigma\varsigma$
      - $g:(0,1)\rightarrow(0,1)\times(0,1),g(x)=(x,0.5)\in(0.1,0.1)$

      - ex) $g(0.1)=(0.1,0.5)$

      - $\therefore(0,1)\subseteq(0,1)\times(0,1)$

6. $\aleph_0\varsigma=\varsigma$
   1. $\aleph_0\varsigma\le\varsigma$
      - $\aleph_0\varsigma\le\varsigma\varsigma\le\varsigma$
   2. $\aleph_0\varsigma\ge\varsigma$
      - 자명

### 주의
- $\aleph_0+\aleph_0=\aleph_0=\aleph_0+1\Rightarrow \aleph_0\neq q$

- $\aleph_0\aleph_0=\aleph_0=\aleph_0\cdot1\Rightarrow \aleph_0\neq1$

- 즉, 기수의 연산이 자연수와 닮은 점이 있지만, 다른 점도 있다는 사실에 주의해야 한다.

## 기수의 지수
- 집합 $A,B$에 대하여 $\\#A=m,\\#B=n$일 때,

1. $B^A=\\{f\|f:A\rightarrow B\\}$

2. $\\#(B^A)=n^m$

### 예시
- $A=\\{1,2,3\\}, B=\\{4,5\\}$

- $B^A=f:A\rightarrow B$의 총 갯수$\Rightarrow 2\times 2\times 2=2^3=8=\\#B^{\\#A}$

### 특수한 축양형
- $B=\\{0,1\\}$일 때, $B^A=\\{0,1\\}^A$이다. 이를 축약하여 $2^A$로 표기하기도 한다.

## 여러가지 정리
1. 집합 $X$에 대하여 $\\#X=x$일 때, $\\#P(X)=2^x$이다.
   - $\\{0,1\\}^X=2^x$

2. 기수 $x,y,z$에 대하여
   1. $x^yx^z=x^{y+z}$
      - $X=\\{1,2\\},Y=\\{3\\},Z=\\{4,5,6\\}$

      - $\\#X=2,\\#Y=1,\\#Z=3$

      - $\\#X^Y=2$

      - $\\#X^Z=2^3=8$

      - $\\#X^{Y\cup Z}=2^4=16$

   2. $(x^y)^z=x^{yz}$
      - $(x^y)=2, (x^y)^z=2^3=8$

      - $x^{yz}=2^3=8$

   3. $(xy)^z=x^zy^z$
      - $xy=2,(xy)^z=8$

      - $x^z=8,y^z=1,x^zy^z=8$

3. **$\varsigma=\aleph_0^{\aleph_0}=\varsigma^{\aleph_0}$**
   - 앞에서 $\aleph_0$를 $\varsigma$로 바꾸는 것은 거의 불가능하다고 했었는데, 이렇게 지수로 올려주면 $\varsigma$로 바꿀 수 있다.

   - $\varsigma=2^{\aleph_0}=\aleph_0^{\aleph_0}$임을 보이고, $\varsigma=\varsigma^{\aleph_0}$임을 통해서 증명할 것이다.

   1. $\varsigma=2^{\aleph_0}$
      - $2^{\aleph_0}$는 자연수 집합의 멱집합의 기수와 같다.
      
      1. $\varsigma\le2^{\aleph_0}(=\\#(P(\mathbb{N})))$
        
            - $f:(0,1)\rightarrow P(\mathbb{N})$

            - $f(0.a_1a_2a_3\cdots)=\\{a_n\times 10^n\| n,a_n\in \mathbb{N}\\}$

            - ex) $f(0.109372)=\\{10, 9000, 30000, 700000, 2000000\\}\in P(\mathbb{N})$

            - $f$는 단사이기 때문에 $\varsigma\le2^{\aleph_0}$임이 증명된다.
   
        2. $2^{\aleph_0}\le\varsigma$
            - $g:\\{0,1\\}^\mathbb{N}\rightarrow(0,1)$

         - $g(f)=0.f(1)f(2)f(3)\cdots\in(0,1)$

         - $g$는 단사

   2. $2^{\aleph_0}=\aleph_0^{\aleph_0}$
      $$\begin{matrix}
         &=& \{f\|f:\mathbb{N}\rightarrow\{0,1\}\}\subseteq\{f\|f:\mathbb{N}\rightarrow\mathbb{N}\} \\
         && (\{f\|f:\mathbb{N}\rightarrow\mathbb{N}\}의\;기수는\; \aleph_0^{\aleph_0}) \\
         &=& \{f\|f:\mathbb{N}\rightarrow\mathbb{N}\}\subseteq \{f\|f:\mathbb{N}\times\mathbb{N}\} \\
         &=& \{f\|f:\mathbb{N}\times\mathbb{N}\}\subseteq P(\mathbb{N}\times\mathbb{N}) \\
      \end{matrix}$$

      - $P(\mathbb{N}\times\mathbb{N})$의 기수는 $2^{\aleph_0\aleph_0}$이며, $2^{\aleph_0\aleph_0}=2^{\aleph_0}$이다.

      - $2^{\aleph_0}\le\aleph_0^{\aleph_0}\le2^{\aleph_0}$

      - $2^{\aleph_0}=\aleph_0^{\aleph_0}$

   3. $\varsigma=\varsigma^{\aleph_0}$
       $$\begin{matrix}
         s^{\aleph_0} &=&  (2^{\aleph_0})^{\aleph_0}(\because \varsigma=2^{\aleph_0}) \\
         &=&  2^{\aleph_0\aleph_0} \\
         &=&  2^{\aleph_0} \\
         &=&  \varsigma \\
      \end{matrix}$$

4. $2^\varsigma=\aleph_0^\varsigma=\varsigma^\varsigma$
   1. $2^\varsigma=\aleph_0^\varsigma$
      $$\begin{matrix}
         \{f|f:\mathbb{R}\rightarrow \{0,1\}\} (기수는\;2^{\varsigma}) &\subseteq&  \{f|f:\mathbb{R}\rightarrow \mathbb{N}\} (기수는\;\aleph_0^{\varsigma}) \\
         &\subseteq& \{f|f:\mathbb{R}\times\mathbb{N}\}  \\
         &\subseteq& P(\mathbb{R},\mathbb{N}) (기수는\;2^{\varsigma\aleph_0}) \\
         && 2^{\varsigma\aleph_0}=2^\varsigma \\
         && 2^\varsigma\le\aleph_0^\varsigma\le2^\varsigma \\
         &\therefore& 2^\varsigma=\aleph_0^\varsigma \\
      \end{matrix}$$

   2. $2^\varsigma=\varsigma^\varsigma$
      $$\begin{matrix}
         \varsigma^\varsigma &=& (2^{\aleph_0})^\varsigma \\
         &=& 2^{\aleph_0\varsigma}
         &=& 2^{\varsigma}
      \end{matrix}$$