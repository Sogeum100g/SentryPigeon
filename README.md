# 센트리피전 (Sentry Pigeon)
> 파편화된 공지·채용·지원사업·복지 정보를 한곳에 모아 관리하는 개인용 정보 운영 어시스턴트

![Platform](https://img.shields.io/badge/platform-Flutter%20%7C%20FastAPI-blue)
![Status](https://img.shields.io/badge/status-Portfolio%20Public%20Repo-success)
![Scope](https://img.shields.io/badge/scope-Architecture%20%26%20Structure-informational)

## 1. 프로젝트 개요

센트리피전은 사용자가 자주 확인해야 하는 여러 웹사이트의 공지사항, 채용 공고, 지원사업, 복지 정보 등을 **서버 측에서 주기적으로 추적하고**, 이를 **모바일 앱에서 구독·분류·알림** 형태로 관리할 수 있도록 설계한 서비스입니다.

기존의 웹 모니터링 도구는 다음과 같은 한계가 있었습니다.

- 사이트별로 직접 방문해야 하므로 정보 탐색 비용이 큼
- 일반 사용자가 설정하기 복잡함
- 모바일 환경에서 사용성이 낮거나 기기 리소스 소모가 큼
- 원문 모니터링은 가능하지만, 개인화된 정보 관리 경험은 부족함

센트리피전은 이를 해결하기 위해 다음 방향으로 설계되었습니다.

- **서버 기반 통합 모니터링**
- **사이트 구독 및 공지 통합 조회**
- **즐겨찾기 폴더/키워드 기반 개인화**
- **하루 1회 알림 및 신규 정보 리마인드**
- **동적 웹사이트 대응을 위한 확장 가능한 수집 구조**

---

## 2. 핵심 문제 정의

여러 사이트에 분산된 정보는 사용자가 직접 방문해 확인하지 않으면 놓치기 쉽습니다.

예를 들어 다음과 같은 정보는 놓쳤을 때 실질적인 기회비용이 발생합니다.

- 대학 공지 및 장학금
- 대외활동 / 공모전 / 교육 프로그램
- 기업 채용 공고
- 지원사업 / 입찰 공고
- 법령 개정 / 정책 공지
- 복지관 / 지자체 공지

센트리피전은 이런 정보를 **“사용자가 먼저 찾으러 가지 않아도 되는 상태”**로 바꾸는 것을 목표로 했습니다.

---

## 3. 주요 기능

### 3-1. 사이트 구독
사용자가 특정 공지 페이지 URL을 등록하면, 서버가 해당 사이트를 추적 대상으로 관리합니다.

### 3-2. 공지 통합 조회
여러 사이트의 공지를 앱 내에서 통합 목록으로 확인할 수 있습니다.

### 3-3. 즐겨찾기 폴더 관리
사용자는 관심 주제별 폴더를 만들고, 공지를 별도 정리할 수 있습니다.

### 3-4. 폴더별 키워드 관리
폴더에 키워드를 등록하여 관심 정보만 분류·관리할 수 있도록 설계했습니다.

### 3-5. 신규 정보 알림
새로운 공지가 등록되었을 때, 사용자가 설정한 시간에 리마인드 형태로 알림을 받을 수 있습니다.

### 3-6. 사용자 문의 및 운영 응답
앱 내 문의 기능과 운영자 응답 흐름을 포함하여, 서비스 운영 구조도 함께 설계했습니다.

---

## 4. 대표 화면

> 실제 공개 레포에서는 `docs/images/` 아래에 스크린샷 또는 GIF를 배치하는 것을 권장합니다.

### 주요 화면 구성
- 즐겨찾기 화면
- 구독 화면
- 홈 화면
- 사이트 등록 화면
- 설정 화면
- 폴더 키워드 관리 화면
- 알림 설정 화면
- 사용처 추천 화면

```text
docs/
└── images/
    ├── screen-favorites.jpg
    ├── screen-subscriptions.jpg
    ├── screen-home.jpg
    ├── screen-add-site.jpg
    ├── screen-managing-keywords.jpg
    ├── screen-recommending-sites-1.jpg
    ├── screen-recommending-sites-2.jpg
    ├── screen-recommending-sites-3.jpg
    └── screen-notification.jpg

## 5. 기술 스택
### Frontend
- Flutter
- Provider
- Firebase Cloud Messaging
- Google Sign-In
- Local Notifications
- SharedPreferences / Secure Storage

### Backend
- FastAPI
- PostgreSQL
- Redis
- Celery
- Nginx
- httpx / requests / BeautifulSoup / Playwright

### Infra / Operations
- Docker / Docker Compose
- Firebase Admin SDK
- 관리자 응답 및 운영 알림 구조


## 6. 시스템 아키텍처

<img width="1725" height="971" alt="mermaid-diagram" src="https://github.com/user-attachments/assets/39d4445f-8a14-45ec-bf0d-97287bb59965" />


