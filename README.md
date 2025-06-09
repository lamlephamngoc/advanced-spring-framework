# Advanced Spring Framework Guide

Welcome to the **Advanced Spring Framework** repository — a curated reference and visual guide for mastering Spring's most powerful and enterprise-grade features.

This repo is ideal for:
- Senior Java developers
- Tech Leads
- Architects building enterprise Spring applications
- Engineers transitioning into microservices or cloud-native development

---

## What You'll Find Here

This repository is structured by **Spring modules** and includes:

- ✅ Hands-on **code examples** (Java 21, Spring Boot 3+)
- ✅ Visual **Mermaid diagrams** to explain architecture, flow, and lifecycles
- ✅ Explanations for **real-world use cases**, not just Hello World
- ✅ Design patterns and anti-patterns

---

## 📂 Project Structure

```
├── core/
│   ├── bean_lifecycle/
│   └── custom_post_processors/
│
├── aop/
│   ├── logging_aspect/
│   └── security_aspect/
│
├── transactions/
│   ├── propagation_isolation/
│   └── nested_transactions/
│
├── security/
│   ├── jwt_auth/
│   └── method_level_security/
│
├── events/
│   ├── sync_async_events/
│   └── domain_events/
│
├── data/
│   ├── spring_data_jpa/
│   └── querydsl_specifications/
│
├── cloud/
│   ├── service_discovery/
│   └── config_server/
│
├── reactive/
│   ├── webflux_intro/
│   └── r2dbc/
│
├── docs/
│   ├── mermaid/
│   │   ├── spring_security_flow.md
│   │   └── transaction_lifecycle.md

```

---

## 🧠 Key Concepts Covered

| Topic                  | Highlights |
|------------------------|------------|
| **Spring Core**        | Bean lifecycle, scopes, post processors |
| **Spring AOP**         | Custom aspects, join points, `@Around` logic |
| **Transaction Mgmt**   | Propagation, isolation, rollback strategy |
| **Spring Security**    | JWT authentication, filters, RBAC |
| **Event System**       | Decoupled communication with sync/async events |
| **Spring Data**        | Repositories, projections, specifications |
| **Spring Cloud**       | Config Server, Eureka, Resilience4j |
| **WebFlux**            | Reactive streams with Mono/Flux |
| **Mermaid Docs**       | Visual flowcharts and architecture graphs |

---

## 🔁 Example: Spring Security with JWT

```mermaid
graph TD
    subgraph Client
        A[User Login Request] --> B[POST /auth/login]
    end

    subgraph Backend API
        B --> C[AuthenticationFilter]
        C --> D[AuthenticationManager]
        D --> E[UserDetailsService + JWTProvider]
        E --> F[JWT Token Response]
    end

    F --> A
