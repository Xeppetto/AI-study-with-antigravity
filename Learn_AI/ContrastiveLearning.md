# Contrastive Learning (대조 학습)

## 1. 개요 (Overview)
Contrastive Learning(대조 학습)은 [자기지도 학습(Self-Supervised Learning)](./SelfSL.md)의 대표적인 방법론 중 하나입니다. 데이터 간의 유사성을 학습하여, 비슷한 데이터는 잠재 공간에서 가깝게, 다른 데이터는 멀게 배치하는 것을 목표로 합니다.

## 2. 작동 원리 (Mechanism)

1.  **Positive Pair 생성**: 하나의 이미지에 서로 다른 [데이터 증강(Data Augmentation)](./DataAugmentation.md)을 적용하여 두 개의 뷰(View)를 만듭니다. (예: 자르기, 색상 변경)
2.  **Negative Pair 정의**: 배치(Batch) 내의 다른 이미지들은 모두 서로 다른 데이터로 간주합니다.
3.  **Loss Function**: Positive Pair의 임베딩 거리는 좁히고, Negative Pair의 거리는 멀어지도록 학습합니다. (예: InfoNCE Loss)

## 3. 주요 모델 (Key Models)
- **SimCLR**: 간단한 구조와 강력한 데이터 증강을 통해 성능을 입증했습니다.
- **MoCo (Momentum Contrast)**: 큐(Queue)와 모멘텀 인코더를 사용하여 많은 수의 Negative Sample을 효율적으로 관리합니다.

## 4. 한계와 [JEPA](./JEPA.md)
Contrastive Learning은 Negative Sample(오답 데이터)이 반드시 필요하거나, 이를 대체할 복잡한 트릭이 필요합니다. 또한, 픽셀 수준의 불변성(Invariance)에 지나치게 의존할 수 있습니다.
- **[JEPA](./JEPA.md)**는 Negative Sample 없이, 오직 예측(Prediction)만을 통해 학습하므로 Contrastive Learning의 단점을 극복하고 더 효율적인 학습이 가능합니다.
