# 지나갔나요? (IsItGone) 

지나갔나요?는 삼성 청년 SW 아카데미 대전 캠퍼스 학생을 위한 셔틀 버스 정보 제공 서비스입니다.

교육생이 셔틀을 이용할 때 안내되는 정류장 위치와 실제 위치가 다르고, 셔틀 노선 변경에도 교육생이 잘 알지 못하는 불편함이 있습니다.

실제 정류장과 노선의 위치를 동적으로, 마치 지도 앱처럼 제공합니다.

---

## 🌐 사용해보기

### 🔗 [🖥️ https://isitgone.site](https://isitgone.site)

### 📱 모바일

[![Download on the Play Store](https://img.shields.io/badge/Google%20Play-Download-brightgreen?logo=google-play)](https://play.google.com/store/apps/details?id=com.example.app)
[![Download on the App Store](https://img.shields.io/badge/App%20Store-Download-blue?logo=apple)](https://apps.apple.com/app/id000000000)

<img src="./assets/qrcode-playstore.png" alt="Play Store QR" width="140"/>
<img src="./assets/qrcode-appstore.png" alt="App Store QR" width="140"/>

---

## **프로젝트 구조**

조직 내 전체적인 아키텍처 요약을 적습니다.
- (선택) 아키텍처 다이어그램 또는 마이크로서비스 간 데이터·통신 흐름이 있다면 이미지를 추가.

```
 ┌───────────┐      ┌─────────────┐
 │ Client(s) │ ---> │ Gateway/API │ ---> … 
 └───────────┘      └─────────────┘
         … 
```

---

## **주요 레포 소개**

- [client](https://github.com/IsItGone/client)
- [graphql](https://github.com/IsItGone/graphql)
- [route](https://github.com/IsItGone/route)
- [station](https://github.com/IsItGone/station)
- [cluster-config](https://github.com/IsItGone/cluster-config)
- [helm-base-chart](https://github.com/IsItGone/helm-base-chart)
- [ci-templates](https://github.com/IsItGone/ci-templates)


조직 내 레포와 간단한 기능 및 사용 목적을 정리합니다.

### 1) 마이크로서비스 레포
- **레포명**: `orders-service` 등
    - **설명**: 주문 관리 마이크로서비스
    - **주요 언어/프레임워크**: 예) Spring Boot, Node.js …
    - **기능/역할**: 주문 처리, 결제 연동 …

- **레포명**: `users-service` 등
    - **설명**: 사용자 관리 마이크로서비스
    - **주요 언어/프레임워크**: …
    - **기능/역할**: 로그인/회원가입, 유저 권한 관리 …

> 마이크로서비스가 많다면 이런 식으로 간략히 반복해서 나열합니다.

### 2) Chart 레포
- **레포명**: `helm-charts` 등
    - **설명**: Helm 차트 관리
    - **기능/역할**: 각 마이크로서비스를 Kubernetes에 배포하기 위한 Helm 차트 제공
    - **배포 방식**: Helm CLI 사용 또는 CICD 연동

### 3) GitOps 레포
- **레포명**: `gitops-config` 등
    - **설명**: GitOps(Argo CD 혹은 Flux) 설정 관리
    - **기능/역할**: 특정 브랜치/태그를 모니터링해 자동으로 Kubernetes 클러스터에 적용
    - **운영 프로세스**: PR 병합 → GitOps 레포 동기화 → 자동 배포

### 4) 클라이언트 레포
- **레포명**: `frontend` (React/Angular/Vue 등)
    - **설명**: 웹 프론트엔드 레포
    - **기능/역할**: 사용자 UI, API 호출 로직, 빌드·배포 스크립트 등

주요 레포 소개
조직 내 레포와 간단한 기능 및 사용 목적을 정리합니다.

1) 마이크로서비스 레포
   레포명: orders-service 등

설명: 주문 관리 마이크로서비스

주요 언어/프레임워크: 예) Spring Boot, Node.js …

기능/역할: 주문 처리, 결제 연동 …

레포명: users-service 등

설명: 사용자 관리 마이크로서비스

주요 언어/프레임워크: …

기능/역할: 로그인/회원가입, 유저 권한 관리 …

마이크로서비스가 많다면 이런 식으로 간략히 반복해서 나열합니다.

2) Chart 레포
   레포명: helm-charts 등

설명: Helm 차트 관리

기능/역할: 각 마이크로서비스를 Kubernetes에 배포하기 위한 Helm 차트 제공

배포 방식: Helm CLI 사용 또는 CICD 연동

3) GitOps 레포
   레포명: gitops-config 등

설명: GitOps(Argo CD 혹은 Flux) 설정 관리

기능/역할: 특정 브랜치/태그를 모니터링해 자동으로 Kubernetes 클러스터에 적용

운영 프로세스: PR 병합 → GitOps 레포 동기화 → 자동 배포

4) 클라이언트 레포
   레포명: frontend (React/Angular/Vue 등)

설명: 웹 프론트엔드 레포

기능/역할: 사용자 UI, API 호출 로직, 빌드·배포 스크립트 등
---

## **배포 및 운영 개요**

- **CI/CD**:
    - 어떤 툴을 사용해서 빌드·테스트·배포하는지 (예: Jenkins, GitLab CI, GitHub Actions)
    - 파이프라인 개요 (개발 브랜치 → QA 환경 → 프로덕션 환경 식의 순서)
- **배포 흐름**:
    - 예: 코드 변경 → PR 승인 → 자동 빌드 → Helm 차트 또는 GitOps 레포 업데이트 → Kubernetes 클러스터에 자동 배포
- **모니터링/로그**:
    - 주요 모니터링 툴 (예: Prometheus, Grafana), 로그 수집 방식 (예: ELK stack)

배포 및 운영 개요
CI/CD:

어떤 툴을 사용해서 빌드·테스트·배포하는지 (예: Jenkins, GitLab CI, GitHub Actions)

파이프라인 개요 (개발 브랜치 → QA 환경 → 프로덕션 환경 식의 순서)

배포 흐름:

예: 코드 변경 → PR 승인 → 자동 빌드 → Helm 차트 또는 GitOps 레포 업데이트 → Kubernetes 클러스터에 자동 배포

모니터링/로그:

주요 모니터링 툴 (예: Prometheus, Grafana), 로그 수집 방식 (예: ELK stack)

---

## **기술 스택**

빠르게 파악할 수 있도록 주요 기술 스택을 표나 간단한 리스트로 정리합니다.

| 구분             | 기술/도구         | 비고                         |
|------------------|-------------------|------------------------------|
| 언어/프레임워크  | Java(Spring Boot) | 마이크로서비스 구현          |
| 인프라/컨테이너  | Docker, Kubernetes| 컨테이너 오케스트레이션 사용 |
| 배포/CI-CD       | Helm, Argo CD     | GitOps 기반 자동 배포        |
| DB/스토리지      | MySQL             | 관계형 DB, 사용자 등 관리    |
| 모니터링/로그    | Prometheus, Grafana | 시스템 모니터링 시각화     |

---

## **문의 및 참조 링크**

- **추가 문서**: 사내 Wiki, API 문서, Confluence 등 링크
- **문의 채널**: 슬랙 채널, 메일, 담당자 연락처
- **기타 레퍼런스**: 테스트 커버리지 리포트, 시스템 설계 문서, 보안 정책 등 내부 문서가 있다면 링크로 연결

---

> 위 템플릿은 “조직/서비스의 개요를 빠르게 파악하고, 주요 레포에 접근할 수 있도록 돕는” 목적에 맞춰 최소한의 정보만 담았습니다.  
> 내부 문서는 일반적으로 처음 읽는 사람이 이 프로젝트의 전반적인 구조를 쉽게 이해할 수 있도록 작성하면 됩니다. 세부 구현 내용이나 설정값 등은 각 레포의 개별 README나 사내 Wiki로 분산하여 관리하는 편이 효율적입니다.