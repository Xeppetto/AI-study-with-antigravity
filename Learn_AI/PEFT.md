# PEFT (Parameter-Efficient Fine-Tuning)

## 1. 개요 (Overview)
PEFT(Parameter-Efficient Fine-Tuning)는 거대한 사전 학습 모델(Pre-trained Model) 전체를 미세 조정(Fine-tuning)하는 대신, 아주 적은 수의 파라미터만 학습하여 모델을 특정 태스크에 적응시키는 기술입니다.

## 2. 장점
- **비용 절감**: 전체 파라미터를 업데이트하는 Full Fine-tuning에 비해 메모리 사용량과 학습 시간이 획기적으로 줄어듭니다.
- **저장 공간 절약**: 모델 전체를 저장할 필요 없이, 학습된 소량의 파라미터만 저장하면 됩니다.

## 3. 주요 기법
- **LoRA (Low-Rank Adaptation)**: 가중치 업데이트 행렬을 두 개의 저랭크 행렬의 곱으로 분해하여 학습합니다. 가장 널리 사용되는 방식입니다.
- **Adapter**: 트랜스포머 레이어 사이에 작은 신경망 모듈(Adapter)을 삽입하여 학습합니다.
- **P-Tuning / Prefix Tuning**: 프롬프트 임베딩 자체를 학습 가능한 파라미터로 두고 최적화합니다.

## 4. 관련 문서
- [Transfer Learning](./TransferLearning.md)
- [GPT](./GPT.md)
- [Transformer](./Transformer.md)
