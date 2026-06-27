# RAG System Design (Retrieval-Augmented Generation)

## Overview
RAG는 LLM의 정적 지식 한계를 극복하기 위해 실시간 문서 검색과 생성을 결합한 아키텍처다. LLM의 추론 능력 + 최신·도메인 특화 지식을 결합할 수 있다.

## RAG 파이프라인

`
[질문] "2025년 우리 회사 제품 가격은?"
   ↓
[임베딩] 질문을 벡터로 변환
   ↓
[벡터 검색] 벡터 DB에서 유사 문서 검색 (Cosine Similarity)
   ↓
[컨텍스트 구성] 검색 결과를 프롬프트에 삽입
   ↓
[LLM 생성] 컨텍스트 기반으로 답변 생성
   ↓
[응답] "2025년 기준 제품 A는 월 "
`

## 핵심 구성요소

### 1. 문서 처리 (Ingestion)
- 문서 로드 (PDF, Word, 웹페이지)
- 청킹(Chunking): 문서를 적절한 크기로 분할
- 임베딩 생성 및 벡터 DB 저장

### 2. 벡터 데이터베이스
| DB | 특징 |
|---|---|
| **Pinecone** | 완전 관리형, 프로덕션 안정적 |
| **Weaviate** | 오픈소스, 하이브리드 검색 |
| **Chroma** | 로컬 개발·프로토타이핑 |
| **pgvector** | PostgreSQL 확장, 기존 DB 통합 |

### 3. 검색 전략
- **Semantic Search**: 벡터 유사도 기반 (의미 검색)
- **Hybrid Search**: BM25(키워드) + 벡터 결합 (더 강건)
- **Reranking**: 검색 결과를 LLM으로 재정렬

## RAG 평가 지표
- **Faithfulness**: 답변이 검색된 문서에 근거하는가?
- **Answer Relevance**: 질문과 답변의 관련성
- **Context Precision/Recall**: 검색 품질

## Related Terms
- [[LLM-Architecture]] — RAG에서 생성을 담당하는 핵심 컴포넌트
- [[Responsible-AI-Principles]] — RAG 시스템 설계 시 윤리 고려

## References
- [RAG Paper — Lewis et al. (2020)](https://arxiv.org/abs/2005.11401)
- [LangChain Documentation](https://docs.langchain.com/)
