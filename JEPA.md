# JEPA (Joint-Embedding Predictive Architecture)

## 1. 개요 (Overview)
JEPA(Joint-Embedding Predictive Architecture)는 Meta의 수석 AI 과학자 Yann LeCun이 제안한 차세대 AI 아키텍처입니다. 현재의 거대 언어 모델(LLM)이나 생성형 AI(Generative AI)가 가진 한계를 극복하고, 인간 수준의 지능(Human-level AI)과 상식(Common Sense)을 갖춘 AI를 만들기 위한 핵심 프레임워크로 제시되었습니다.

JEPA는 단순히 텍스트나 픽셀을 생성하는 것이 아니라, **세상의 구조와 인과관계(Causality)를 이해하고 예측**하는 것을 목표로 합니다. 이를 통해 AI가 보다 효율적으로 학습하고, 계획(Planning)과 추론(Reasoning)을 수행할 수 있도록 돕습니다.

## 2. 핵심 개념 (Key Concepts)

### 2.1. 예측적 학습 (Predictive Learning)
JEPA의 핵심 아이디어는 "예측"입니다. 하지만 기존의 생성 모델처럼 입력 데이터의 모든 세부 사항(예: 픽셀 단위)을 예측하는 것이 아니라, **추상적인 표현(Abstract Representation)** 수준에서의 예측을 수행합니다.
- **Generative Model**: 입력 $x$의 일부를 보고 나머지 $y$를 픽셀/토큰 단위로 복원 ($P(y|x)$). 계산 비용이 높고 불필요한 디테일에 집중함.
- **JEPA**: 입력 $x$와 $y$를 각각 인코더를 통해 잠재 공간(Latent Space)의 표현 $s_x$, $s_y$로 매핑한 뒤, $s_x$로부터 $s_y$를 예측.

### 2.2. Joint-Embedding (결합 임베딩)
JEPA는 두 개의 입력(예: 비디오의 현재 프레임과 미래 프레임, 또는 이미지의 일부와 나머지)을 공통된 잠재 공간으로 매핑합니다. 이 공간에서 모델은 서로 관련된 입력들이 유사한 표현을 갖도록 학습하며, 동시에 불필요한 정보(노이즈)는 버리고 중요한 의미적 정보(Semantic Information)만을 포착합니다.

### 2.3. World Model (세계 모델)
LeCun은 JEPA를 통해 AI가 내부적인 **World Model**을 구축할 수 있다고 봅니다. World Model은 세상이 어떻게 작동하는지에 대한 압축된 지식으로, AI가 행동의 결과를 미리 시뮬레이션하고 복잡한 작업을 계획하는 데 필수적입니다.

### 2.4. [Energy-Based Model (EBM)](./EBM.md)
JEPA는 에너지 기반 모델의 일종으로 볼 수 있습니다. 예측된 표현과 실제 타겟 표현 사이의 차이(에너지)를 최소화하는 방향으로 학습합니다. 에너지가 낮을수록 두 표현이 호환됨(Compatible)을 의미합니다.

## 3. 주요 특징 및 장점 (Features & Benefits)

1.  **효율성 (Efficiency)**: 픽셀 단위의 생성을 하지 않으므로 계산 비용이 훨씬 적고 학습 속도가 빠릅니다.
2.  **추상화 (Abstraction)**: 사소한 디테일(배경의 흔들리는 나뭇잎 등)을 무시하고, 중요한 객체의 움직임이나 상태 변화와 같은 본질적인 정보에 집중합니다.
3.  **계층적 학습 (Hierarchical Learning)**: 다양한 시간 및 공간 스케일에서 예측을 수행함으로써 계층적인 표현을 학습할 수 있습니다.
4.  **다양한 모달리티 적용 가능**: 이미지(I-JEPA), 비디오(V-JEPA) 등 다양한 데이터 유형에 적용되어 우수한 성능을 입증했습니다.

## 4. 사전 지식 (Prerequisites)

JEPA를 깊이 있게 이해하기 위해서는 다음의 개념들에 대한 사전 지식이 필요합니다. (추후 별도의 문서로 상세히 설명될 예정입니다.)

1.  **[Self-Supervised Learning (SSL, 자기지도 학습)](./SelfSL.md)**
    - Generative vs. Discriminative vs. Joint-Embedding Methods
    - Pretext Tasks (Inpainting, Prediction etc.)

2.  **[Energy-Based Models (EBM, 에너지 기반 모델)](./EBM.md)**
    - Energy Function의 개념
    - Contrastive Methods (대조 학습) vs. Regularized Methods (정규화 방법)
    - Collapse (붕괴) 문제와 해결책

3.  **Representation Learning (표현 학습)**
    - Latent Space (잠재 공간)
    - Feature Extraction (특징 추출)
    - Invariance (불변성) & Equivariance (공변성)

4.  **[Deep Learning Basics](./DLBasic.md)**
    - Encoder-Decoder Architectures
    - [Loss Functions (L2 distance, Cosine Similarity etc.)](./DLBasic.md)
    - [Optimization (Gradient Descent)](./DLBasic.md)

