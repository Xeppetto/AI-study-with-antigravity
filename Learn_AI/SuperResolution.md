# Super Resolution (초해상도)

## 1. 개요 (Overview)
Super Resolution(SR, 초해상도)은 저해상도(Low Resolution) 이미지를 고해상도(High Resolution) 이미지로 복원하는 기술입니다.

## 2. 주요 접근법
- **Interpolation (보간법)**: 주변 픽셀 값을 이용하여 빈 픽셀을 채웁니다. (Bilinear, Bicubic 등) 흐릿해지는 단점이 있습니다.
- **Deep Learning (SRCNN, EDSR)**: [CNN](./CNN.md)을 이용하여 저해상도와 고해상도 이미지 사이의 매핑 관계를 학습합니다.
- **GAN-based (SRGAN)**: [GAN](./GAN.md)을 사용하여 사람이 보기에 더 자연스럽고 디테일이 살아있는 이미지를 생성합니다.

## 3. 응용 분야
- 구형 영상 복원
- 의료 영상 화질 개선
- CCTV 영상 개선

## 4. 관련 문서
- [Computer Vision](./ComputerVision.md)
- [CNN](./CNN.md)
- [GAN](./GAN.md)
