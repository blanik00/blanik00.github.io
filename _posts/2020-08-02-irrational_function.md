---
title: '무리함수(Irrational Function)'
date: 2020-08-02
permalink: /posts/2020/08/02/irrational_function
category:
  - posts
---

## 무리함수
- 무리수 : 분수로 나타낼 수 없는 수
	- $\sqrt{2}, \sqrt{3}, \pi$
	- $\pi$와 같은 특수한 수를 제외하고는 $\sqrt{}$가 있다.

- 무리식 : 근호 안에 문자가 포함된 식 중 유리식이 아닌 것(**근호 안에 있는 것은 0보다 크거나 같다.**)

- 무리함수 : $y=f(x)$, $f(x)$는 $x$에 관한 무리식이다.(**근호 안에 있는 것은 0보다 크거나 같다.**)

## $y=\sqrt{ax}(a>0, x\ge 0)$
![](https://user-images.githubusercontent.com/26649034/89093644-3d79d980-d3f7-11ea-8783-39c4a17ad189.png)
- **무리함수의 정의역은 근호 안을 보면 알 수 있다.**
	- 근호 안은 0크거나 같아야 한다.
	- $a>0$이면 $x\ge 0$이 정의역이 된다.
	- $a<0$이면 $x\le 0$이 정의역이 된다.
	- 이 경우는 $a>0$이므로, 정의역은 $x\ge 0$이다.

- $y={1\over a}x^2(a>0,x\ge 0)$의 역함수이다.

- 위 그래프는 $a=2$를 넣어 그린 것

- 즉, 이들의 관계는 다음과 같다.
	1. 역함수
	2. $y=x$를 기준으로 대칭

## $y=\sqrt{ax}, y=-\sqrt{ax}(a\neq 0)$
![](https://user-images.githubusercontent.com/26649034/89093646-3eab0680-d3f7-11ea-8b2d-669854408622.png)

- 두 함수는 $a>0$, $a<0$으로 나눠볼 수 있다. 즉 총 네 개의 그래프가 나오며, 각각은 사분면을 하나씩 차지한다.

- 모든 그래프는 원점을 지난다.

	- 4사분면에 있는 것은 $y=\sqrt{ax}(a>0, x\ge 0)$를 x축 대칭한 것($y$에 $-y$ 대입)
	- 2사분면에 있는 것은 $y=\sqrt{ax}(a>0, x\ge 0)$를 y축 대칭한 것($x$에 $-x$ 대입)
	- 3사분면에 있는 것은 $y=\sqrt{ax}(a>0, x\ge 0)$를 원점 대칭한 것($x$에 $-x$, $y$에 $-y$ 대입)

- 그래프의 모양을 생각해보면 정의역과 치역을 쉽게 구할 수 있다.
	- 1사분면($y=\sqrt{ax}(a>0, x\ge 0)$)
		- 정의역 : $\\{x|x\ge 0\\}$
		- 치역 : $\\{y|y\ge 0\\}$
	- 4사분면($y=\sqrt{ax}(a>0, x\ge 0)$)
		- 정의역 : $\\{x|x\ge 0\\}$
		- 치역 : $\\{y|y\le 0\\}$
	- 2사분면($y=\sqrt{ax}(a<0, x\le 0)$)
		- 정의역 : $\\{x|x\le 0\\}$
		- 치역 : $\\{y|y\ge 0\\}$
	- 4사분면($y=\sqrt{ax}(a<0, x\le 0)$)
		- 정의역 : $\\{x|x\le 0\\}$
		- 치역 : $\\{y|y\le 0\\}$

- **근호는 반드시 양수이기 때문에 치역은 근호 앞의 부호가 결정한다.**
	- 부호가 +이면 치역은 $\\{y|y\ge 0\\}$
	- 부호가 -이면 치역은 $\\{y|y\le 0\\}$

## $y=\sqrt{a(x-p)}+q, y=-\sqrt{a(x-p)}+q(a\neq 0)$
![](https://user-images.githubusercontent.com/26649034/89093647-3f439d00-d3f7-11ea-8f20-d2910fb75482.png)

- $y=\sqrt{ax}, y=-\sqrt{ax}(a\neq 0)$을 $x$축으로 $p$만큼, $y$축으로 $q$만큼 평행 이동시킨 것이다.($x$에 $x-p$ 대입, $y$에 $y-q$ 대입)

- 정의역과 치역도 그에 맞게 변경시키면 된다.

- **무리함수들 또한 유리함수와 역함수 관계를 가진다는 것을 기억해야 한다.**