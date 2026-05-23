### Ryan Su 
<img src="https://ryansu.uk/assets/img/pikachuR.png" width="50" align="right">

- **Education:** Mathematics & Computer Science (JMC) @ Imperial College London
- **Core System:** Built **CoolLib** — an offline-first, native cross-platform library management system. Engineered a containerized Kotlin & Spring Boot REST API backend alongside dual native mobile clients via Jetpack Compose (Android) and SwiftUI (iOS 18 / Swift 6 concurrency). Integrated a live telemetry and edge analytics pipeline using Cloudflare Workers & D1.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
[![Live Analytics](https://img.shields.io/badge/Live_Analytics-Monitor-dc3545?style=flat&logo=chartmogul&logoColor=white)](https://ryansu.uk/analytics/)&nbsp;&nbsp;&nbsp;&nbsp;
[![Android Client](https://img.shields.io/badge/Android-Showcase-3DDC84?style=flat&logo=android&logoColor=white)](https://ryansu.uk/android-demo/)&nbsp;&nbsp;&nbsp;&nbsp;
[![iOS Client](https://img.shields.io/badge/iOS-Showcase-007AFF?style=flat&logo=apple&logoColor=white)](https://ryansu.uk/ios-demo/)&nbsp;&nbsp;&nbsp;&nbsp;
[![System Architecture](https://img.shields.io/badge/Architecture-Ecosystem_Topology-198754?style=flat&logo=diagrams.net&logoColor=white)](https://ryansu.uk/spring-architecture/)

---

### System Architecture Topology

```text
            ┌─────────────────────────────────────────────────────────────────────────┐
            │                          Cloudflare Edge Layer                          │
            │     [ Workers + D1 Telemetry Ingestion ]     [ R2 Media Storage ]       │
            └────────────────────────────────────┬────────────────────────────────────┘
                                                 │ (Tunnels / Zero Trust)
                                                 ▼
                                    ┌─────────────────────────┐
                                    │       Nginx Proxy       │
                                    └────────────┬────────────┘
                                                 ▼
                                    ┌─────────────────────────┐
                                    │   Spring Boot Backend   │
                                    │   (Clean Architecture)  │
                                    └────────────┬────────────┘
                                                 ▼
                                    ┌─────────────────────────┐
                                    │    PostgreSQL Database  │
                                    └─────────────────────────┘
                                                 ▲
                                                 │ (Reactive Sync / REST)
            ┌────────────────────────────────────┴────────────────────────────────────┐
            │                             Native Clients                              │
            │       [ coollib-android (Compose) ]        [ coollib-ios (SwiftUI) ]    │
            └─────────────────────────────────────────────────────────────────────────┘
```

### Technical Stack

```text
Mobile:   Kotlin (Compose, Hilt, Room) • Swift (SwiftUI, Combine, SwiftData)
Backend:  Spring Boot • REST APIs • PostgreSQL • Actuator • JWT • Clean Architecture
Infra:    Docker • Nginx • CI/CD (GitHub Actions) • Containerized Deployment
Cloud:    Cloudflare Workers • D1 • R2 (S3 API) • Edge Computing • CDN • Zero Trust
```
