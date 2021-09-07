# Eigendecompositions (고유값 분해)

Date: August 21, 2021

## Eigenvalues & Eigenvector (고유값 &고유 벡터)

하나의 벡터(V)가 있다고 가정할 때 그 벡터의 직선상에 있는 벡터를 고유벡터(V')라고 하고 원래 벡터(V)에 고유벡터(V')로의 상수배를 고유 값이라고 한다. 

쉽게 말하면 한 벡터의 상수를 곱한 벡터가 **고유 벡터**고 그 곱한 값이 **고유 값**이다.  

고유값의 기하학적 의미 : 방향은 똑같고 길이만 달라지기 때문에 고유 벡터의 변화정도를 나타내는 값이다. 

## Decomposing Matrics (고유값 분해)

![Untitled](./Untitled.png)

위의 그림을 보면 벡터의 열백터가 고유값의 대각행렬과 곱해지면 각 고유값만큼 증가한 벡터가 된다. 

![Untitled](./Untitled%201.png)

원래 벡터

![Untitled](./Untitled%202.png)

고유벡터

![Untitled](./Untitled%203.png)

![Untitled](./Untitled%204.png)

→ 원래 벡터와 고유벡터를 안다면 각 원래 벡터의 열벡터를 고유벡터에 곱하면 고유값을 알 수 있다! (고유값 분해)

## Gershgorin Circle Theorem (게르시고린의 정리)

- 고유값을 근사적으로 계산할 수 있는 공식

행렬 A가 정사각 행렬이라고 가정할 때, A의 i째 행의 대각성분을 제외한 나머지 성분의 절댓값의 합을 반지름으로 하고 i번째 행의 대각성분을 중심으로 하는 원판을 구할 수 있다. 이 원판을 게르시고린의 원판이라 하고 이를 통해

A의 모든 고유값은 A의 게르시고린 원판 중 하나의 안쪽에 놓인다.

와 같이 공식화 할 수 있다. 

![Untitled](./Untitled%205.png)

![Untitled](./Untitled%206.png)

게르시고린의 정리로 구한 4개의 원판의 범위

실제 고유값 : 0.99, 2.97, 4.95, 9.08 ⇒ 모두 저 원판 중 한개의 범위 안에 있다. 

# Neural Network Wegith Initialization

실제 neural network는 선형 레이어와 non-linear 함수의 반복이다. 하지만 여기서는 비선형 함수를 고려하지 않고 행렬 A를 여러번 곱한 것이라 가정해본다. 

![Untitled](./Untitled%207.png)

이 모델이 초기화 될때, A는 가우시안 분포에서 랜덤하게 추출된다. 

만약에 우리가 고양이 이미지를 input으로 넣고 예측하는 상황이라고 가정하면, A가 계속 곱해지면서 원래의 행렬을 매우 크게 만들거나 매우 작게 만들면 원래의 행렬과 매우 다른 예측값을 내게 된다. (크게 하면 input값에 매우 의존하게 되고 작게 하면 input값과 독립적인 output을 내게 됨) 그래서 우리는 growth 와 decay의 사이에서 잘 조절을 해야한다. 

![Untitled](./Untitled%208.png)

벡터가 매우 커지게 되는 경우

![Untitled](./Untitled%209.png)

1.97... 으로 안정적인 그래프
