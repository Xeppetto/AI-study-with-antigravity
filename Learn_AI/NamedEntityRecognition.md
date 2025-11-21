# Named Entity Recognition (NER, 개체명 인식)

## 1. 개요 (Overview)
Named Entity Recognition(NER, 개체명 인식)은 텍스트에서 인물, 장소, 조직, 시간 등 미리 정의된 유형의 개체(Entity)를 찾아내고 분류하는 [자연어 처리(NLP)](./NLP.md) 기술입니다.

## 2. 예시
- 문장: "이순신 장군은 1592년에 한산도 대첩을 이끌었다."
- 결과:
    - 이순신: PERSON (인물)
    - 1592년: DATE (날짜)
    - 한산도: LOCATION (장소)

## 3. 주요 모델
- **Bi-LSTM + CRF**: 양방향 LSTM으로 문맥을 파악하고, CRF(Conditional Random Field)로 레이블 간의 제약 조건(예: B-PER 뒤에 I-ORG가 올 수 없음)을 고려하여 최적의 시퀀스를 찾습니다.
- **BERT-based**: [BERT](./BERT.md)와 같은 사전 학습 언어 모델을 미세 조정하여 높은 성능을 냅니다.

## 4. 응용 분야
- 정보 추출 (Information Extraction)
- 질문 답변 시스템 (QA)
- 자동 문서 요약

## 5. 관련 문서
- [NLP](./NLP.md)
- [RNN](./RNN.md)
- [BERT](./BERT.md)
