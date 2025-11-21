# Swarm Intelligence (집단 지성)

## 1. 개요 (Overview)
Swarm Intelligence(집단 지성)는 개미, 벌, 새 떼와 같은 사회적 곤충이나 동물의 집단 행동에서 영감을 받은 AI 알고리즘입니다. 개별 개체는 단순한 규칙을 따르지만, 집단 전체로는 복잡하고 지능적인 문제를 해결합니다.

## 2. 주요 알고리즘 (Key Algorithms)

### 2.1. PSO (Particle Swarm Optimization)
새 떼가 먹이를 찾는 과정을 모방한 최적화 알고리즘입니다.
- 각 입자(Particle)는 자신의 최적 위치(pBest)와 전체 무리의 최적 위치(gBest)를 향해 이동합니다.
- [Optimization Algorithms](./OptimizationAlgorithms.md)의 일종으로, 미분 불가능한 문제에서도 잘 작동합니다.

### 2.2. ACO (Ant Colony Optimization)
개미가 페로몬(Pheromone)을 남겨 최단 경로를 찾는 과정을 모방합니다.
- 외판원 문제(TSP)와 같은 경로 최적화 문제에 주로 사용됩니다.

## 3. 특징
- **Decentralized (탈중앙화)**: 중앙 제어 장치가 없습니다.
- **Robustness (견고성)**: 일부 개체가 고장 나도 전체 시스템은 작동합니다.

## 4. 관련 문서
- [Optimization Algorithms](./OptimizationAlgorithms.md)
- [Evolutionary Algorithms](./EvolutionaryAlgorithms.md)
