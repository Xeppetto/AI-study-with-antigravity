# LeJEPA (Latent-Euclidean Joint-Embedding Predictive Architecture)

## 1. 개요 (Overview)
LeJEPA(Latent-Euclidean Joint-Embedding Predictive Architecture)는 Meta의 Yann LeCun과 Randall Balestriero가 제안한 새로운 [자기지도 학습(Self-Supervised Learning, SSL)](./SelfSL.md) 모델이자 학습 방법론입니다. 

기존의 SSL 방식들이 성능을 높이기 위해 의존했던 여러 경험적 기법(Heuristics)이나 복잡한 엔지니어링 트릭(예: Stop-gradient, EMA, Negative sampling 등)을 제거하고, **"제1원칙(First-principles)"**에 기반하여 설계된 모델입니다. LeJEPA는 [JEPA(Joint-Embedding Predictive Architecture)](./JEPA.md) 프레임워크를 기반으로 하며, 학습된 잠재 표현(Latent Representation)이 유클리드 공간에서 **등방성 가우시안(Isotropic Gaussian)** 분포를 따르도록 강제함으로써 학습의 안정성과 효율성을 극대화합니다.

## 2. 핵심 개념 (Key Concepts)

### 2.1. JEPA (Joint-Embedding Predictive Architecture)
LeJEPA는 LeCun이 제안한 JEPA 아키텍처를 따릅니다. JEPA는 입력 데이터의 일부를 보고 나머지 부분을 예측하는 방식이 아니라, 입력의 서로 다른 뷰(View)를 잠재 공간(Latent Space)으로 매핑한 뒤, 잠재 공간 상에서 하나의 뷰로부터 다른 뷰의 표현을 예측하도록 학습합니다. 이는 픽셀 단위의 생성(Generation)이 아닌, 의미론적 표현(Representation)의 예측에 초점을 맞춥니다.

### 2.2. Latent-Euclidean Geometry (잠재 유클리드 기하학)
LeJEPA의 가장 큰 특징은 잠재 공간의 기하학적 구조를 명확히 정의했다는 점입니다. 연구진은 모델의 임베딩이 **등방성 가우시안 분포(Isotropic Gaussian Distribution)**를 따를 때, 다운스트림 작업(Downstream Tasks)에서의 예측 위험(Prediction Risk)이 최소화됨을 이론적으로 증명했습니다. 즉, 임베딩이 모든 방향으로 고르게 퍼져 있으며 중심에 모여 있는 형태가 가장 이상적이라는 것입니다.

### 2.3. [SIGReg (Sketched Isotropic Gaussian Regularization)](./SIGReg.md)
위의 이상적인 분포를 실제로 구현하기 위해 LeJEPA는 **[SIGReg](./SIGReg.md)**라는 새로운 정규화(Regularization) 기법을 도입했습니다.
- **Random Projections**: 계산 효율성을 위해 임베딩을 무작위로 투영(Sketching)하여 차원을 축소한 뒤 정규화를 수행합니다.
- **Variance Regularization**: 임베딩의 분산을 특정 값으로 유지하여 붕괴(Collapse)를 방지합니다.
- **Invariance Regularization**: 서로 다른 뷰의 임베딩이 비슷해지도록 유도합니다.
SIGReg는 기존의 복잡한 [손실 함수(Loss Function)](./DLBasic.md)나 트릭 없이도 모델이 효과적인 표현을 학습하도록 돕습니다.

### 2.4. Heuristics 제거 (Elimination of Heuristics)
기존 SSL 모델(예: BYOL, DINO, SimCLR 등)은 학습 붕괴를 막기 위해 다음과 같은 기법들을 사용했습니다.
- Negative Pairs (부정 샘플)
- Stop-Gradient (기울기 차단)
- Momentum Encoder (EMA)
- Large Batch Sizes
LeJEPA는 이러한 기법들 없이도 안정적으로 학습이 가능하며, 하이퍼파라미터 설정이 훨씬 단순합니다.

## 3. 주요 특징 및 장점 (Features & Benefits)

1.  **단순성 및 재현성**: 복잡한 트릭을 제거하여 코드가 간결하고, 다양한 아키텍처나 데이터셋에서도 일관된 성능을 보입니다.
2.  **학습 안정성**: 이론적 근거에 기반한 설계로 인해 학습 곡선이 매우 안정적이며, Exploding Gradient와 같은 문제가 적습니다.
3.  **성능 예측 가능성**: 학습 중의 Loss 값과 실제 다운스트림 작업(예: ImageNet 분류)의 성능 간에 매우 높은 상관관계(약 99%)가 있어, 별도의 검증 과정 없이도 모델의 성능을 가늠할 수 있습니다.
4.  **효율성**: 선형적인 시간 및 메모리 복잡도를 가지며, 대규모 모델로의 확장이 용이합니다.

---

## 4. 사전 지식 (Prerequisites)

LeJEPA를 깊이 있게 이해하기 위해서는 다음의 개념들에 대한 사전 지식이 필요합니다. (추후 별도의 문서로 상세히 설명될 예정입니다.)

1.  **Self-Supervised Learning (SSL, 자기지도 학습)**
    - Contrastive Learning (대조 학습)
    - Masked Image Modeling (MIM)
    - Representation Learning (표현 학습)의 목표와 붕괴(Collapse) 문제

2.  **JEPA (Joint-Embedding Predictive Architecture)**
    - LeCun의 World Model 비전
    - Generative Model vs. Joint-Embedding Model의 차이

3.  **Linear Algebra & Probability (선형대수 및 확률론)**
    - Gaussian Distribution (가우시안 분포) 및 Isotropic(등방성)의 의미
    - Eigenvalues & Eigenvectors (고유값과 고유벡터)
    - Covariance Matrix (공분산 행렬)
    - Random Projections (무작위 투영)

4.  **[Deep Learning Architectures (딥러닝 아키텍처)](./DLBasic.md)**
    - Vision Transformers (ViT)
    - Encoder-Decoder 구조 vs. Encoder-Predictor 구조

