# World Model (세계 모델)

## 1. 개요 (Overview)
World Model(세계 모델)은 에이전트가 자신이 속한 환경(World)이 어떻게 작동하는지에 대한 내부적인 멘탈 모델(Internal Mental Model)을 의미합니다. 인간이 머릿속으로 시뮬레이션을 돌려 미래를 예측하고 행동을 결정하는 것과 유사합니다.

## 2. 핵심 기능 (Key Functions)
- **Simulation (시뮬레이션)**: 실제 환경에서 행동하지 않고도, 가상의 시나리오를 통해 결과를 예측해볼 수 있습니다.
- **Planning (계획)**: 예측된 미래를 바탕으로 현재 최적의 행동을 결정할 수 있습니다.
- **Reasoning (추론)**: 인과 관계를 이해하고 복잡한 문제를 해결하는 능력의 기반이 됩니다.

## 3. 구성 요소 (Components)
일반적으로 다음과 같은 모듈로 구성됩니다.
- **Vision Model (V)**: 관측된 이미지로부터 현재 상태를 압축하여 표현합니다.
- **Memory Model (M)**: 과거의 정보를 기억하고 현재 상태와 결합합니다. (주로 RNN 사용)
- **Controller (C)**: 기억된 정보를 바탕으로 행동을 선택합니다.

## 4. World Model과 [JEPA](./JEPA.md)
Yann LeCun은 진정한 지능(Autonomous Machine Intelligence)을 위해서는 기계가 세계 모델을 가져야 한다고 주장합니다.
- **[JEPA (Joint-Embedding Predictive Architecture)](./JEPA.md)**는 이러한 세계 모델을 학습하기 위한 핵심 아키텍처입니다.
- JEPA는 입력($x$)과 행동($a$)이 주어졌을 때, 결과($y$)의 추상적 표현을 예측함으로써 세계의 인과 관계를 학습합니다. 이는 픽셀 단위의 생성(Generative) 모델보다 훨씬 효율적이고 강력한 세계 모델을 가능하게 합니다.

## 5. 관련 분야
- **[Reinforcement Learning (강화 학습)](./ReinforcementLearning.md)**: Model-Based RL에서 세계 모델이 핵심적인 역할을 합니다.
