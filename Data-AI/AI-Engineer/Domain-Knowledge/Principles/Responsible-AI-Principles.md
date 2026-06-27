# Responsible AI Principles

## Overview
책임 있는 AI(Responsible AI)는 AI 시스템이 안전하고 공정하며 투명하게 작동하도록 보장하는 원칙·프레임워크다. LLM과 생성형 AI의 확산으로 더욱 중요해진 분야다.

## 핵심 원칙 (주요 기관 공통)

### 1. Fairness (공정성)
- 보호 속성(인종·성별·연령)에 따른 편향 없음
- 훈련 데이터 편향 → 모델 편향으로 증폭될 수 있음
- 편향 탐지: 그룹별 성능 지표 차이 측정

### 2. Reliability & Safety (신뢰성·안전성)
- 예상치 못한 입력에도 안전하게 동작
- LLM: Hallucination 방지, 유해 콘텐츠 차단
- 레드팀 테스트(Red Teaming)로 취약점 발견

### 3. Privacy & Security (개인정보·보안)
- 훈련 데이터에서 개인정보 추출 방지 (Memorization 공격)
- 차분 프라이버시(Differential Privacy)로 개인 데이터 보호
- GDPR·AI Act 준수

### 4. Inclusiveness (포용성)
- 다양한 사용자 그룹이 동등하게 혜택
- 접근성 고려, 저자원 언어 지원

### 5. Transparency (투명성)
- 모델 의사결정 설명 가능 (XAI, LIME, SHAP)
- 모델 카드(Model Card)로 성능·한계 공개
- 사용자가 AI임을 인지하게 함

### 6. Accountability (책임)
- AI 결정의 영향에 대해 책임질 사람/조직 명확화
- 고위험 의사결정(의료·법률·금융)에서 인간 감독 필수

## AI 안전 체계
- **Anthropic Constitutional AI** — 원칙 기반 AI 훈련
- **EU AI Act** — 위험 수준별 규제 프레임워크
- **NIST AI RMF** — AI 위험 관리 프레임워크

## Related Terms
- [[LLM-Architecture]] — 책임 있는 AI 원칙이 적용되는 핵심 기술
- [[RAG-System-Design]] — Hallucination 감소로 신뢰성 향상

## References
- [Microsoft Responsible AI Principles](https://www.microsoft.com/en-us/ai/responsible-ai)
- [EU AI Act](https://artificialintelligenceact.eu/)
