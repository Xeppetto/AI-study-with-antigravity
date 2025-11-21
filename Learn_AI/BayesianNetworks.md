# Bayesian Networks (베이지안 네트워크)

## 1. 개요 (Overview)
Bayesian Networks(베이지안 네트워크)는 변수들 간의 확률적 의존 관계를 그래프(DAG, Directed Acyclic Graph)로 표현한 확률 모델입니다. 불확실한 상황에서의 추론과 예측에 강력합니다.

## 2. 구조 (Structure)
- **Nodes (노드)**: 확률 변수(Random Variables)를 나타냅니다. (예: 비가 옴, 잔디가 젖음)
- **Edges (엣지)**: 변수 간의 인과 관계나 의존성을 나타냅니다. (비가 옴 -> 잔디가 젖음)
- **CPT (Conditional Probability Table)**: 각 노드가 부모 노드의 상태에 따라 가질 수 있는 조건부 확률을 표로 나타냅니다.

## 3. 특징
- **Inference (추론)**: 일부 변수의 값을 알 때(Evidence), 다른 변수의 확률을 계산할 수 있습니다. (진단, 예측)
- **Learning**: 데이터로부터 그래프 구조와 CPT를 학습할 수 있습니다.

## 4. 응용 분야
- 의료 진단 시스템
- 고장 진단
- 유전자 네트워크 분석

## 5. 관련 문서
- [Probability and Statistics](./ProbabilityStatistics.md)
- [Machine Learning Basics](./MLBasic.md)
