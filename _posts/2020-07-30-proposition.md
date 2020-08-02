---
title: '명제(Proposition)'
date: 2020-07-30
permalink: /lecture/2020/07/30/proposition
category:
  - lecture
tags:
  - 수2
---

## 명제와 조건
- 명제 : 참, 거짓을 판별할 수 있는 문장 또는 식
	- 2는 홀수이다. (거짓인 명제)
	- 3은 홀수이다. (참인 명제)
	- 나는 잘생겼다. (명제 아님)

- 조건($p$) : 미지수를 포함하는 문장 또는 식이 미지수의 값에 따라 참, 거짓이 결정되는 것
	- $x^2=4$의 경우, $x=2$일 때는 참이고, $x=3$일 때는 거짓임

- 진리집합($P$) : 조건 $p$를 참이 되게 하는 모든 원소들의 집합

## 명제와 조건의 부정
- $\sim p$ : $p$가 아니다.
	- 집합으로 나타내면 $p^c$

- $\sim(\sim p)=p$
	- 집합으로 나타내면 $(p^c)^c$

- 아래 목록에 있는 것들은 서로 부정이다.
	- $and\Leftrightarrow or$
	- $>\Leftrightarrow \le$
	- $=\Leftrightarrow \neq$
	- $a\le x\le b\Leftrightarrow x < a \;or\; x > b$

## $p\rightarrow q$의 참, 거짓
- 조건 두 개를 합치면 명제가 된다.($p\rightarrow q$)

- $P\subset Q$

	- $x=2$이면 $x^2=4$이다.
	- **이 명제가 참이 되기 위해서는 $p$의 진리집합이 $q$의 진리집합의 부분집합이어야 한다.**
	- $p$의 진리집합은 $\\{2\\}$이고, $q$의 진리집합은 $\\{2,-2\\}$이다.
	- 그러므로 이 명제는 참인 명제이다.

- $p$를 "가정"이라고 하고, $q$를 "결론"이라고 한다.

## 필요조건, 충분조건
- "$p$이면 $q$이다."가 참인 명제라면 화살표 두 개를 사용해서 $p\Rightarrow q$라고 표현한다.

- $P\subset Q$

- 이 때 $p$를 **충분조건**, $q$를 **필요조건**이라고 한다.
	- "$p$는 조건이 충분해서 조건이 필요한 $q$에게 나눠준다."라고 외우기
	- 예를 들어, "6의 배수이면 2의 배수이다."라는 명제를 생각해보자. 6의 배수는 "2의 배수 & 3의 배수"라는 두 조건을 만족시켜야 하며, 2의 배수는 "2의 배수"만 만족시키면 된다. 6의 배수의 조건이 더 까다로우므로(충분하므로) 6의 배수가 충분조건이 된다.

- $p$의 진리집합은 $q$의 진리집합의 부분집합이다.

- 필요충분조건
	- $p\Leftrightarrow q$
	- $P=Q$

- 명제는 집합으로 포함할 수 있다. 그래서 $p\rightarrow q$라는 명제를 아래와 같은 집합으로 표현하기도 한다.
	1. $A\cap B=A$
	2. $A\cup B=B$
	3. $A-B=\emptyset$
	4. $A\cup B^c=\emptyset$
	5. $A^c\supset B^c$
	6. $A^c\cup B=U$

## '모든' 또는 '어떤'을 포함한 명제
- **모든** $x$에 대하여 $p$이다.
	- $p$의 진리집합과 모든 $x$, 즉 $U$가 같으면 참이다.

- **어떤** $x$에 대하여 $p$이다.
	- $p$의 진리집합이 하나라도 있으면 참이다.

- **'모든'과 '어떤'은 서로 부정이다.**

## 역과 대우
- 역 : 가정과 결론을 바꾸는 것
	- $p\rightarrow q$의 역은 $q\rightarrow p$이다.

- 대우 : 가정과 결론을 바꾸고 부정함
	- $p\rightarrow q$의 대우은 $\sim q\rightarrow \sim p$이다.

![](https://w.namu.la/s/eaf398891d96c37b17685e9112c1cc79ce6e7362e1286f4b585c8be7c3cab2980ba072f3968cae89113d109dcafd059ea3946187571381e96a1c6874bf260d755029afd0013862b07731df955615d102a53b61daadbad33086db22fdd3f8780b)

빨간 선은 역, 파란 선은 대우

- 실제로 중요한 것은 **대우** 관계이다.
	- $p\rightarrow q$가 참이면 $P\subset Q$가 성립한다. 드모르간의 법칙에 의해 $Q^c\subset P^c$도 성립하며, 이는 $p\rightarrow q$의 대우 명제인 $\sim q\rightarrow \sim p$도 성립함을 나타낸다.

- **명제와 대우의 참, 거짓은 일치한다.**

## 삼단논법
- $p\Rightarrow q, q \Rightarrow r$이면 $p\Rightarrow r$이다.
	- $P\subset Q, Q\subset R$이면 $P\subset R$이다.