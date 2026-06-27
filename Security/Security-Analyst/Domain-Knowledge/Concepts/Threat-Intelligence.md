# Threat Intelligence

## Overview
위협 인텔리전스(Threat Intelligence)는 사이버 위협 행위자·기법·지표에 관한 증거 기반 지식으로, 보안 의사결정을 지원한다. 단순 데이터가 아닌 실행 가능한 인사이트를 제공해야 진정한 인텔리전스다.

## 위협 인텔리전스 유형

| 유형 | 대상 | 시간 | 예시 |
|---|---|---|---|
| **Strategic** | 경영진 | 장기 | 위협 행위자 동향, 산업별 위협 |
| **Tactical** | 보안팀 | 중기 | TTPs (전술·기법·절차), MITRE ATT&CK |
| **Operational** | 사고 대응팀 | 단기 | 특정 캠페인 세부사항 |
| **Technical** | SOC 분석가 | 실시간 | IoC (침해 지표) — IP, 해시, 도메인 |

## IoC (Indicators of Compromise) 유형
- **IP 주소**: 알려진 C2 서버, 스캐너 IP
- **도메인**: 악성코드 C2 도메인, 피싱 도메인
- **해시**: 알려진 악성 파일의 MD5/SHA256
- **URL**: 악성 다운로드 URL
- **이메일**: 피싱 발신자 주소

## 위협 인텔리전스 공유 프레임워크

### STIX (Structured Threat Intelligence eXpression)
- 위협 인텔리전스 표준화 형식

### TAXII (Trusted Automated eXchange of Intelligence)
- 위협 인텔리전스 공유 프로토콜

### MITRE ATT&CK Framework
- 실제 공격자의 TTPs를 매핑한 지식 베이스
- Matrix: Enterprise, Mobile, ICS
- 탐지 룰 개발, 레드팀 계획에 활용

## 위협 정보 소스
- **상용**: Recorded Future, Mandiant Threat Intelligence
- **오픈소스**: AlienVault OTX, VirusTotal, MISP
- **정부**: CISA, KISA (한국)

## Related Terms
- [[SOC-Operations]] — 위협 인텔리전스를 소비하는 팀
- [[Incident-Response-Principles]] — 인텔리전스로 사고 대응 향상

## References
- [MITRE ATT&CK](https://attack.mitre.org/)
- [Threat Intelligence 101](https://www.cisa.gov/topics/critical-infrastructure-security-and-resilience/sharing-cyber-threat-indicators)
