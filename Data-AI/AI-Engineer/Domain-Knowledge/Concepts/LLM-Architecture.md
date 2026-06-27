# LLM Architecture (Large Language Model)

## Overview
LLM(거대 언어 모델)은 수천억 개 파라미터와 방대한 텍스트 데이터로 학습된 신경망으로, 자연어 이해·생성·추론이 가능하다. GPT, Claude, Gemini, LLaMA가 대표 모델이다.

## Transformer 아키텍처 핵심

### Self-Attention 메커니즘
`
입력: "The cat sat on the mat"
Q (Query) × K (Key) → 주의 가중치 계산
주의 가중치 × V (Value) → 가중합 출력

"sat"을 처리할 때 "cat"에 높은 주의 → 문맥 이해
`

### LLM 주요 개념
| 개념 | 설명 |
|---|---|
| **Token** | LLM이 처리하는 텍스트 최소 단위 (~4 글자) |
| **Context Window** | 한 번에 처리 가능한 최대 토큰 수 |
| **Temperature** | 생성 무작위성 조절 (0=결정론적, 1=창의적) |
| **Top-p / Top-k** | 다음 토큰 선택 전략 |
| **Embedding** | 텍스트를 고차원 벡터로 변환 |

## LLM 활용 패턴

### Prompt Engineering
- **Zero-shot**: 예시 없이 태스크 지시
- **Few-shot**: 2-5개 예시 후 태스크 수행
- **Chain-of-Thought (CoT)**: "단계별로 생각하세요" → 추론 능력 향상

### Fine-tuning
- 도메인 특화 데이터로 기반 모델 추가 훈련
- LoRA (Low-Rank Adaptation): 파라미터 효율적 파인튜닝

### RAG (Retrieval-Augmented Generation)
- 벡터 DB에서 관련 문서 검색 → LLM에 컨텍스트로 제공
- 환각(Hallucination) 감소, 최신 정보 반영 가능

## Related Terms
- [[RAG-System-Design]] — LLM에 외부 지식을 결합하는 아키텍처
- [[Responsible-AI-Principles]] — LLM 활용 시 윤리·안전 원칙

## References
- [Attention Is All You Need (2017)](https://arxiv.org/abs/1706.03762)
- [Anthropic Model Card](https://www.anthropic.com/claude)
