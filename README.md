### Ryan Su
<img src="https://ryansu.uk/assets/img/pikachuR.png" width="50" align="right">

*Software Engineer specializing in mobile, backend, and cloud platforms. Built CoolLib, a distributed system combining native Android/iOS applications, Spring Boot microservices, Cloudflare edge infrastructure, real-time telemetry, and automated CI/CD delivery.*

<p align="left">
  <a href="https://ryansu.uk/analytics/infrastructure"><img src="https://img.shields.io/badge/Infra-Monitor-dc3545?style=for-the-badge&logo=docker&logoColor=white"/></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://ryansu.uk/analytics/mobile"><img src="https://img.shields.io/badge/Mobile-Analytics-007aff?style=for-the-badge&logo=expo&logoColor=white"/></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://ryansu.uk/analytics/github/"><img src="https://img.shields.io/badge/GitHub-Analytics-6f42c1?style=for-the-badge&logo=github&logoColor=white"/></a><a href="https://ryansu.uk/analytics/infrastructure"><img src="https://img.shields.io/badge/Infra-Monitor-dc3545?style=for-the-badge&logo=docker&logoColor=white"/></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://ryansu.uk/analytics/mobile"><img src="https://img.shields.io/badge/Mobile-Analytics-007aff?style=for-the-badge&logo=expo&logoColor=white"/></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://ryansu.uk/analytics/github/"><img src="https://img.shields.io/badge/GitHub-Analytics-6f42c1?style=for-the-badge&logo=github&logoColor=white"/></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://ryansu.uk/analytics/incidents/"><img src="https://img.shields.io/badge/Live--Incidents-Clearance-DF5000?style=for-the-badge&logo=pagerduty&logoColor=white"/></a>
</p>

<p align="left">
  <a href="https://ryansu.uk/demo/android-demo/"><img src="https://img.shields.io/badge/Android-UI_Demo-3DDC84?style=flat-square&logo=android&logoColor=white"/></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://ryansu.uk/demo/ios-demo/"><img src="https://img.shields.io/badge/iOS-UI_Demo-007AFF?style=flat-square&logo=apple&logoColor=white"/></a>
</p>


---

### System Architecture

```mermaid
 flowchart LR

                subgraph Clients ["`**Mobile Clients**`"]
                A(Android\nCompose)
                B(iOS\nSwiftUI)
                end

                subgraph CF1 ["`**Cloudflare Edge (Delivery)**`"]
                G1{CDN\nCache}
                R2[(R2\nStorage)]
                C{Tunnel}
                end

                subgraph CF2 ["`**Cloudflare Observability**`"]
                W(Telemetry\nGateway)
                D1[(Metrics\nStore)]
                AL(Alert\nEngine)
                MON(Analytics\nDashboard)
                end

                subgraph Docker ["`**Docker Infrastructure**`"]
                E("`**<span style='font-size:2em;color:white;'>Spring<br>Boot</span>**`")
                H[(Postgre\nSQL)]
                end

                subgraph External ["`**External Services**`"]
                N1(Email\nPagerDuty)
                end

                %% =========================
                %% FLOW
                %% =========================

                Clients e1@--> G1

                G1 -- "Static Assets" --> R2
                G1 -- "API Requests" --> C

                C e3@--> E
                E --> H

                %% Observability
                E e4@--> W
                Clients e2@-. Telemetry .-> W

                W --> D1
                D1 --> MON
                
                %% Alert Engine reads data from D1
                D1 --> AL

                %% Corrected Alert Flow: Trigger outputs & Update Dashboard
                AL --> N1
                AL --> MON

                %% Edge animations
                e1@{ animate: true }
                e2@{ animate: true }
                e3@{ animate: true }
                e4@{ animate: true }


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
                %% OBSERVABILITY (unified blue system - AL deep indigo)
                %% =========================

                style W fill:#93c5fd,stroke:#3b82f6,stroke-width:2px,color:#fff
                style D1 fill:#bfdbfe,stroke:#60a5fa,stroke-width:1px,color:#fff
                style MON fill:#3b82f6,stroke:#2563eb,stroke-width:2px,color:#fff
                style AL fill:#1e40af,stroke:#1e3a8a,stroke-width:2px,color:#fff

                %% =========================
                %% BACKEND (unified gray system)
                %% =========================

                style E fill:#475569,stroke:#334155,stroke-width:2px,color:#fff
                style H fill:#334155,stroke:#334155,stroke-width:2px,color:#fff

                %% =========================
                %% EXTERNAL NOTIFICATIONS (Clean Light Blue / Translucent)
                %% =========================
                style N1 fill:#eff6ff,stroke:#60a5fa,stroke-width:1.5px,stroke-dasharray: 5 5,color:#1e40af

                style Clients fill:#f8fafc
                style CF1 fill:#f1f5f9
                style CF2 fill:#f8fafc
                style Docker fill:#f1f5f9
                style External fill:none,stroke:#cbd5e1,stroke-width:1px,stroke-dasharray: 3 3

                %% =========================
                %% LINKS
                %% =========================

                linkStyle default stroke:#94a3b8,stroke-width:1.5px
```

### EDGE PLATFORM TELEMETRY

<p align="left"><a href="https://ryansu.uk/analytics/"><img src="https://status.ryansu.uk/svg/system-telemetry.svg" alt="Infrastructure Mini Monitor" width="560" /></a></p>

### DEVELOPMENT METRICS
<p><a href="https://ryansu.uk/analytics/"><img src="https://status.ryansu.uk/svg/github-telemetry.svg" alt="GitHub Telemetry Monitor" width="560" /></a></p>


### Infrastructure Highlights

- Edge analytics pipeline using Cloudflare Workers + D1
- Live telemetry ingestion from Spring Boot Actuator
- Containerized deployment with Docker and Nginx
- CDN-backed static delivery via Cloudflare R2
- Native Android/iOS clients sharing unified backend services

### Technical Stack


```text
Mobile          Kotlin • Jetpack Compose • SwiftUI
Backend         Java • Spring Boot • PostgreSQL • REST APIs
Frontend        TypeScript • Astro
Cloud & Edge    Cloudflare Workers • D1 • R2 • CDN
Platform        Docker • Nginx • GitHub Actions • CI/CD
Observability   Telemetry Pipelines • Metrics • Logging
```

