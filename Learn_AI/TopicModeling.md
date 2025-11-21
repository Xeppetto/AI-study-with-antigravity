# Topic Modeling (토픽 모델링)

## 1. 개요 (Overview)
Topic Modeling(토픽 모델링)은 문서 집합에서 추상적인 "주제(Topic)"를 발견하기 위한 통계적 모델링 기법입니다. 비지도 학습(Unsupervised Learning)의 일종입니다.

## 2. 주요 알고리즘
- **LDA (Latent Dirichlet Allocation, 잠재 디리클레 할당)**: 각 문서는 여러 토픽의 혼합으로 구성되어 있고, 각 토픽은 특정 단어들의 분포로 구성되어 있다고 가정합니다. 가장 고전적이고 널리 쓰이는 방법입니다.
- **BERTopic**: [BERT](./BERT.md) 임베딩과 클러스터링(HDBSCAN)을 결합하여 토픽을 추출합니다. 문맥을 고려하므로 LDA보다 품질이 좋은 경우가 많습니다.

## 3. 응용 분야
- 뉴스 기사 분류 및 트렌드 분석
- 고객 리뷰 분석
- 추천 시스템

## 4. 관련 문서
- [NLP](./NLP.md)
- [Clustering](./Clustering.md)
- [BERT](./BERT.md)
