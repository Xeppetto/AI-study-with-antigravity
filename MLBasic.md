# Machine Learning Basics (머신러닝 기초)

## 1. 개요 (Overview)
Machine Learning(머신러닝)은 인공지능(AI)의 하위 분야로, 컴퓨터가 명시적으로 프로그래밍되지 않고도 데이터로부터 학습하여 성능을 향상시키는 기술입니다. 데이터를 통해 패턴을 발견하고, 이를 바탕으로 예측이나 결정을 내리는 알고리즘을 구축하는 것이 핵심입니다.

## 2. 핵심 개념 (Key Concepts)

### 2.1. 데이터 (Data)
머신러닝의 원료입니다.
- **Feature (특징)**: 예측에 사용되는 입력 변수 (예: 집의 크기, 방의 개수).
- **Label (레이블/타겟)**: 예측하고자 하는 정답 (예: 집의 가격).

### 2.2. 모델 (Model)
데이터의 패턴을 학습한 수학적 구조입니다. 입력(Feature)을 받아 출력(Prediction)을 생성하는 함수로 볼 수 있습니다.

### 2.3. 학습 (Training)
모델의 파라미터(Parameter)를 조정하여 예측 오차를 최소화하는 과정입니다.
- **Loss Function (손실 함수)**: 예측값과 실제값의 차이를 측정하는 지표.
- **Optimization (최적화)**: 손실 함수를 최소화하기 위해 파라미터를 업데이트하는 방법.

## 3. 학습 유형 (Types of Learning)

### 3.1. Supervised Learning (지도 학습)
정답(Label)이 있는 데이터로 학습합니다.
- **Classification (분류)**: 데이터를 정해진 카테고리로 구분 (예: 스팸 메일 분류).
- **Regression (회귀)**: 연속적인 값을 예측 (예: 주가 예측).

### 3.2. Unsupervised Learning (비지도 학습)
정답이 없는 데이터에서 숨겨진 구조나 패턴을 찾습니다.
- **Clustering (군집화)**: 유사한 데이터끼리 그룹화.
- **Dimensionality Reduction (차원 축소)**: 데이터의 주요 특징을 유지하면서 차원을 줄임.

### 3.3. Reinforcement Learning (강화 학습)
에이전트(Agent)가 환경(Environment)과 상호작용하며 보상(Reward)을 최대화하는 행동 방식을 학습합니다.

### 3.4. [Self-Supervised Learning (SSL, 자기지도 학습)](./SelfSL.md)
레이블이 없는 데이터로부터 스스로 레이블을 생성하여 학습하는 방식으로, 최근 딥러닝 분야에서 매우 중요하게 다루어집니다.

## 4. 주요 알고리즘 (Algorithms)

- **Linear Regression / Logistic Regression**: 가장 기초적인 회귀 및 분류 알고리즘.
- **Decision Tree / Random Forest**: 의사결정 규칙을 나무 구조로 나타낸 모델.
- **SVM (Support Vector Machine)**: 데이터를 구분하는 최적의 경계선(Hyperplane)을 찾는 알고리즘.
- **K-Means Clustering**: 대표적인 군집화 알고리즘.
- **[Deep Learning (딥러닝)](./DLBasic.md)**: 인공 신경망을 이용한 고도화된 머신러닝 기법.

## 5. 사전 지식 (Prerequisites)

머신러닝을 깊이 있게 이해하기 위해서는 다음의 기초 지식이 필요합니다.

1.  **Mathematics**
    - Linear Algebra (선형대수): 행렬 연산, 벡터 공간.
    - Calculus (미적분): 기울기(Gradient), 편미분.
    - Probability & Statistics (확률 및 통계): 데이터 분포, 가설 검정.

2.  **Programming**
    - Python: 가장 널리 사용되는 언어.
    - Libraries: NumPy, Pandas, Scikit-learn, PyTorch/TensorFlow.
