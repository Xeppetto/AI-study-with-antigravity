# Object Tracking (객체 추적)

## 1. 개요 (Overview)
Object Tracking(객체 추적)은 비디오의 연속된 프레임에서 특정 객체의 위치 변화를 추적하는 [컴퓨터 비전](./ComputerVision.md) 기술입니다.

## 2. 종류
- **SOT (Single Object Tracking)**: 하나의 객체만 추적합니다. 첫 프레임에서 추적할 대상을 지정해줍니다.
- **MOT (Multi-Object Tracking)**: 여러 객체를 동시에 추적합니다. 각 객체에 고유한 ID를 부여하고 유지해야 합니다.

## 3. 주요 알고리즘 (MOT 중심)
- **SORT (Simple Online and Realtime Tracking)**: 칼만 필터(Kalman Filter)와 헝가리안 알고리즘(Hungarian Algorithm)을 사용하여 객체의 위치를 예측하고 매칭합니다.
- **DeepSORT**: SORT에 딥러닝 기반의 특징 추출(Re-ID)을 추가하여, 객체가 가려졌다가 다시 나타나도 ID를 유지할 수 있게 개선했습니다.

## 4. 관련 문서
- [Computer Vision](./ComputerVision.md)
- [Object Detection](./ObjectDetection.md)
