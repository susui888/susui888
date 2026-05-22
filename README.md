### Ryan Su 
<img src="https://ryansu.uk/assets/img/pikachuR.png" width="50" align="right">

- **Education:** Mathematics & Computer Science (JMC) @ Imperial College London
- **Core System:** Built **CoolLib** — an offline-first, native cross-platform library management system. Engineered a containerized Kotlin & Spring Boot REST API backend alongside dual native mobile clients via Jetpack Compose (Android) and SwiftUI (iOS 18 / Swift 6 concurrency). Integrated a live telemetry and edge analytics pipeline using Cloudflare Workers & D1.
- **Links:** [Portfolio Website](https://ryansu.uk) • [me@ryansu.uk](mailto:me@ryansu.uk)

---

```text
[Architecture Topology]
Mobile Clients (iOS/Android) ───► Cloudflare WAF/Tunnels ───► Nginx ───► Spring Boot Backend ───► PostgreSQL
                                         │
                                         └───► Workers + D1 (Edge Real-time Analytics)
```

### Technical Stack

```text
Backend & Infra :: Kotlin • Java • Spring Boot • PostgreSQL • Docker • Nginx • GitHub Actions
Edge & Cloud    :: Cloudflare Workers • D1 (Edge SQL) • R2 (S3 API Object Storage) • Zero Trust
Mobile Apps     :: iOS (Swift 6, SwiftUI, SwiftData, Observation) • Android (Kotlin, Compose, Room, Hilt)
Other           :: Haskell • C  • Real Analysis • Group Theory
```

### Core Production Repositories
- **[CoolLeaf](https://github.com/susui888/CoolLeaf)** (Backend): Layered Clean Architecture REST API using Kotlin/Spring Boot. Features atomicity pipelines for S3/R2 asset upload and Spring Boot Actuator for operational observability.
- **[coollib-android](https://github.com/susui888/coollib-android)**: Native Android app using Jetpack Compose, Hilt (DI), and Room DB for offline-first local persistence.
- **[coollib-ios](https://github.com/susui888/coollib-ios)**: Native iOS 18 client built with Swift 6 strict concurrency checks, SwiftUI, SwiftData, and the Observation framework.
