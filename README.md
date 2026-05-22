### Ryan Su 
<img src="https://ryansu.uk/assets/img/pikachuR.png" width="50" align="right">

- **Education:** Mathematics & Computer Science (JMC) @ Imperial College London
- **Core System:** Built **CoolLib** — an offline-first, native cross-platform library management system. Engineered a containerized Kotlin & Spring Boot REST API backend alongside dual native mobile clients via Jetpack Compose (Android) and SwiftUI (iOS 18 / Swift 6 concurrency). Integrated a live telemetry and edge analytics pipeline using Cloudflare Workers & D1.
- **Links:** [Portfolio Website](https://ryansu.uk) • [Live Monitor](https://ryansu.uk/analytics/) • [me@ryansu.uk](mailto:me@ryansu.uk)

---

### [System Architecture Topology](https://ryansu.uk/spring-architecture/)

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

### Core Production Repositories
- **[CoolLeaf](https://github.com/susui888/CoolLeaf)** (Backend): Layered Clean Architecture REST API using Kotlin/Spring Boot. Features atomicity pipelines for S3/R2 asset upload and Spring Boot Actuator for operational observability.
- **[coollib-android](https://github.com/susui888/coollib-android)**: Native Android app using Jetpack Compose, Hilt (DI), and Room DB for offline-first local persistence.
- **[coollib-ios](https://github.com/susui888/coollib-ios)**: Native iOS 18 client built with Swift 6 strict concurrency checks, SwiftUI, SwiftData, and the Observation framework.
