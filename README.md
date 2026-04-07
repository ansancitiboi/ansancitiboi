# 최태웅 — Backend Developer

> Race Condition, 분산 락, 이벤트 정합성 같은 백엔드 문제를 직접 해결한 개발자입니다.

Java/Spring 기반 백엔드 개발자로, 대규모 트래픽 환경에서의 동시성 제어와 이벤트 기반 아키텍처 설계에 집중합니다.

---

## 🛠 Tech Stack

**Backend**
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat&logo=spring-boot&logoColor=white)
![Spring Batch](https://img.shields.io/badge/Spring_Batch-6DB33F?style=flat&logo=spring&logoColor=white)

**Database / Messaging**
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat&logo=redis&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat&logo=mongodb&logoColor=white)
![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?style=flat&logo=elasticsearch&logoColor=white)
![Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=flat&logo=apache-kafka&logoColor=white)

**Infra / Frontend**
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![AWS EC2](https://img.shields.io/badge/AWS_EC2-FF9900?style=flat&logo=amazon-aws&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=github-actions&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)

---

## 🚀 Projects

### DolChat — 고가용성 마이크로서비스 팬덤 플랫폼
> Java 21 · Spring Boot 3.4 · MSA (14 services) · Kafka · Redis · MongoDB · Elasticsearch

아이돌과 팬이 실시간으로 소통하는 플랫폼. 연말 시상식 등 Spiky Traffic 환경에서 채팅·투표·랭킹·알림이 동시에 안정적으로 동작하는 것을 목표로 설계.

- **실시간 채팅**: STOMP + Kafka → Redis Pub/Sub 브릿지로 다중 서버 브로드캐스팅
- **동시성 제어**: Redis Lua Script 원자적 연산으로 중복 투표 방지, Redis 분산 락으로 좌석 예매 Race Condition 차단
- **이벤트 정합성**: Transactional Outbox Pattern + `@TransactionalEventListener(AFTER_COMMIT)`으로 DB-Kafka 이중 쓰기 문제 해소
- **보안**: JWT Refresh Token Rotation + Aho-Corasick Leet-speak 욕설 탐지
- **DevOps**: 변경된 서비스만 빌드하는 선택적 CI/CD (14개 서비스 모노레포)

[📂 Repository](https://github.com/olatedis/idol)

---

### F1pitwall — F1 실시간 레이싱 데이터 플랫폼
> Java 25 · Spring Boot 4.0.5 · Spring Batch 6 · Redis · Elasticsearch · React

OpenF1 공개 API를 활용해 레이스 중 순위 변동·피트스톱·세이프티카 이벤트를 감지하고, 구독한 드라이버 기준으로 SSE 알림을 제공하는 개인 프로젝트.

- **실시간 감지**: 3초 폴링 + Redis 상태 비교로 DB 조회 없이 O(1) 변화 감지 후 SSE 푸시
- **배치 파이프라인**: Spring Batch 3 Job으로 레이스 결과·피트스톱·챔피언십 순위 자동 수집 (실패 지점 추적 및 재시작)
- **AI 요약**: Claude Haiku로 RSS 뉴스 한국어 3문장 요약 + Elasticsearch 색인
- **테스트**: MySQL + Redis 실 컨테이너(Testcontainers) 기반 통합 테스트 19건

[📂 Repository](https://github.com/ansancitiboi/F1pitwall)

---

## 📬 Contact

- **Portfolio**: [Notion](https://marble-devourer-a02.notion.site/DolChat-Project-2e031fe5bfa680539bc9fc7606282e8e)
- **Email**: tw4380833@naver.com
