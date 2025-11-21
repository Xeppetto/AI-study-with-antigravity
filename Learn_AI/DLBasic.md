# Deep Learning Basics (딥러닝 기초)

## 1. 개요 (Overview)
Deep Learning(딥러닝)은 [머신러닝(Machine Learning)](./MLBasic.md)의 한 분야로, 인간의 뇌 구조에서 영감을 받은 인공 신경망(Artificial Neural Networks)을 사용하여 데이터로부터 복잡한 패턴과 특징을 학습하는 기술입니다. "Deep"이라는 용어는 신경망이 여러 개의 은닉층(Hidden Layers)으로 구성되어 있음을 의미하며, 이를 통해 데이터의 계층적 표현(Hierarchical Representation)을 자동으로 학습할 수 있습니다.

## 2. 핵심 개념 (Key Concepts)

### 2.1. 인공 신경망 (Artificial Neural Networks)
입력층(Input Layer), 은닉층(Hidden Layers), 출력층(Output Layer)으로 구성된 뉴런들의 연결 구조입니다. 각 뉴런은 입력을 받아 가중치(Weight)와 연산하고, 활성화 함수(Activation Function)를 거쳐 다음 층으로 신호를 전달합니다.

### 2.2. 활성화 함수 (Activation Functions)
신경망에 비선형성(Non-linearity)을 부여하여 복잡한 함수를 근사할 수 있게 합니다.
- **ReLU (Rectified Linear Unit)**: $f(x) = \max(0, x)$. 학습 속도가 빠르고 기울기 소실 문제를 완화하여 가장 널리 사용됩니다.
- **Sigmoid / Tanh**: 출력을 특정 범위로 제한하지만, 깊은 망에서는 기울기 소실(Vanishing Gradient) 문제가 발생할 수 있습니다.
- **Softmax**: 다중 클래스 분류 문제의 출력층에서 사용되며, 출력의 합이 1이 되도록 정규화하여 확률로 해석할 수 있게 합니다.

### 2.3. 역전파 (Backpropagation)
예측값과 실제값의 차이(Loss)를 최소화하기 위해, 출력층에서 입력층 방향으로 오차를 전파하며 가중치를 업데이트하는 알고리즘입니다. 미분의 연쇄 법칙(Chain Rule)을 기반으로 합니다.

## 3. 주요 아키텍처 (Architectures)

### 3.1. [CNN (Convolutional Neural Networks)](./CNN.md)
이미지와 같은 격자 구조 데이터 처리에 특화된 신경망입니다. Convolution Layer와 Pooling Layer를 통해 이미지의 지역적 특징(Edge, Texture 등)을 효과적으로 추출합니다. (예: ResNet, EfficientNet)

### 3.2. [RNN (Recurrent Neural Networks)](./RNN.md)
순차 데이터(Sequential Data) 처리에 적합하며, 이전 시점의 정보가 다음 시점의 입력으로 사용되는 순환 구조를 가집니다. (예: LSTM, GRU)

### 3.3. [Transformer](./Transformer.md)
[Attention](./AttentionMechanism.md) 메커니즘을 기반으로 하여 시퀀스 데이터의 장거리 의존성(Long-range Dependency)을 효과적으로 학습합니다. NLP 분야를 혁신했으며, 최근에는 비전 분야([ViT](./ViT.md))에서도 널리 사용됩니다.

## 4. 최적화 (Optimization)

손실 함수(Loss Function)를 최소화하는 파라미터를 찾기 위한 알고리즘입니다.
- **Gradient Descent (GD)**: 전체 데이터에 대해 기울기를 계산하여 업데이트 (느림). ([참고](./OptimizationAlgorithms.md))
- **Stochastic Gradient Descent (SGD)**: 미니 배치(Mini-batch) 단위로 기울기를 계산하여 업데이트 (빠르지만 불안정).
- **Adam (Adaptive Moment Estimation)**: 모멘텀(Momentum)과 적응형 학습률(Adaptive Learning Rate)을 결합하여 빠르고 안정적인 수렴을 돕습니다.

## 5. 손실 함수 (Loss Functions)

모델의 예측이 실제 정답과 얼마나 다른지를 측정하는 함수입니다.
- **MSE (Mean Squared Error)**: 회귀(Regression) 문제에서 주로 사용. ([참고](./LossFunctions.md))
- **Cross-Entropy Loss**: 분류(Classification) 문제에서 주로 사용. 확률 분포 간의 차이를 측정합니다. ([참고](./LossFunctions.md))
