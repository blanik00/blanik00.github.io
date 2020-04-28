---
title: 'Taylor Series'
date: 2020-04-13
permalink: /posts/2020/04/13/taylor_series
category:
  - posts
---

## 테일러 급수  
테일러 급수(Taylor Series) 또는 테일러 전개(Taylor Expansion)은 어떤 함수 $f(x)$를 우리가 다루기 쉬운 다항함수 형태로 바꾸어 준다.  
    
$f(x)=p\_{\\infty}(x)$    
$p\_n(x)=f(a)+f'(a)(x-a)+{f\'\'(a)\\over 2!}(x-a)^2+...+{f^{(n)}(a)\\over n!}(x-a)^n$    
$\\qquad\\quad=\\Sigma\_{k=0}^{n}{f^{(k)}(a)\\over k!}(x-a)^k$    
    
근사다항식의 차수가 높으면 높을수록 $p\_n(x)$는 $f(x)$를 잘 근사하게 된다.    
    
주의해야 할 사항은 모든 $x$에 대해서 잘 근사하는 것이 아니라 $x=a$ 근처에서만 잘 근사한다는 것이다. 즉, $x$가 $a$로부터 멀어지면 멀어질수록 $f(x)=p(x)$는 큰 오차를 갖게 된다.    
    
그렇다면 위에서 봤던 $p\_n(x)$는 어떻게 구한 것일까    
    
테일러 급수는 미적분의 기본 정리로부터 출발한다.    
    
$\\int\_a^xf'(t)dt=f(x)-f(a)$    
$f(x)=f(a)+\\int\_a^xf'(t)dt$    
    
이제 우변의 마지막 항인 $\\int\_a^xf'(t)dt$를 부분적분을 활용해 바꿔줄 것이다.    
    
$\\int\_a^xf'(t)dt=\\int\_a^x1\\cdot f'(t)dt$    
$\\qquad\\qquad =\[(t+c)f'(t)dt\]\_a^x-\\int\_a^x(t+c)f\'\'(t)dt$    
    
여기서 $c$는 적분상수이기 때문에 우리가 원하는 값을 넣을 수 있다. $c$에 $-x$를 대입한다.  

$\\qquad\\qquad =\[(t-x)f'(t)dt\]\_a^x-\\int\_a^x(t-x)f\'\'(t)dt$    
$\\qquad\\qquad =(x-x)f'(x)-(a-x)f'(a)-\\int\_a^x(t-x)f\'\'(t)dt$    
$\\qquad\\qquad =(x-a)f'(a)-\\int\_a^x(t-x)f\'\'(t)dt$    
    
정리하면 다음과 같다.    
    
$p\_1(x)=f(a)+(x-a)f'(a)-\\int\_a^x(t-x)f\'\'(t)dt$    
    
마찬가지로 마지막 항인 $-\\int\_a^x(t-x)f\'\'(t)dt$를 부분적분을 활용해 바꿔줄 것이다.    
$-\\int\_a^x(t-x)f\'\'(t)dt=-(\[{(t-x)^2\\over 2}f\'\'(t)\]\_a^x-\\int\_a^x{(t-x)^2\\over 2}f\'\'\'(t)dt)$    
$\\qquad\\qquad\\qquad\\qquad ={(x-a)^2 \\over 2}f\'\'(a)+\\int\_a^x{(t-x)^2\\over 2}f\'\'\'(t)dt$    
    
정리하면 다음과 같다.    
    
$p\_2(x)=f(a)+(x-a)f'(a)+{(x-a)^2 \\over 2}f\'\'(a)+\\int\_a^x{(t-x)^2\\over 2}f\'\'\'(t)dt$    
    
마찬가지로 마지막 항인 $\\int\_a^x{(t-x)^2\\over 2}f\'\'\'(t)dt$를 부분적분을 활용해 바꿔줄 것이다.    
    
$\\int\_a^x{(t-x)^2\\over 2}f\'\'\'(t)dt=\[{(t-x)^3\\over 2\\cdot 3}f\'\'\'(t)\]\_a^x-\\int\_a^x{(t-x)^3\\over 2\\cdot 3}f\'\'\'\'(t)dt$    
$\\qquad\\qquad\\qquad\\quad ={(x-a)^3 \\over 2\\cdot 3}f\'\'\'(a)-\\int\_a^x{(t-x)^2\\over 2\\cdot 3}f\'\'\'\'(t)dt$    
    
정리하면 다음과 같다.    
    
$p\_3(x)=f(a)+(x-a)f'(a)+{(x-a)^2 \\over 2}f\'\'(a)+{(x-a)^3 \\over 2\\cdot 3}f\'\'\'(a)-\\int\_a^x{(t-x)^2\\over 2\\cdot 3}f\'\'\'\'(t)dt$    
    
이 정도 해보면 패턴이 눈에 보일 것이다. $p\_n(x)$는 다음과 같다.    
    
$p\_n(x)=f(a)+f'(a)(x-a)+{f\'\'(a)\\over 2!}(x-a)^2+...+{f^{(n)}(a)\\over n!}(x-a)^n$    
$\\qquad\\quad=\\Sigma\_{k=0}^{n}{f^{(k)}(a)\\over k!}(x-a)^k$    

참고로 테일러 급수는 보통 $a$에 0을 넣어서 사용하는데, 이를 매클로린 급수(Maclaurin Series)라고 한다.    

또한, 일반적으로 테일러 급수는 1차 또는 2차까지만 하는 경우가 많다. 1차, 2차 다항함수로 근사할 경우에는    
    
$f(x)\\approx p\_1=f(a)+(x-a)f'(a)+Q\_2(x)$    
$f(x)\\approx p\_2=f(a)+(x-a)f'(a)+{(x-a)^2 \\over 2}f\'\'(a)+Q\_3(x)$    
    
와 같이 놓고, $Q(x)$를 0으로 간주해 무시한다. 이 경우, $f(x)$를 무한차수 다항함수로 근사하는 것 보다는 근사오차가 크지만, $x$가 충분히 $a$에 가까운 경우에는 근사오차가 거의 없다.  

## 테일러 급수가 필요한 이유

1. 잘 모르거나 복잡한 함수를 다루기 쉽고 이해하기 쉬운 다항함수로 대체  
2. 함수의 특성을 분석하기 용이

## 예시 - $e$ 
$e^x = 1 + {x \over 1!} + {x^2 \over 2!} + {x^3 \over 3!} + ...$  
$\quad =\sum_{k=0}^{\infty}{x^k \over k!}$

## 정리
- 매클로린 급수  
  $f(x)=\sum_{k=0}^{\infty}{f^{(k)}(0) \over k!}x^k$  
- 테일러 급수  
  $f(x-a)=\sum_{k=0}^{\infty}{f^{(k)}(a) \over k!}(x-a)^k$