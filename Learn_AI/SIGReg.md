# SIGReg (Sketched Isotropic Gaussian Regularization)

## 1. 개요 (Overview)
SIGReg(Sketched Isotropic Gaussian Regularization)는 Meta의 Yann LeCun과 Randall Balestriero가 제안한 [LeJEPA](./LeJEPA.md)의 핵심 정규화 기법입니다. 

자기지도 학습(SSL)에서 모델의 표현(Representation)이 붕괴(Collapse)하는 것을 막고, 학습된 임베딩이 이론적으로 가장 이상적인 형태인 **등방성 가우시안 분포(Isotropic Gaussian Distribution)**를 따르도록 강제합니다. 이를 통해 복잡한 경험적 트릭(Heuristics) 없이도 안정적이고 효율적인 학습을 가능하게 합니다.

## 2. 핵심 개념 (Key Concepts)

### 2.1. 등방성 가우시안 분포 (Isotropic Gaussian Distribution)
연구진은 다운스트림 작업의 예측 위험을 최소화하는 최적의 임베딩 분포가 등방성 가우시안임을 증명했습니다.
- **Isotropic (등방성)**: 모든 방향으로 분산이 동일함. 즉, 특정 방향으로 치우치지 않고 고르게 퍼져 있음.
- **Gaussian (가우시안)**: 중심에 데이터가 밀집되어 있고 멀어질수록 밀도가 낮아지는 정규 분포 형태.

### 2.2. Sketching (스케칭)
고차원의 임베딩 공간에서 직접 정규화를 수행하는 것은 계산 비용이 높습니다. SIGReg는 **Random Projections(무작위 투영)**을 통해 임베딩을 저차원으로 "스케치(Sketch)"한 뒤 정규화를 적용합니다. 이는 계산 효율성을 크게 높여줍니다.

### 2.3. 정규화 목표 (Regularization Objectives)
SIGReg는 다음 두 가지를 동시에 달성하도록 [손실 함수(Loss Function)](./DLBasic.md)를 구성합니다.
1.  **Variance Regularization**: 임베딩의 공분산 행렬(Covariance Matrix)이 단위 행렬(Identity Matrix)에 비례하도록 하여, 모든 차원을 골고루 활용하고 붕괴를 방지합니다.
2.  **Invariance Regularization**: 서로 다른 뷰(View)에서 얻은 임베딩 간의 거리를 좁혀, 의미론적으로 유사한 데이터가 가깝게 위치하도록 합니다.

## 3. 주요 특징 및 장점 (Features & Benefits)

1.  **Heuristics 제거**: Stop-gradient, Momentum Encoder, Negative Sampling 등 기존 SSL의 복잡한 트릭들을 대체합니다.
2.  **단순성 (Simplicity)**: 구현이 매우 간단하며(약 50줄의 코드), 하이퍼파라미터 설정이 단순합니다.
3.  **효율성 (Efficiency)**: 선형적인 시간 및 메모리 복잡도를 가지며, 멀티 GPU 환경에서도 확장이 용이합니다.
4.  **안정성 (Stability)**: 이론적 근거에 기반하여 학습 과정이 매우 안정적입니다.

## 4. 사전 지식 (Prerequisites)

SIGReg를 깊이 있게 이해하기 위해서는 다음의 개념들에 대한 사전 지식이 필요합니다.

1.  **Linear Algebra (선형대수)**
    - Covariance Matrix (공분산 행렬)
    - Identity Matrix (단위 행렬)
    - Random Projections (무작위 투영) & Johnson-Lindenstrauss Lemma

2.  **Probability & Statistics (확률 및 통계)**
    - Gaussian Distribution (가우시안 분포)
    - Variance & Standard Deviation (분산 및 표준편차)

3.  **[Machine Learning Basics](./MLBasic.md)**
    - Regularization (정규화) - L1, L2, etc.
    - Dimensionality Reduction (차원 축소)
    - [Self-Supervised Learning (SSL)](./SelfSL.md)의 Collapse 문제
