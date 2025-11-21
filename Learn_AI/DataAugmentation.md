# Data Augmentation (데이터 증강)

## 1. 개요 (Overview)
Data Augmentation(데이터 증강)은 기존의 학습 데이터를 변형하여 데이터의 양을 인위적으로 늘리는 기법입니다. 모델이 다양한 변형에 대해 강건(Robust)해지도록 돕고 과적합을 방지합니다.

## 2. 주요 기법 (Key Techniques)

### 2.1. 이미지 (Image)
- **Geometric**: 회전(Rotation), 뒤집기(Flip), 자르기(Crop), 확대/축소(Zoom).
- **Color**: 밝기, 대비, 채도 조절, 노이즈 추가.
- **Mixup / CutMix**: 두 이미지를 섞거나 일부를 잘라 붙여 새로운 이미지를 생성.

### 2.2. 텍스트 (Text)
- **Back-translation**: 다른 언어로 번역했다가 다시 원래 언어로 번역.
- **Synonym Replacement**: 유의어로 단어 교체.

## 3. [Self-Supervised Learning](./SelfSL.md)에서의 역할
[Contrastive Learning](./ContrastiveLearning.md)과 같은 자기지도 학습에서는 데이터 증강이 매우 중요합니다.
- 하나의 이미지에 서로 다른 증강을 적용하여 두 개의 뷰(Positive Pair)를 만들고, 모델이 이 둘을 "같은 것"으로 인식하도록 학습시킵니다.
- 즉, 데이터 증강은 모델이 학습해야 할 **불변성(Invariance)**을 정의하는 역할을 합니다.
