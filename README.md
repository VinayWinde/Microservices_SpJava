# 🏗️ Microservices Architecture with Spring Boot

This project demonstrates a modular **Microservices Architecture** built with **Spring Boot**, showcasing service discovery, centralized config, API gateway, and resilience patterns.

---

## 🧱 Services Overview

| Service         | Description                                     | Port  |
|----------------|-------------------------------------------------|--------|
| `user-service` | Manages users and their associated ratings       | 8081   |
| `hotel-service`| Manages hotel info                              | 8082   |
| `rating-service`| Handles ratings given to hotels by users       | 8083   |
| `config-server`| Centralized externalized configuration          | 8085   |
| `api-gateway`  | Single entry point for routing + load balancing | 8084   |
|'servive-registry|Enables Eureka server                           | 8761   |

---

## 🔄 Inter-Service Communication

- `user-service` fetches hotel and rating data via:
  - 🔗 **RestTemplate** (manual HTTP calls)
  - 🤝 **FeignClient** (declarative REST client)

---

## 🛡️ Resilience Patterns (via Resilience4j)

Implemented in key communication paths:

- ✅ **Circuit Breaker** – Automatically stops calling failing services temporarily.
- 🔁 **Retry** – Automatically retries failed requests with backoff.
- ⏳ **Rate Limiter** – Controls request rate to avoid overloading services.
- 🧘 **Time Limiter** – Defines max timeout duration for calls.

---

## 🌐 API Gateway (Spring Cloud Gateway)

- Handles dynamic routing to microservices
- Provides centralized access control and monitoring
- Routes example:
  - `/users/**` → `user-service`
  - `/hotels/**` → `hotel-service`
  - `/ratings/**` → `rating-service`

---

## ⚙️ Configuration Server (Spring Cloud Config)

- Central place for storing external properties for all services
- Connected to a Git repo for dynamic config refresh

---

## 📦 Technologies Used

- Java 21, Spring Boot
- Spring Cloud (Gateway, Config, OpenFeign)
- Eureka (optional for service discovery)
- Maven
- Resilience4j

  -->STRUCTURE<--
├── api-gateway
├── config-server
├── user-service
├── hotel-service
├── rating-service
└── README.md

---

---

Let me know if you're using **Eureka** or need the **GitHub link section** added to the README. I can customize it further!
