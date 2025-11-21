# Model Compression (모델 경량화)

## 1. 개요 (Overview)
Model Compression(모델 경량화)은 딥러닝 모델의 크기(메모리 사용량)를 줄이고 연산 속도를 높이면서도, 성능(정확도) 저하를 최소화하는 기술입니다. 모바일 기기나 임베디드 시스템과 같이 자원이 제한된 환경에서 AI를 실행하기 위해 필수적입니다.

## 2. 주요 기법 (Key Techniques)

### 2.1. Pruning (가지치기)
신경망에서 중요도가 낮은(가중치 값이 0에 가까운) 연결이나 뉴런을 제거하는 방법입니다.
- **Unstructured Pruning**: 개별 가중치를 0으로 만듭니다. 희소 행렬(Sparse Matrix)이 되지만, 일반적인 하드웨어에서는 가속 효과를 보기 어려울 수 있습니다.
- **Structured Pruning**: 채널(Channel)이나 필터(Filter) 단위로 제거합니다. 모델 구조 자체가 작아져서 실제 속도 향상에 유리합니다.

### 2.2. Quantization (양자화)
가중치와 연산의 정밀도를 줄이는 방법입니다. 일반적으로 32비트 부동소수점(FP32)을 사용하는 모델을 16비트(FP16)나 8비트 정수(INT8)로 변환합니다.
- 메모리 사용량을 크게 줄이고 연산 속도를 높일 수 있습니다.

### 2.3. [Knowledge Distillation (지식 증류)](./KnowledgeDistillation.md)
큰 모델(Teacher)의 지식을 작은 모델(Student)에게 전달하여 학습시키는 방법입니다.

### 2.4. Low-Rank Factorization (저랭크 분해)
거대한 가중치 행렬을 여러 개의 작은 행렬의 곱으로 근사하여 파라미터 수를 줄입니다.

## 3. 관련 문서
- [Deep Learning Basics](./DLBasic.md)
- [Knowledge Distillation](./KnowledgeDistillation.md)
- [Edge AI](./EdgeAI.md)
