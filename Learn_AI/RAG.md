# RAG (Retrieval-Augmented Generation, 검색 증강 생성)

## 1. 개요 (Overview)
RAG(Retrieval-Augmented Generation)는 [LLM (Large Language Model)](./GPT.md)의 출력을 최적화하기 위해, 모델 외부의 신뢰할 수 있는 지식 베이스에서 관련 정보를 검색(Retrieval)하여 프롬프트에 추가(Augmentation)한 뒤 답변을 생성(Generation)하는 기술입니다.

## 2. 왜 필요한가?
- **Hallucination (환각) 감소**: 모델이 사실이 아닌 정보를 지어내는 것을 방지합니다.
- **최신 정보 반영**: 모델을 재학습하지 않고도 외부 데이터베이스만 업데이트하면 최신 정보를 답변할 수 있습니다.
- **도메인 특화**: 기업 내부 문서 등 모델이 학습하지 않은 비공개 데이터를 활용할 수 있습니다.

## 3. 작동 원리 (Workflow)
1.  **Indexing**: 문서를 청크(Chunk)로 나누고, 임베딩 모델을 통해 벡터로 변환하여 벡터 DB에 저장합니다.
2.  **Retrieval**: 사용자의 질문을 벡터로 변환하고, 벡터 DB에서 가장 유사한 청크를 검색합니다.
3.  **Generation**: 검색된 청크와 질문을 함께 프롬프트에 넣어 LLM에게 전달하고, LLM은 이를 바탕으로 답변을 생성합니다.

## 4. 관련 문서
- [GPT](./GPT.md)
- [Prompt Engineering](./PromptEngineering.md)
- [Vector Database](./VectorDatabase.md)
