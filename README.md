# 👋 Lee Kanghyun · Backend Developer

> **"AI가 코드를 쓰는 시대, 저는 '왜 이렇게 설계했는가'를 설명할 수 있는 개발자입니다."**

LLM이 기능 구현을 대체하는 지금, 백엔드 개발자의 가치는 **신뢰성·보안·확장성을 책임지는 설계 능력**에 있다고 믿습니다.
저는 결제 멱등성, 서버 사이드 검증, AI 통합 시 책임 경계 설정 같은 **"틀어지면 안 되는 영역"** 을 직접 설계하고 구현해왔습니다.

---

## 🎯 Core Strengths

### 1. **돈과 직결되는 시스템을 다뤄봤습니다 (IAP, 광고 보상)**
- iOS / Android **인앱결제(IAP) 시스템 전체 재설계**
  - DB 유니크 제약 + 서비스 레벨 멱등성 이중 방어로 **중복 지급 0건**
  - Apple `appAccountToken` 바인딩으로 영수증 탈취·계정 주입 공격 차단
  - 인터페이스 기반 `StorePurchaseVerifier` 도입 → 신규 스토어 추가 시 **기존 코드 수정 0**
- AdMob **서버 사이드 검증(SSV) 보상 시스템** 구현
  - 클라이언트 신뢰 X, 서명 검증 + 세션 기반 + DB row lock으로 동시 요청까지 방어

### 2. **AI를 "도구"로 다룰 줄 압니다 **
연애 궁합 기능에서 OpenAI를 통합했지만, 점수 계산은 **서버가 직접 수행**했습니다.
- AI에 원본 프로필 전송 X → 가공된 score/grade만 전달 (개인정보 + 토큰 비용 최소화)
- **timeout / API 실패 시 fallback summary 반환** → AI가 죽어도 API는 살아있음
- 결과 일관성·재현성·비용 예측 가능성 모두 확보

> "AI 기능"이 아니라 **"AI를 안전하게 통합한 백엔드 기능"** 으로 설계.

### 3. **운영 가능한 시스템을 만듭니다 (CI/CD, Trace 로깅, 문서화)**
- **GitHub Actions + Docker** 자동 배포 파이프라인 구축
  - 수동 SSH 배포 → 자동 배포 / 배포 시간 **수 분 → 수 초**
  - 빌드 실패 시 배포 차단, Secret 기반 인증, 무중단에 가까운 재배포
- **traceId 기반 전구간 로깅** + 민감정보 마스킹 → 운영팀이 로그만 보고 장애 지점 즉시 파악
- API 8개 엔드포인트 상세 문서화 (`docs/iap-api.md`) → 프론트 연동 비용 절감

---

## 🏆 Awards & Achievements

### 🥇 2025 한국관광공사 관광데이터 활용 공모전 — **우수상 (사장상)**
**MoneyWay** · Backend Developer
- Spring Boot REST API 설계 / JPA 기반 DB 모델링 / 공공 API 연동 / Docker 환경 구성

### 🏅 2025 멋쟁이사자처럼 전국 해커톤 — **2차 진출**
**서산책** · Backend Developer
- MyBatis + PostgreSQL 데이터베이스 설계 및 서버 로직 구현

---

## 🚀 Featured Project: AirConnect (2025.11~)

**대학생 매칭 서비스 — iOS/Android 출시 운영 중**
> 단순 CRUD가 아닌, **결제·광고·인증·AI** 가 얽힌 실제 프로덕션 백엔드를 1인 개발

| 영역 | 무엇을 했는가 | 왜 중요한가 |
|---|---|---|
| **결제 (IAP)** | 트랜잭션 보장 + Apple JWS 사용자 바인딩 | 매출 손실·CS 폭증 방지 |
| **광고 보상 (SSV)** | 서명 검증 + 세션 기반 보상 지급 | 클라이언트 조작 차단 |
| **인증 플로우** | "인증/계정생성/로그인" 책임 분리, `purpose` 도입 | 앱 종료·재시도 등 현실 케이스 대응 |
| **AI 통합** | 점수는 서버, 요약만 OpenAI, fallback 필수 | 비용·일관성·안정성 동시 확보 |
| **CI/CD** | GitHub Actions + Docker 자동 배포 | 휴먼 에러 0, 배포 추적 가능 |

📝 시행착오와 의사결정 과정을 [기술 블로그](https://velog.io/@ka09068)에 정리했습니다.

---

## 🛠 Tech Stack

**Language**
![Java](https://img.shields.io/badge/Java-007396?style=flat&logo=Java&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=Python&logoColor=white)

**Backend & Data**
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat&logo=Spring%20Boot&logoColor=white)
![JPA](https://img.shields.io/badge/JPA-59666C?style=flat&logo=hibernate&logoColor=white)
![MyBatis](https://img.shields.io/badge/MyBatis-000000?style=flat&logo=mybatis&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=MySQL&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=PostgreSQL&logoColor=white)

**DevOps & Infra**
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=Docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
![AWS EC2](https://img.shields.io/badge/AWS%20EC2-FF9900?style=flat&logo=amazonec2&logoColor=white)

**Integration**
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat&logo=openai&logoColor=white)
![Apple](https://img.shields.io/badge/Apple%20IAP-000000?style=flat&logo=apple&logoColor=white)
![Google Play](https://img.shields.io/badge/Google%20Play%20Billing-414141?style=flat&logo=googleplay&logoColor=white)
![AdMob](https://img.shields.io/badge/AdMob%20SSV-EA4335?style=flat&logo=googleadmob&logoColor=white)

---

## 🧠 What I Focus On

- **신뢰 경계 설계** — 클라이언트는 믿지 않는다. 서버가 진실의 원천.
- **멱등성과 무결성** — DB 제약 + 로직 이중 방어로 "정확히 한 번"을 보장.
- **책임 분리** — Controller / Service / Domain, 그리고 AI와 비즈니스 로직의 경계.
- **운영 가능성** — traceId, 마스킹, 문서화. "장애가 났을 때 빠르게 파악할 수 있는가?"
- **확장 가능한 추상화** — 인터페이스로 스토어·인증 제공자 분리 → 새 요구사항이 와도 기존 코드 변경 최소화.
- **설계 의도를 글로 설명할 수 있는 코드** — 블로그에 모든 의사결정 기록.

---

## 📬 Contact

<p align="left">
<a href="https://velog.io/@ka09068/posts">
  <img src="https://img.shields.io/badge/Tech%20Blog-20C997?style=flat&logo=Velog&logoColor=white"/>
</a>
<a href="https://www.instagram.com/k_hyun__e" target="_blank">
  <img src="https://img.shields.io/badge/Instagram-E4405F?style=flat&logo=Instagram&logoColor=white"/>
</a>
</p>
