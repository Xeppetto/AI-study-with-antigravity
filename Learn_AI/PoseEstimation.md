# Pose Estimation (자세 추정)

## 1. 개요 (Overview)
Pose Estimation(자세 추정)은 이미지나 비디오에서 사람의 관절(Keypoints) 위치를 찾아내어 자세를 인식하는 [컴퓨터 비전](./ComputerVision.md) 기술입니다.

## 2. 주요 방식
- **Top-down**: 먼저 사람을 탐지(Detection)하고, 각 사람 영역 안에서 관절을 찾습니다. 정확도가 높지만 사람이 많으면 느려집니다.
- **Bottom-up**: 이미지 전체에서 모든 관절을 먼저 찾고, 이를 사람별로 연결(Grouping)합니다. 사람이 많아도 속도가 일정합니다.

## 3. 주요 모델
- **OpenPose**: Bottom-up 방식의 대표적인 모델로, PAF(Part Affinity Fields)를 사용하여 관절 간의 연결 관계를 학습합니다.
- **HRNet (High-Resolution Net)**: 고해상도 특징을 유지하여 정밀한 위치 추정이 가능합니다.

## 4. 응용 분야
- 행동 인식 (Action Recognition)
- 피트니스/스포츠 자세 교정
- 모션 캡처 (Motion Capture)

## 5. 관련 문서
- [Computer Vision](./ComputerVision.md)
- [Object Detection](./ObjectDetection.md)
