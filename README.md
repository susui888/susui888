### Ryan Su 
<img src="https://ryansu.uk/assets/img/pikachuR.png" width="50" align="right">

- **Education:** *&nbsp;&nbsp;&nbsp;&nbsp;Mathematics & Computer Science (JMC) @ Imperial College London*
- **The Stack:** *&nbsp;&nbsp;&nbsp;&nbsp;Built **CoolLib** — a native cross-platform library management system. Engineered a containerized Kotlin & Spring Boot REST API backend alongside dual native mobile clients via Jetpack Compose and SwiftUI. Integrated a live telemetry and edge analytics pipeline using Cloudflare Workers & D1.*

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
[![Live Analytics](https://img.shields.io/badge/Live_Analytics-Monitor-dc3545?style=flat&logo=chartmogul&logoColor=white)](https://ryansu.uk/analytics/)&nbsp;&nbsp;&nbsp;&nbsp;
[![Android Client](https://img.shields.io/badge/Android-Showcase-3DDC84?style=flat&logo=android&logoColor=white)](https://ryansu.uk/android-demo/)&nbsp;&nbsp;&nbsp;&nbsp;
[![iOS Client](https://img.shields.io/badge/iOS-Showcase-007AFF?style=flat&logo=apple&logoColor=white)](https://ryansu.uk/ios-demo/)&nbsp;&nbsp;&nbsp;&nbsp;

---

### System Architecture

```mermaid
flowchart LR

                subgraph Clients ["<span style='color:#000'><b>Clients</b></span>"]
                A(Android
                Compose)
                B(iOS
                SwiftUI)
                end


                subgraph CF1 ["<span style='color:#000'><b>Cloudflare Edge (Delivery)</b></span>"]
                G1{CDN
                Cache}
                R2[(R2
                Storage)]
                C{Tunnel}
                end


                subgraph CF2 ["<span style='color:#000'><b>Cloudflare Observability</b></span>"]
                W(Worker
                Monitor)
                D1[(D1
                Metrics)]
                MON(Monitor
                Dashboard)
                end


                subgraph Docker ["<span style='color:#000'><b>Docker Infrastructure</b></span>"]
                D(Nginx
                Proxy)
                E(Spring
                Boot)
                H[(Postgre
                SQL)]
                end


                %% =========================
                %% FLOW
                %% =========================

                A e1@--> G1
                B e2@--> G1

                G1 -- "Static Assets" --> R2
                G1 -- "API Requests" --> C

                C e3@--> D
                D --> E
                E --> H

                %% Observability (clean separation)
                E e4@--> W
                W --> D1
                D1 --> MON
                W --> MON


                %% =========================
                %% animations
                %% =========================

                e1@{ animation: slow }
                e2@{ animation: slow }
                e3@{ animation: slow }
                e4@{ animation: slow }


                %% =========================
                %% CLIENT LAYER (brand light)
                %% =========================

                style A fill:#22c55e,stroke:#16a34a,stroke-width:2px,color:#fff
                style B fill:#0A84FF,stroke:#0066cc,stroke-width:2px,color:#fff


                %% =========================
                %% CLOUDFLARE LAYER (unified blue system)
                %% =========================

                style G1 fill:#3b82f6,stroke:#2563eb,stroke-width:2px,color:#fff
                style C fill:#3b82f6,stroke:#2563eb,stroke-width:2px,color:#fff
                style R2 fill:#60a5fa,stroke:#3b82f6,stroke-width:1px,color:#fff


                %% =========================
                %% OBSERVABILITY (light blue system)
                %% =========================

                style W fill:#93c5fd,stroke:#3b82f6,stroke-width:2px,color:#fff
                style D1 fill:#bfdbfe,stroke:#60a5fa,stroke-width:1px,color:#fff
                style MON fill:#3b82f6,stroke:#2563eb,stroke-width:2px,color:#fff

                %% =========================
                %% BACKEND (UNIFIED SYSTEM COLOR)
                %% Nginx + Spring + PostgreSQL = ONE SYSTEM
                %% =========================

                style D fill:#64748b,stroke:#334155,stroke-width:2px,color:#fff
                style E fill:#475569,stroke:#334155,stroke-width:2px,color:#fff
                style H fill:#334155,stroke:#334155,stroke-width:2px,color:#fff

                style Clients fill:#f8fafc
                style CF1 fill:#f1f5f9
                style CF2 fill:#f8fafc
                style Docker fill:#f1f5f9

                %% =========================
                %% LINKS
                %% =========================

                linkStyle default stroke:#94a3b8,stroke-width:1.5px
```
<a href="https://ryansu.uk/analytics/">
  <img src="https://svg-status.ryansu.uk/?v=20260523" alt="Infrastructure Mini Monitor" width="520" />
</a>

### Technical Stack

```text
Mobile:   Kotlin (Compose, Hilt, Room) • Swift (SwiftUI, Combine, SwiftData)
Backend:  Spring Boot • REST APIs • PostgreSQL • Actuator • JWT • Clean Architecture
Infra:    Docker • Nginx • CI/CD (GitHub Actions) • Containerized Deployment
Cloud:    Cloudflare Workers • D1 • R2 (S3 API) • Edge Computing • CDN • Zero Trust
```

<p>
  <!-- Ecosystem & Multiplatform -->
  <img src="https://img.shields.io/badge/Kotlin-2.2-purple"/>&nbsp;
  <img src="https://img.shields.io/badge/Jetpack_Compose-Android-3DDC84"/>&nbsp;
  <img src="https://img.shields.io/badge/SwiftUI-iOS-0D96F6"/>&nbsp;
  <img src="https://img.shields.io/badge/Spring_Boot-4.0-green"/>
</p>
<p>
  <!-- Infra & Edge Computing -->
  <img src="https://img.shields.io/badge/PostgreSQL-18-blue"/>&nbsp;
  <img src="https://img.shields.io/badge/Cloudflare-Workers--D1--R2-orange"/>&nbsp;
  <img src="https://img.shields.io/badge/Docker-Containerized-2496ED"/>
</p>
