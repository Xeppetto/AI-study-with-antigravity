# Generative AI (생성형 AI)

## 1. 개요 (Overview)
Generative AI(생성형 AI)는 데이터의 패턴과 구조를 학습하여, 기존 데이터와 유사하지만 새로운 콘텐츠(텍스트, 이미지, 오디오, 비디오 등)를 만들어내는 [인공지능(AI)](./ArtificialIntelligence.md) 기술입니다.

## 2. 주요 모델 (Key Models)

### 2.1. GAN (Generative Adversarial Networks)
생성자(Generator)와 판별자(Discriminator)가 경쟁하며 학습하는 구조입니다. 이미지가 매우 사실적이지만 학습이 불안정할 수 있습니다.

### 2.2. VAE (Variational Autoencoders)
입력 데이터를 잠재 공간(Latent Space)으로 인코딩한 후 다시 디코딩하여 생성합니다. 확률적 분포를 학습합니다.

### 2.3. Diffusion Models
데이터에 노이즈를 점진적으로 추가했다가 다시 제거하는 과정을 학습하여 고품질의 이미지를 생성합니다. (예: Stable Diffusion, DALL-E)

### 2.4. LLM (Large Language Models)
대규모 텍스트 데이터로 학습된 트랜스포머 기반 모델로, 인간과 유사한 텍스트를 생성합니다. (예: GPT-4, Claude, Gemini)

## 3. Generative AI vs. [JEPA](./JEPA.md)
Yann LeCun은 픽셀 단위의 생성(Generative) 모델이 비효율적이라고 비판하며, **[JEPA (Joint-Embedding Predictive Architecture)](./JEPA.md)**를 대안으로 제시했습니다.
- **Generative AI**: $x$의 모든 세부 사항(픽셀 등)을 예측/생성하려고 함. (계산 비용 높음, 불필요한 디테일에 집중)
- **JEPA**: 추상화된 잠재 공간(Latent Space)에서 $x$의 표현(Representation)을 예측함. (효율적, 의미론적 정보에 집중)

## 4. 응용 분야 (Applications)
- 콘텐츠 창작 (글쓰기, 그림 그리기, 음악 작곡)
- 코드 생성 및 보조
- 데이터 증강 (Data Augmentation)
