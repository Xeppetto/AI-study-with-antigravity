# Evolutionary Algorithms (진화 알고리즘)

## 1. 개요 (Overview)
Evolutionary Algorithms(진화 알고리즘)는 생물의 진화 과정(자연 선택, 돌연변이, 교배)을 모방하여 최적의 해를 찾는 메타휴리스틱(Metaheuristic) 알고리즘입니다.

## 2. 주요 과정 (Process)
1.  **Initialization**: 무작위로 초기 해집단(Population)을 생성합니다.
2.  **Evaluation**: 각 해(Individual)의 적합도(Fitness)를 평가합니다.
3.  **Selection**: 적합도가 높은 해를 선택하여 다음 세대의 부모로 삼습니다. (생존 경쟁)
4.  **Crossover (Recombination)**: 부모 해의 유전자를 섞어 자손을 생성합니다.
5.  **Mutation**: 일정 확률로 유전자에 변이를 주어 다양성을 확보합니다. (지역 최적해 탈출)
6.  **Replacement**: 새로운 세대로 교체하고 반복합니다.

## 3. 대표적인 알고리즘
- **Genetic Algorithm (GA, 유전 알고리즘)**: 가장 일반적인 형태의 진화 알고리즘.
- **Evolution Strategies (ES)**: 파라미터 최적화에 특화되어 있으며, 최근 강화학습과 결합하여 사용되기도 합니다.

## 4. 관련 문서
- [Optimization Algorithms](./OptimizationAlgorithms.md)
- [Reinforcement Learning](./ReinforcementLearning.md)
