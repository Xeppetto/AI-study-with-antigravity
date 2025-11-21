# Collaborative Filtering (협업 필터링)

## 1. 개요 (Overview)
Collaborative Filtering(CF, 협업 필터링)은 [추천 시스템](./RecommenderSystems.md)의 핵심 알고리즘으로, 많은 사용자들로부터 얻은 기호 정보(평점, 구매 이력 등)를 바탕으로 사용자의 관심사를 예측합니다. "나와 비슷한 취향을 가진 사람들이 좋아한 것은 나도 좋아할 것이다"라는 가정에 기반합니다.

## 2. 종류
- **User-based CF**: 나와 유사한 패턴을 가진 사용자(Neighbor)를 찾아, 그들이 좋아한 아이템을 추천합니다.
- **Item-based CF**: 내가 과거에 좋아했던 아이템과 유사한 아이템을 추천합니다. (예: 아이템 A를 산 사람들이 아이템 B도 많이 샀다면, A를 산 나에게 B를 추천)

## 3. 구현 방법
- **Memory-based**: 유사도(Cosine Similarity, Pearson Correlation)를 직접 계산합니다.
- **Model-based**: 머신러닝 모델을 학습시킵니다. 대표적으로 **Matrix Factorization (행렬 분해)**가 있습니다. 사용자-아이템 행렬을 잠재 요인(Latent Factor) 행렬의 곱으로 분해하여 빈칸(예측 평점)을 채웁니다.

## 4. 문제점
- **Cold Start**: 새로운 사용자나 아이템에 대한 데이터가 없으면 추천이 불가능합니다.

## 5. 관련 문서
- [Recommender Systems](./RecommenderSystems.md)
- [Machine Learning Basics](./MLBasic.md)
