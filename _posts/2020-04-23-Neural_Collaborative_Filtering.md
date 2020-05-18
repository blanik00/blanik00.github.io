---
title: 'Neural Collaborative Filtering'
date: 2020-04-24
permalink: /paper_review/2020/04/24/Neural_Collaborative_Filtering
category:
  - review
--- 

# 요약
- Implicit Feedback을 활용한 Collaborative Filtering을 다룬다.  
- output이 1이면 User와 Item은 연관성이 있는 것이며, 0이면 User와 Item은 연관성이 없는 것이다. 즉, binary classification 문제이다.  
- Collaborative Filtering에서 Matrix Factorization은 많이 쓰이는 기법이다.  
- 기존의 Matrix Factorization은 User Latent Factor와 Item Latent Factor를 구하고, 두 Latent Factor를 내적하는 방법을 통해 Rating Matrix를 복원한다.  
- 하지만 이 방법은 User-Item Interaction을 충분히 표현하지 못한다.  
- 저자는 **내적**이라는 지나치게 단순한 방법으로 Rating Matrix를 복원했기 때문이라고 본다.  
- 대안으로 **뉴럴 네트워크**의 사용을 권한다.  
- 뉴럴 네트워크를 도입함으로써 Matrix Factorization이 가지는 Linearity와 뉴럴 네트워크가 가지는 Non-Linearity를 모두 가질 수 있다.  

# 문제 제시  
기존의 Matrix Factorization은 SGD나 ALS 등의 방법을 사용해서 User-Item Interaction($M\times N$)을 User Latent Factor($M\times K$)와 Item Latent Factor($K\times N$)로 분해한다(K << M, N).  

