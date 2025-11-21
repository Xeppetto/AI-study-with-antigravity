# Regularization (정규화)

## 1. 개요 (Overview)
Regularization(정규화)은 [머신러닝(Machine Learning)](./MLBasic.md) 모델의 과적합(Overfitting)을 방지하고 일반화(Generalization) 성능을 높이기 위해 사용되는 기법입니다. 모델이 학습 데이터에 너무 집착하지 않도록 제약(Constraint)을 가하는 것입니다.

## 2. 주요 기법 (Key Techniques)

### 2.1. L1 / L2 Regularization
손실 함수(Loss Function)에 가중치(Weight)의 크기에 대한 페널티 항을 추가합니다.
- **L1 (Lasso)**: 가중치의 절댓값 합을 더함. 일부 가중치를 0으로 만들어 희소(Sparse) 모델을 만듭니다.
- **L2 (Ridge)**: 가중치의 제곱 합을 더함. 큰 가중치를 억제하여 모델을 부드럽게 만듭니다.

### 2.2. Dropout
학습 과정에서 신경망의 일부 뉴런을 무작위로 비활성화하여, 특정 뉴런에 대한 의존도를 낮춥니다.

### 2.3. Early Stopping
검증 데이터(Validation Data)에 대한 성능이 더 이상 향상되지 않으면 학습을 조기에 종료합니다.

## 3. [SIGReg](./SIGReg.md)와 Regularization
[LeJEPA](./LeJEPA.md)에서 사용되는 **[SIGReg (Sketched Isotropic Gaussian Regularization)](./SIGReg.md)**는 잠재 공간(Latent Space)의 임베딩이 붕괴(Collapse)하지 않도록 강제하는 특수한 형태의 정규화입니다.
- 일반적인 정규화가 가중치($W$)를 제어한다면, SIGReg는 출력 임베딩($Z$)의 분포를 직접 제어합니다.
