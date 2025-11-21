# Neuromorphic Computing (뉴로모픽 컴퓨팅)

## 1. 개요 (Overview)
Neuromorphic Computing(뉴로모픽 컴퓨팅)은 인간 뇌의 신경 구조와 작동 방식을 하드웨어 및 소프트웨어로 모방하려는 컴퓨팅 기술입니다. 기존의 폰 노이만(Von Neumann) 구조의 한계(메모리 병목 현상, 전력 소모)를 극복하고자 합니다.

## 2. 핵심 기술: SNN (Spiking Neural Networks)
기존의 [인공 신경망(ANN)](./NeuralNetworks.md)이 실수값(Continuous Value)을 주고받는 것과 달리, SNN은 뇌의 뉴런처럼 **스파이크(Spike)**라는 전기 신호를 통해 정보를 전달합니다.
- **Event-driven**: 입력 신호(이벤트)가 있을 때만 작동하므로 전력 효율이 매우 높습니다.
- **Time-dependent**: 시간적인 정보(Timing)를 처리하는 데 유리합니다.

## 3. 하드웨어
- **Intel Loihi**: 인텔이 개발한 뉴로모픽 칩.
- **IBM TrueNorth**: IBM이 개발한 저전력 뉴로모픽 프로세서.

## 4. 응용 분야
- 초저전력 에지 디바이스
- 실시간 센서 데이터 처리 (예: 이벤트 기반 카메라)
- 뇌 과학 연구

## 5. 관련 문서
- [Neural Networks](./NeuralNetworks.md)
- [Edge AI](./EdgeAI.md)
