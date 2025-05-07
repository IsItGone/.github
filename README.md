
<h1 align="center">
  <a href="https://web.isitgone.site"><img src="/assets/isitgone.png" alt="Is It Gone?" width="192" style="margin-bottom: 10px"></a>
  <br>
  지나갔나요?
  <br>
</h1>

<h4 align="center">삼성 청년 SW 아카데미 대전 캠퍼스 교육생을 위한 셔틀 앱</h4>

---
### 🚀 서비스 바로가기

<table>
  <tr>
    <td align="center">
      <a href="https://web.isitgone.site">
        <img src="https://img.shields.io/badge/Web-Available-ad83d9?logo=google-chrome&logoColor=white" alt="Web" />
      </a>
      <br>
      <img src="/assets/qr-web.png" alt="Web QR" width="160" />
    </td>
    <td align="center">
      <a href="https://play.google.com/store/apps">
        <img src="https://img.shields.io/badge/Google%20Play-Coming_soon!-brightgreen?logo=google-play" alt="Google Play" />
      </a>
      <br>
      <img src="/assets/qr.png" alt="Play Store QR" width="160" />
    </td>
    <td align="center">
      <a href="https://apps.apple.com">
        <img src="https://img.shields.io/badge/App%20Store-Coming_soon!-blue?logo=apple" alt="App Store" />
      </a>
      <br>
      <img src="/assets/qr.png" alt="App Store QR" width="160" />
    </td>
  </tr>
</table>


### 🛠️ Built With

[![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://flutter.dev/) 
[![GraphQL](https://img.shields.io/badge/GraphQL-E10098?style=for-the-badge&logo=graphql&logoColor=white)](https://graphql.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)](https://spring.io/projects/spring-boot) 
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/) 
[![K3s](https://img.shields.io/badge/K3s-FF6600?style=for-the-badge&logo=k3s&logoColor=white)](https://k3s.io/) 
[![Helm](https://img.shields.io/badge/Helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)](https://helm.sh/) 
[![Argo CD](https://img.shields.io/badge/Argo--CD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white)](https://argo-cd.readthedocs.io/) 
[![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)](https://github.com/features/actions)


### ☁️ Simple Architecture

![img_1.png](/assets/architecture.png)


## ⭐ Repositories

### 1) Client
**[client](https://github.com/IsItGone/client)**: Flutter 기반 Android, iOS, Web 앱 코드베이스


### 2) Server
**[Graphql service (graphql)](https://github.com/IsItGone/graphql)**: 조회 성능 개선을 위한 읽기 모델

**[Route service (route)](https://github.com/IsItGone/route)**: 노선 관리 서비스

**[Station service (station)](https://github.com/IsItGone/station)**: 정류장 관리 서비스


### 3) CI/CD, GitOps
**[GitOps (cluster-config)](https://github.com/IsItGone/cluster-config)**: ArgoCD 동기화 대상 리소스 및 클러스터 상태 구성

**[helm-base-chart](https://github.com/IsItGone/helm-base-chart)**: 재사용 가능한 Helm 베이스 차트 저장소

**[ci-templates](https://github.com/IsItGone/ci-templates)**: 재사용 가능한 Composite actions 템플릿 모음
