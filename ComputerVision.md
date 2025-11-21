# Computer Vision (컴퓨터 비전)

## 1. 개요 (Overview)
Computer Vision(컴퓨터 비전)은 기계가 시각적 데이터(이미지, 비디오)를 분석하고 이해하여 유의미한 정보를 추출하는 [인공지능(AI)](./ArtificialIntelligence.md)의 한 분야입니다. 인간의 시각 시스템을 모방하여 객체 탐지, 인식, 추적 등을 수행합니다.

## 2. 주요 태스크 (Key Tasks)

- **Image Classification (이미지 분류)**: 이미지가 무엇인지(예: 고양이, 강아지) 판별합니다.
- **[Object Detection (객체 탐지)](./ObjectDetection.md)**: 이미지 내의 객체 위치를 찾고(Bounding Box), 종류를 분류합니다.
- **[Semantic Segmentation](./SemanticSegmentation.md)**: 이미지의 모든 픽셀을 특정 클래스로 분류합니다.
- **Instance Segmentation**: 같은 클래스 내에서도 개별 객체를 구분합니다.

## 3. 핵심 기술 (Key Technologies)

### 3.1. [CNN (Convolutional Neural Networks)](./CNN.md)
이미지 처리에 특화된 딥러닝 아키텍처로, 이미지의 지역적 특징을 계층적으로 학습합니다.

### 3.2. [Vision Transformer (ViT)](./ViT.md)
NLP에서 성공한 Transformer 구조를 비전 분야에 적용한 모델로, 대규모 데이터셋에서 CNN을 능가하는 성능을 보이기도 합니다.

### 3.3. [Self-Supervised Learning in Vision](./SelfSL.md)
레이블 없는 대량의 이미지를 활용하여 시각적 표현을 학습하는 방법입니다.
- **[JEPA (Joint-Embedding Predictive Architecture)](./JEPA.md)**: 생성(Generation) 대신 예측(Prediction)을 통해 표현을 학습하는 최신 아키텍처.
- **[LeJEPA](./LeJEPA.md)**: 잠재 공간에서의 유클리드 기하학을 강조한 JEPA의 변형.

## 4. 응용 분야 (Applications)
- 자율 주행 자동차 (객체 인식, 차선 유지)
- 의료 영상 분석 (암 진단)
- 안면 인식 보안 시스템
