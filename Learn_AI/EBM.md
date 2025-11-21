# Energy-Based Models (EBM, 에너지 기반 모델)

## 1. 개요 (Overview)
Energy-Based Model(EBM, 에너지 기반 모델)은 Yann LeCun이 제안한 [머신러닝(Machine Learning)](./MLBasic.md) 프레임워크로, 변수들 간의 호환성(Compatibility)을 "에너지(Energy)"라는 스칼라 값으로 측정하는 방법론입니다.

전통적인 확률 모델(Probabilistic Model)이 데이터의 확률 분포 $P(Y|X)$를 정규화(Normalization)하여 합이 1이 되도록 만드는 데 집중하는 반면, EBM은 정규화 제약 없이 **"정답 데이터에는 낮은 에너지를, 오답 데이터에는 높은 에너지를 부여"**하는 에너지 함수 $E(W, Y, X)$를 학습하는 데 초점을 맞춥니다.

## 2. 핵심 개념 (Key Concepts)

### 2.1. 에너지 함수 (Energy Function)
에너지 함수 $E(W, Y, X)$는 입력 $X$와 출력 $Y$가 주어졌을 때, 이 쌍이 얼마나 "자연스러운지" 또는 "호환되는지"를 나타냅니다.
- **낮은 에너지 (Low Energy)**: $X$와 $Y$가 서로 잘 어울림 (정답에 가까움).
- **높은 에너지 (High Energy)**: $X$와 $Y$가 서로 어울리지 않음 (오답에 가까움).

### 2.2. 추론 (Inference)
입력 $X$가 주어졌을 때, 가장 적절한 출력 $Y$를 찾는 과정은 에너지를 최소화하는 $Y$를 찾는 [최적화(Optimization)](./DLBasic.md) 문제로 정의됩니다.
$$ Y^* = \text{argmin}_{Y} E(W, Y, X) $$
이는 Gradient Descent와 같은 최적화 기법을 통해 수행될 수 있습니다.

### 2.3. 학습 (Learning)
학습의 목표는 정답 데이터(Positive Sample)의 에너지를 낮추고(Pull down), 오답 데이터(Negative Sample)의 에너지를 높이는(Push up) 에너지 지형(Energy Landscape)을 만드는 것입니다. 이를 위해 Contrastive Divergence와 같은 방법이 사용됩니다.

## 3. 확률 모델과의 차이 (Difference from Probabilistic Models)

- **Normalization 불필요**: 확률 모델은 모든 가능한 $Y$에 대해 확률의 합이 1이 되어야 하므로, 분모(Partition Function)를 계산해야 합니다. 이는 고차원 공간에서 매우 계산 비용이 높거나 불가능할 수 있습니다. EBM은 이러한 제약이 없어 모델 설계가 훨씬 자유롭습니다.
- **다양한 출력 처리**: 하나의 입력에 대해 여러 개의 타당한 출력이 존재할 때(Multimodality), EBM은 여러 $Y$ 값에 대해 낮은 에너지를 부여함으로써 이를 자연스럽게 표현할 수 있습니다.

## 4. 주요 응용 분야 (Applications)

1.  **[Self-Supervised Learning (SSL, 자기지도 학습)](./SelfSL.md)**: 데이터의 일부를 보고 나머지를 예측할 때, EBM은 불확실성을 효과적으로 다룰 수 있습니다. [JEPA](./JEPA.md) 또한 EBM의 일종으로 볼 수 있습니다.
2.  **Structured Prediction**: 출력 간의 복잡한 의존성이 있는 경우(예: 이미지 분할, 자연어 처리)에 유용합니다.
3.  **Anomaly Detection**: 학습된 데이터 분포에서 벗어난 데이터는 높은 에너지를 가지므로, 이를 통해 이상치를 탐지할 수 있습니다.

## 5. 사전 지식 (Prerequisites)

EBM을 깊이 있게 이해하기 위해서는 다음의 개념들에 대한 사전 지식이 필요합니다.

1.  **Calculus & [Optimization (미적분 및 최적화)](./DLBasic.md)**
    - Gradient Descent (경사 하강법)
    - Energy Landscapes (에너지 지형)

2.  **Statistical Physics (통계 물리학)**
    - Boltzmann Distribution (볼츠만 분포)
    - Gibbs Measure (깁스 측도)
    - Partition Function (분배 함수)

3.  **[Machine Learning Basics](./MLBasic.md)**
    - Maximum Likelihood Estimation (최대 우도 추정)
    - Contrastive Learning (대조 학습)