그 후 두 Latent Factor를 내적해 Rating Matrix를 복원하는 방법을 통해 User가 Item을 얼마나 선호하는지 등을 예측한다.  
![](https://user-images.githubusercontent.com/26649034/80499831-6a59c300-89a8-11ea-9e96-de5ff1654354.png)  

내적의 의미를 생각해보면 내적을 한다는 것은 User Latent Factor와 Item Latent Factor를 선형 결합해서 Rating Matrix를 복원한다는 것이다(Linear). 하지만 Linear한 방법은 단순한 예제에서는 잘 작동하지만, User-Item Interaction과 같이 복잡한 관계를 가지는 것을 잘 표현하지 못한다는 단점이 있다.  

# 대안 제시  
저자는 이 문제를 해결하기 위해 두 가지 방법이 있다고 말한다.  

1. Latent Factor의 Dimension(K)을 늘리는 것  
2. Non-Linear한 방법을 통해 모델 구축  

둘 다 좋은 방법이지만 1번 방법의 경우 오버피팅이 발생한다는 문제가 있어 2번 방법을 채택했으며, Non-Linearity를 추가하기 위한 방법으로 Neural Network를 도입한 것이다.  

# 뉴럴 네트워크 도입으로 인해 달라지는 것들 

## 1. Embedding Layer  
Embedding Layer를 한 문장으로 표현하면 다음과 같다.  

> Turns positive integers (indexes) into dense vectors of fixed size.  

즉, categorical한 input을 고정된 사이즈의 dense한 벡터로 바꿔주는 Layer이다. 이 논문에서는 User Latent Factor와 Item Latent Factor를 표현하는 데 사용한다.  
## 2. 필요한 모델
### (0) Neural Collaborative Filtering Framework
![](https://user-images.githubusercontent.com/26649034/80499827-69c12c80-89a8-11ea-920a-969720de8bec.png)  

뒤에 나오는 모델들의 뼈대가 되는 것이다. 다음과 같은 과정을 거친다.  

1. Input Layer  
2. Embedding Layer  
3. Neural CF Layers  
4. Output Layer  

### (1) MLP(Multi-Layer Perceptron)  

앞의 Neural Collaborative Filtering Framework을 충실히 재현한 모델이다. User Latent Factor와 Item Latent Factor를 여러 Layer를 거치게 해 결과를 낸다.(Layer의 activation function을 relu로 해 Non-Linearity를 얻는다.)  

수식으로 표현하면 다음과 같다.  
![](https://user-images.githubusercontent.com/26649034/80499829-6a59c300-89a8-11ea-97fb-11ba105acc76.png)  

$W_x$ : weight matrix for x-th layer  
$b_x$ : bias vector for x-th layer  
$a_x$ : activation function for x-th layer  
$h$ : edge weights of the output layer  

수식에서 볼 수 있듯이 첫 번째 layer는 User Latent Factor와 Item Latent Factor를 Concatenate한 것이다.  

### (2) GMF(Generalized Matrix Factorization)  
![](https://user-images.githubusercontent.com/26649034/80499823-69289600-89a8-11ea-959a-3d6377197ead.png)  

이번에는 앞에서 본 Neural Collaborative Filtering Framework의 특별한 케이스 중 하나를 다룰 것이다.

수식으로 표현하면 다음과 같다.  

![](https://user-images.githubusercontent.com/26649034/80499822-688fff80-89a8-11ea-8ca8-fa287685f3d2.png)  

$a_{out}$ : activation function  
$h$ : edge weights of the output layer  
$\odot$ : element-wise product  

만약 activation function으로 non-linear한 함수를 사용하면 non-linear한 	모델로도 사용할 수 있다. 하지만 논문에서 저자는 GMF 모델이 Linearity를 가지게 한다(저자가 작성한 [코드](https://github.com/hexiangnan/neural_collaborative_filtering/blob/master/GMF.py)를 보면 확인할 수 있다).  

$a_{out}$이 identity function($y=x$)이며, $h$가 1로 이루어진 벡터라면, Matrix Factorization과 똑같아진다. 

실제로는 $a_{out}$과 $h$를 없애고, $p_u^G\odot p_u^M$만을 사용한다.  

### (3) NeuMF(Neural Matrix Factorization)  
![](https://user-images.githubusercontent.com/26649034/80499819-67f76900-89a8-11ea-9f46-525a6837a031.png)  

NeuMF는 GMF와 MLP에서 얻은 최종 Layer를 Concatenate하여 결과를 낸다. GMF와 MLP를 결합해 Linearity와 Non-Linearity 모두를 얻고자 하는 모델이다.  

수식으로 표현하면 다음과 같다.  

![](https://user-images.githubusercontent.com/26649034/80499815-67f76900-89a8-11ea-984f-43480da9eb07.png)  

$p_u^G$ : User Embedding for GMF  
$p_u^M$ : User Embedding for MLP  
$q_i^G$ : Item Embedding for GMF  
$q_i^M$ : Item Embedding for MLP  

# 결과  
## 1. 다른 모델과의 비교
![](https://user-images.githubusercontent.com/26649034/80499809-675ed280-89a8-11ea-8e8d-49c6c72d7ea3.png)  

## 2. Pre-training의 성과
Pre-training에 대한 내용은 뒤에 나온다.  
![](https://user-images.githubusercontent.com/26649034/80499805-662da580-89a8-11ea-97a6-29afd932fd3d.png)  

## 3. 3가지 모델의 성능 비교
![](https://user-images.githubusercontent.com/26649034/80499803-65950f00-89a8-11ea-925d-f29d1bca75af.png)  

## 4. Negative Sample의 수에 따른 성능 비교 
Negative Sampling에 대한 내용은 뒤에 나온다.  
![](https://user-images.githubusercontent.com/26649034/80499801-6463e200-89a8-11ea-9ad3-1ff6c31a7290.png)  

## 5. MLP Layer의 수에 따른 성능 비교
![](https://user-images.githubusercontent.com/26649034/80499792-62018800-89a8-11ea-92d8-3ed1cd21bbf9.png)  

# 기타
## 1. Pre-training  
NCF의 Loss Function은 non-convex하기 때문에 GD를 사용하면 Local Optimum에 수렴할 가능성이 있다. 이러한 경우 초기값을 어떻게 주는지가 딥러닝 모델의 성능에 큰 영향을 미친다. 저자는 미리 훈련된(pretrained) GMF, MLP 모델을 사용하여 NeuMF의 weights를 초기화하는 방식을 제안한다.  

방법은 다음과 같다.  

1. GMF와 MLP 모델을 수렴할 때 까지 훈련시킨다.  
2. GMF와 MLP의 파라미터를 NeuMF의 해당하는 부분에 초기값으로 대입한다.  

## 2. How to deal with Absence of Negative Feedback
[How to deal with Absence of Negative Feedback](https://blanik00.github.io/posts/2020/05/17/absence_of_negative_feedback)에서 다루었다. "Negative Sampling" 항목을 보면 된다.

## 3. Loss Function
이 모델에서 output은 0과 1이므로 Bernoulli Distribution을 따른다.  

베르누이 분포에서 가능도는 다음과 같이 표현할 수 있다.  

![](https://user-images.githubusercontent.com/26649034/80507963-659a0c80-89b2-11ea-9c1a-a85714fa00d1.png)  
	
가능도의 negative logarithm은 다음과 같다. 이 식을 활용해서 loss를 최소화하는 방향으로 학습을 진행시킬 수 있다(식이 binary cross-entropy와 같다).

![](https://user-images.githubusercontent.com/26649034/80507967-6763d000-89b2-11ea-8d63-b4fc7d23c660.png)  

# 참고
[Neural Collaborative Filtering](https://arxiv.org/pdf/1708.05031.pdf)  
[Collaborative Filtering for Implicit Feedback Datasets](http://yifanhu.net/PUB/cf.pdf)  