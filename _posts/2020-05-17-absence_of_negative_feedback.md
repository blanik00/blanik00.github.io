---
title: 'How to deal with Absence of Negative Feedback'
date: 2020-05-17
permalink: /posts/2020/05/17/absence_of_negative_feedback
category:
  - posts
---  

Implicit Feedback을 활용한 추천 시스템은 아마 unobserved data를 어떻게든 해결해야 할 것이다. 이 문제는 Explicit Feedback과 비교하면 명백하게 알 수 있다.  

점수가 1\~5점 사이에 분포해 있는 Explicit Feedback의 경우 1점은 "유저가 아이템을 좋아하지 않는다"는 것을 나타내며, 5점은 "유저가 아이템을 좋아한다"는 것을 나타낸다.  

하지만 Implicit Feedback의 경우 0점을 기록(ex. 유저가 해당 아이템을 구매한 적이 없음)하더라도 "유저가 해당 아이템을 좋아하지 않는다"고 말할 수 없다. 유저가 실제로 아이템을 좋아하지 않는 경우 이외에도 유저가 아이템을 인지하지 못했던 경우가 있기 때문이다. 이러한 문제를 부정적인 피드백의 부재(absence of negative feedback)라고 한다.  

만약 부정적인 피드백를 모두 포함시켜 학습을 시킨다면 부정적인 피드백의 수가 긍정적인 피드백보다 훨씬 많아 긍정적인 피드백 무시하는 방향으로 학습이 진행될 것이다. 반대로 부정적인 피드백를 모두 제외시킨다면 긍정적인 피드백만 학습이 진행되어 우리의 최종 목표인 binary classification을 수행하지 못할 것이다.  

이 문제를 해결하기 위한 두 가지 방법을 제안한다. 하나는 Neural Collaborative Filtering에서 사용한 방법이고, 다른 하나는 Collaborative Filtering for Implicit Feedback Datasets에서 사용한 방법이다.

### 1. Negative Sampling  
- [Neural Collaborative Filtering](https://arxiv.org/pdf/1708.05031.pdf)  
- 유저가 긍정적인 피드백을 준 것 이외에 유저가 아직 피드백을 주지 않은 k개의 아이템을 포함시켜 Training Set을 구성한다.(k는 하이퍼 파라미터이며, 이 논문에서는 $k=4$)  
- 긍정적인 피드백이 $n$개라면 Training Set은 $n(k+1)$개가 된다.  
- 즉, Negative Feedback의 일부만 샘플링해 훈련에 사용하는 방법이다.  

### 2. Confidence Level  
- [Collaborative Filtering for Implicit Feedback Datasets](http://yifanhu.net/PUB/cf.pdf)  
- Confidence Level이라는 개념을 도입한다. 유저가 아이템과 연관성이 있는지 정도를 수치적으로 표현하기 위한 것이다.  
- $c_{ui}=1+\alpha r_{ui}$로 계산할 수 있다. $c_ui$가 클수록 유저와 아이템은 연관성이 큰 것이다.  
- $r_{ui}$는 긍정적인 피드백의 수이며, $r_{ui}$가 증가할수록 $c_ui$도 커진다. (증가하는 정도를 나타낸 것이 $\alpha$다. $\alpha$는 하이퍼 파라미터이며, 이 논문에서는 $\alpha=40$)  
- $c_{ui}$는 모두 1 이상의 값을 갖게 된다.  
- 즉, Negative Feedback도 모두 사용해 훈련에 사용하는 방법이다.  