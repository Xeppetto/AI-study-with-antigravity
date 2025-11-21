# Reinforcement Learning (RL, 강화 학습)

## 1. 개요 (Overview)
Reinforcement Learning(RL, 강화 학습)은 에이전트(Agent)가 환경(Environment)과 상호작용하며, 어떤 행동(Action)을 취했을 때 주어지는 보상(Reward)을 최대화하는 방향으로 학습하는 [머신러닝(Machine Learning)](./MLBasic.md)의 한 유형입니다. 시행착오(Trial and Error)를 통해 최적의 정책(Policy)을 찾습니다.

## 2. 핵심 구성 요소 (Key Components)

- **Agent (에이전트)**: 학습하고 행동하는 주체.
- **Environment (환경)**: 에이전트가 상호작용하는 세계.
- **State (상태, $S$)**: 특정 시점에서의 환경의 상태.
- **Action (행동, $A$)**: 에이전트가 취할 수 있는 행동.
- **Reward (보상, $R$)**: 행동의 결과로 환경이 에이전트에게 주는 피드백 (점수).
- **Policy (정책, $\pi$)**: 특정 상태에서 어떤 행동을 할지 결정하는 규칙.

## 3. 주요 알고리즘 (Key Algorithms)

- **Q-Learning**: 행동 가치 함수(Q-Function)를 학습하여 최적의 행동을 선택합니다.
- **DQN (Deep Q-Network)**: Q-Learning에 [딥러닝(Deep Learning)](./DLBasic.md)을 결합하여 고차원 상태 공간(예: 게임 화면)을 처리합니다.
- **Policy Gradient**: 정책 신경망을 직접 최적화합니다. (예: PPO, TRPO)

## 4. RL과 [JEPA](./JEPA.md)
Yann LeCun의 **Autonomous Machine Intelligence (AMI)** 비전에서 RL은 중요한 구성 요소입니다. 하지만 그는 단순한 Model-Free RL보다는, 세계 모델(World Model)을 가진 Model-Based RL(또는 추론/계획 시스템)을 강조합니다.
- **[JEPA](./JEPA.md)**는 이러한 세계 모델을 학습하기 위한 아키텍처로 볼 수 있습니다. 에이전트가 자신의 행동 결과(미래 상태)를 예측할 수 있게 해줍니다.

## 5. 응용 분야 (Applications)
- 게임 (AlphaGo, StarCraft AI)
- 로봇 제어 (보행, 물체 조작)
- 자원 관리 및 최적화
