# Transformer (트랜스포머)

## 1. 개요 (Overview)
Transformer(트랜스포머)는 2017년 Google이 "Attention Is All You Need" 논문에서 발표한 [딥러닝(Deep Learning)](./DLBasic.md) 아키텍처입니다. 기존의 순환 신경망(RNN)을 대체하며 자연어 처리(NLP) 분야를 혁신했고, 현재는 [컴퓨터 비전(Computer Vision)](./ComputerVision.md) 등 AI 전 분야의 표준이 되었습니다.

## 2. 핵심 메커니즘 (Key Mechanisms)

### 2.1. Self-Attention (셀프 어텐션)
입력 시퀀스 내의 각 요소가 다른 모든 요소와 어떤 관계가 있는지를 계산하여 문맥을 파악합니다. "The animal didn't cross the street because it was too tired"라는 문장에서 "it"이 "animal"을 가리킨다는 것을 알아내는 식입니다.

### 2.2. Multi-Head Attention
여러 개의 어텐션 메커니즘을 병렬로 수행하여 다양한 관점에서 정보를 포착합니다.

### 2.3. Positional Encoding
순서 정보가 없는 어텐션 메커니즘을 보완하기 위해, 입력 데이터의 위치 정보를 벡터에 더해줍니다.

## 3. 주요 변형 (Variants)

- **Encoder-only (BERT 계열)**: 문맥 이해에 강점. 분류, 질의응답 등에 사용.
- **Decoder-only (GPT 계열)**: 텍스트 생성에 강점. [Generative AI](./GenerativeAI.md)의 기반.
- **Encoder-Decoder (T5, Original Transformer)**: 번역, 요약 등에 사용.
- **Vision Transformer (ViT)**: 이미지를 패치(Patch) 단위로 쪼개어 트랜스포머에 입력하는 모델. [LeJEPA](./LeJEPA.md) 등의 백본으로 사용됩니다.

## 4. Transformer와 [JEPA](./JEPA.md)
[JEPA](./JEPA.md) 및 [LeJEPA](./LeJEPA.md) 아키텍처는 주로 Vision Transformer (ViT)를 인코더(Encoder)와 예측기(Predictor)로 사용합니다. Transformer의 강력한 표현 학습 능력을 활용하여 잠재 공간에서의 예측을 수행합니다.
