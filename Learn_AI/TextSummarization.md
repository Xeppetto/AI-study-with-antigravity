# Text Summarization (문서 요약)

## 1. 개요 (Overview)
Text Summarization(문서 요약)은 긴 텍스트에서 중요한 정보를 추출하거나 생성하여 짧은 요약문을 만드는 [자연어 처리(NLP)](./NLP.md) 기술입니다.

## 2. 종류
- **Extractive Summarization (추출 요약)**: 원문에서 중요하다고 판단되는 문장이나 단어를 그대로 뽑아서 요약합니다. (예: TextRank) 문법적으로 어색할 수 있습니다.
- **Abstractive Summarization (생성 요약)**: 원문의 의미를 이해하고, 새로운 문장을 생성하여 요약합니다. 사람이 요약하는 것과 비슷합니다. (예: [Seq2Seq](./MachineTranslation.md), [BART](./BERT.md), [T5](./Transformer.md))

## 3. 평가 지표
- **ROUGE (Recall-Oriented Understudy for Gisting Evaluation)**: 생성된 요약문과 사람이 작성한 참조 요약문(Reference) 사이의 N-gram 중복도를 측정합니다.

## 4. 관련 문서
- [NLP](./NLP.md)
- [Transformer](./Transformer.md)
- [GPT](./GPT.md)
