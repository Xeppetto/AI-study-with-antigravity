# Adversarial Attacks (적대적 공격)

## 1. 개요 (Overview)
Adversarial Attacks(적대적 공격)는 AI 모델, 특히 딥러닝 모델을 속이기 위해 의도적으로 조작된 입력(Adversarial Example)을 주입하는 공격 기술입니다. 사람의 눈에는 차이가 없어 보이지만, 모델은 완전히 다른 결과로 오분류하게 만듭니다.

## 2. 공격 유형
- **White-box Attack**: 공격자가 모델의 구조와 파라미터를 모두 알고 있는 상태에서 공격합니다. (예: FGSM, PGD)
- **Black-box Attack**: 공격자가 모델의 내부 정보를 모르고, 입력과 출력만 관찰할 수 있는 상태에서 공격합니다.

## 3. 대표적인 공격 기법
- **FGSM (Fast Gradient Sign Method)**: 손실 함수(Loss Function)의 기울기(Gradient) 방향으로 아주 약간의 노이즈를 추가하여 오차를 극대화합니다.
- **One-pixel Attack**: 단 하나의 픽셀만 변경하여 이미지를 오분류하게 만듭니다.

## 4. 방어 기법 (Defense)
- **Adversarial Training**: 적대적 예제들을 학습 데이터에 포함시켜 모델을 학습시킵니다. 모델의 견고성(Robustness)을 높이는 가장 효과적인 방법 중 하나입니다.
- **Defensive Distillation**: [Knowledge Distillation](./KnowledgeDistillation.md)을 이용하여 모델의 기울기를 숨기거나 부드럽게 만듭니다.

## 5. 관련 문서
- [Deep Learning Basics](./DLBasic.md)
- [Loss Functions](./LossFunctions.md)
