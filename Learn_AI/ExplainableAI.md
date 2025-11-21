# Explainable AI (XAI, 설명 가능한 AI)

## 1. 개요 (Overview)
Explainable AI(XAI, 설명 가능한 AI)는 인공지능 모델의 결과나 예측 과정을 사람이 이해할 수 있도록 설명(Explanation)을 제공하는 기술입니다. "Black Box"라고 불리는 딥러닝 모델의 불투명성을 해결하기 위해 등장했습니다.

## 2. 왜 필요한가?
- **신뢰성(Trust)**: AI가 왜 그런 결정을 내렸는지 알아야 사용자가 결과를 신뢰할 수 있습니다.
- **투명성(Transparency)**: 의료, 금융, 법률 등 중요한 의사결정 분야에서 AI의 판단 근거를 요구합니다.
- **디버깅(Debugging)**: 모델이 잘못된 예측을 할 때 원인을 파악하고 수정하는 데 도움을 줍니다.

## 3. 주요 기법 (Key Techniques)

### 3.1. LIME (Local Interpretable Model-agnostic Explanations)
복잡한 모델을 국소적(Local)으로 근사하는 간단한 모델(예: 선형 회귀)을 학습시켜 설명을 제공합니다. 특정 입력 데이터 주변에서 모델이 어떻게 행동하는지 보여줍니다.

### 3.2. SHAP (SHapley Additive exPlanations)
게임 이론의 Shapley Value를 기반으로, 각 특징(Feature)이 예측 결과에 얼마나 기여했는지를 계산합니다.

### 3.3. Grad-CAM (Gradient-weighted Class Activation Mapping)
[CNN](./CNN.md) 모델에서 이미지의 어떤 부분이 예측에 중요한 역할을 했는지를 히트맵(Heatmap)으로 시각화합니다.

## 4. 관련 문서
- [Artificial Intelligence](./ArtificialIntelligence.md)
- [AIEthics](./AIEthics.md)
