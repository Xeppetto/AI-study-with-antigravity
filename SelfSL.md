# Self-Supervised Learning (SSL, 자기지도 학습)

## 1. 개요 (Overview)
Self-Supervised Learning(SSL, 자기지도 학습)은 레이블이 지정되지 않은(Unlabeled) 대규모 데이터로부터 데이터 자체의 구조나 패턴을 학습하여 유용한 표현(Representation)을 얻는 [머신러닝(Machine Learning)](./MLBasic.md) 패러다임입니다.

기존의 [지도 학습(Supervised Learning)](./MLBasic.md)은 사람이 일일이 레이블링한 데이터가 필요하여 비용과 시간이 많이 소요되는 반면, SSL은 데이터 그 자체로부터 "Pseudo-label"을 생성하여 학습하므로 데이터 확장성이 매우 뛰어납니다. 이렇게 학습된 모델은 적은 양의 레이블 데이터만으로도 다운스트림 작업(Downstream Tasks)에서 뛰어난 성능을 발휘합니다. Yann LeCun은 이를 "케이크의 본체(The Cake)"에 비유하며, 지도 학습은 "케이크 위의 장식(The Icing)"에 불과하다고 강조했습니다.

## 2. 핵심 개념 (Key Concepts)

### 2.1. Pretext Task (프리텍스트 태스크)
모델이 데이터의 표현을 학습하도록 강제하기 위해 정의된 "가짜" 문제들입니다. 사람이 레이블을 제공하지 않아도 데이터 자체에서 정답을 생성할 수 있습니다.
- **예시**: 이미지의 일부를 가리고 복원하기, 문장의 빈칸 채우기, 비디오의 순서 맞추기, 이미지를 회전시키고 회전 각도 맞추기 등.

### 2.2. Representation Learning (표현 학습)
SSL의 주 목적은 최종 작업(분류, 감지 등)을 직접 수행하는 것이 아니라, 데이터의 의미론적 특징(Semantic Features)을 잘 담고 있는 벡터 표현(Embedding)을 학습하는 것입니다. 잘 학습된 표현은 다양한 작업으로 전이(Transfer)될 수 있습니다.

### 2.3. Downstream Task (다운스트림 태스크)
SSL로 사전 학습(Pre-training)된 모델을 가져와서, 실제로 풀고자 하는 문제(예: 이미지 분류, 객체 탐지, 감정 분석 등)에 맞게 미세 조정(Fine-tuning)하는 단계입니다.

## 3. 주요 방법론 (Main Approaches)

### 3.1. Generative Methods (생성적 방법)
데이터의 일부를 가리거나 손상시킨 후, 원본 데이터를 복원하도록 학습합니다.
- **Autoencoders (AE), Variational Autoencoders (VAE)**
- **Masked Language Modeling (MLM)**: BERT와 같이 문장의 일부 단어를 [MASK]로 가리고 예측.
- **Masked Image Modeling (MIM)**: MAE(Masked Autoencoder)와 같이 이미지의 패치를 가리고 픽셀 값을 예측.

### 3.2. Contrastive Methods (대조적 방법)
데이터 간의 유사성을 학습합니다. 같은 데이터에서 나온 뷰(View)들은 가깝게, 다른 데이터들은 멀게 배치되도록 학습합니다.
- **SimCLR, MoCo (Momentum Contrast)**: 데이터 증강(Augmentation)을 통해 만든 Positive Pair와 다른 이미지인 Negative Pair를 구분.
- **CLIP**: 텍스트와 이미지 쌍의 관계를 학습.

### 3.3. Joint-Embedding Methods (결합 임베딩 방법)
생성적 방법의 비효율성(픽셀 단위 복원)과 대조적 방법의 단점(Negative Sample 필요)을 극복하기 위해 등장했습니다.
- **BYOL (Bootstrap Your Own Latent)**: Negative Sample 없이 Positive Pair만으로 학습하며, 붕괴(Collapse)를 막기 위해 비대칭 구조(Online/Target Network)를 사용.
- **SimSiam**: Stop-gradient 연산을 통해 붕괴 방지.
- **[JEPA (Joint-Embedding Predictive Architecture)](./JEPA.md)**: 잠재 공간에서의 예측을 수행.

## 4. 주요 특징 및 장점 (Features & Benefits)

1.  **데이터 효율성**: 레이블이 없는 방대한 데이터를 활용할 수 있어 데이터 구축 비용을 획기적으로 절감합니다.
2.  **전이 학습 능력**: 다양한 작업에 일반화될 수 있는 강력한 특징을 학습하므로, 적은 레이블 데이터로도 높은 성능을 낼 수 있습니다(Few-shot Learning).
3.  **인간 학습 방식 모사**: 아기가 세상을 관찰하며 물리 법칙을 깨닫는 것처럼, 데이터의 내재적 구조를 스스로 학습합니다.

## 5. 사전 지식 (Prerequisites)

Self-Supervised Learning을 깊이 있게 이해하기 위해서는 다음의 개념들에 대한 사전 지식이 필요합니다. (추후 별도의 문서로 상세히 설명될 예정입니다.)

1.  **[Machine Learning Basics (머신러닝 기초)](./MLBasic.md)**
    - [Supervised vs. Unsupervised Learning](./MLBasic.md)
    - Overfitting & Underfitting
    - [Loss Functions (Cross-Entropy, MSE)](./DLBasic.md)

2.  **[Deep Learning Architectures (딥러닝 아키텍처)](./DLBasic.md)**
    - CNN (Convolutional Neural Networks) - ResNet 등
    - Transformer (Attention Mechanism) - BERT, ViT
    - RNN/LSTM (Sequential Data)

3.  **Information Theory (정보이론)**
    - Mutual Information (상호 의존정보)
    - Entropy & Cross-Entropy
    - KL Divergence

4.  **Data Augmentation (데이터 증강)**
    - Random Crop, Flip, Color Jittering, Gaussian Blur 등
    - Invariance (불변성) 학습을 위한 증강의 역할

