### Ryan Su
<img src="https://ryansu.uk/assets/img/pikachuR.png" width="50" align="right">

*Built **CoolLib** — a distributed library platform with native Android/iOS clients, containerized Spring Boot services, and real-time edge telemetry powered by Cloudflare Workers & D1.*

<p align="left">
  <a href="https://ryansu.uk/analytics/">
    <img src="https://img.shields.io/badge/Live_Infrastructure-Monitor-dc3545?style=for-the-badge&logo=chartmogul&logoColor=white"/>
  </a>
</p>

<p align="left">
  <a href="https://ryansu.uk/android-demo/">
    <img src="https://img.shields.io/badge/Android-UI_Demo-3DDC84?style=flat-square&logo=android&logoColor=white"/>
  </a>&nbsp;&nbsp;&nbsp;
  <a href="https://ryansu.uk/ios-demo/">
    <img src="https://img.shields.io/badge/iOS-UI_Demo-007AFF?style=flat-square&logo=apple&logoColor=white"/>
  </a>
</p>


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

### Live Edge Telemetry

<a href="https://ryansu.uk/analytics/">
  <img src="https://svg-status.ryansu.uk/" alt="Infrastructure Mini Monitor" width="520" />
</a>

### Infrastructure Highlights

- Edge analytics pipeline using Cloudflare Workers + D1
- Live telemetry ingestion from Spring Boot Actuator
- Containerized deployment with Docker and Nginx
- CDN-backed static delivery via Cloudflare R2
- Native Android/iOS clients sharing unified backend services

### Technical Stack


```text
Mobile          Kotlin • Jetpack Compose • SwiftUI
Backend         Spring Boot • PostgreSQL • JWT • REST APIs
Infrastructure  Docker • Nginx • GitHub Actions • CI/CD
Cloud Edge      Cloudflare Workers • D1 • R2 • CDN
Observability   Spring Actuator • Edge Telemetry Pipeline
```

