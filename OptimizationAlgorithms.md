# Optimization Algorithms (최적화 알고리즘)

## 1. 개요 (Overview)
Optimization Algorithms(최적화 알고리즘)은 [머신러닝(Machine Learning)](./MLBasic.md) 모델의 학습 과정에서 손실 함수(Loss Function)를 최소화하기 위해 파라미터(가중치)를 업데이트하는 방법을 정의합니다.

## 2. 주요 알고리즘 (Key Algorithms)

### 2.1. Gradient Descent (GD, 경사 하강법)
가장 기본적인 방법으로, 손실 함수의 기울기(Gradient) 반대 방향으로 파라미터를 조금씩 이동시킵니다.
- **SGD (Stochastic Gradient Descent)**: 전체 데이터 대신 미니 배치(Mini-batch)를 사용하여 속도를 높입니다.

### 2.2. Momentum
이전 단계의 업데이트 방향(관성)을 반영하여, 진동을 줄이고 수렴 속도를 높입니다.

### 2.3. Adaptive Methods
파라미터마다 학습률(Learning Rate)을 다르게 조절합니다.
- **Adagrad**: 많이 업데이트된 파라미터의 학습률을 낮춥니다.
- **RMSProp**: 최근 기울기를 더 크게 반영합니다.
- **Adam (Adaptive Moment Estimation)**: Momentum과 RMSProp의 장점을 결합한 가장 대중적인 알고리즘입니다.

## 3. [EBM](./EBM.md)과 최적화
[Energy-Based Models (EBM)](./EBM.md)에서는 추론(Inference) 과정 자체가 최적화 문제입니다.
- 입력 $x$가 주어졌을 때, 에너지 $E(x, y)$를 최소화하는 $y$를 찾는 과정(Gradient Descent 등)을 통해 예측을 수행합니다.
