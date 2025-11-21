# Causal Inference (인과 추론)

## 1. 개요 (Overview)
Causal Inference(인과 추론)는 데이터로부터 단순한 상관관계(Correlation)가 아닌, 원인과 결과의 인과관계(Causality)를 밝혀내는 통계적 방법론입니다. "X가 변하면 Y도 변하는가?"에 대한 답을 구합니다.

## 2. 상관관계 vs 인과관계
- **상관관계**: 아이스크림 판매량이 늘어나면 익사 사고도 늘어난다. (둘 다 여름이라서 그럴 뿐, 아이스크림이 원인은 아님)
- **인과관계**: 기온이 오르면 아이스크림 판매량이 늘어난다. (기온 상승이 원인)

## 3. 주요 개념
- **Confounder (교란 변수)**: 원인 변수와 결과 변수 모두에 영향을 주는 제3의 변수. (위 예시에서의 '기온')
- **Intervention (개입, do-calculus)**: 변수를 강제로 특정 값으로 고정했을 때의 효과를 분석합니다. ($P(Y|do(X))$)
- **Counterfactuals (반사실)**: "만약 X가 일어나지 않았다면 Y는 어땠을까?"를 추정합니다.

## 4. AI와 인과 추론
현재의 딥러닝은 주로 상관관계를 학습합니다. 인과 추론을 결합하여 더 견고하고 설명 가능한 AI를 만들려는 연구가 활발합니다.

## 5. 관련 문서
- [Probability and Statistics](./ProbabilityStatistics.md)
- [Explainable AI](./ExplainableAI.md)
