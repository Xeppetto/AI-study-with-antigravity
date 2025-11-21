# Edge AI (에지 AI)

## 1. 개요 (Overview)
Edge AI(에지 AI)는 데이터를 클라우드 서버로 보내지 않고, 데이터가 생성되는 기기(Edge Device) 자체에서 AI 알고리즘을 실행하는 기술입니다. 스마트폰, IoT 센서, 자율주행차, 드론 등이 이에 해당합니다.

## 2. 장점 (Advantages)
- **Latency (지연 시간)**: 데이터 전송 과정이 없으므로 실시간 처리가 가능합니다. (예: 자율주행차의 급제동)
- **Privacy (프라이버시)**: 민감한 데이터가 기기 밖으로 나가지 않아 보안에 유리합니다.
- **Bandwidth (대역폭)**: 대용량 데이터를 서버로 전송할 필요가 없어 네트워크 비용을 절감합니다.
- **Reliability (신뢰성)**: 인터넷 연결이 끊겨도 독립적으로 동작할 수 있습니다.

## 3. 주요 챌린지
- **Resource Constraints**: 에지 디바이스는 서버에 비해 컴퓨팅 파워, 메모리, 배터리가 매우 제한적입니다.
- 따라서 [Model Compression](./ModelCompression.md) 기술과 전용 AI 가속기(NPU)의 활용이 중요합니다.

## 4. TinyML
Edge AI의 하위 분야로, 마이크로컨트롤러(MCU)와 같은 초저전력 장치에서 머신러닝을 구동하는 기술을 말합니다.

## 5. 관련 문서
- [Model Compression](./ModelCompression.md)
- [Federated Learning](./FederatedLearning.md)
