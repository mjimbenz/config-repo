
# Banking Microservices Ecosystem (English Version)

This repository contains a complete banking microservices architecture using Spring Cloud, Kafka, MongoDB, Eureka Server, Config Server, API Gateway, and Docker Compose.

---
## 📌 Repository Structure (Based on docker-compose.yml)
Each microservice and infrastructure component is defined according to the structure of the `docker-compose.yml` file.

---
## ✅ Clone Instructions
Before running the project, you **must clone the Docker branch** from each repository:

```bash
git clone -b docker <REPOSITORY_URL>
```
Replace `<REPOSITORY_URL>` with the actual URL of each microservice.


### ✅ Infrastructure Services
| Service | Description | Repository |
|--------|-------------|------------|
| **zookeeper** | Required for Kafka coordination | *Internal Docker Image* |
| **kafka** | Message broker for event processing | *Internal Docker Image* |
| **schema-registry** | Stores Avro schemas | *Internal Docker Image* |
| **kafdrop** | Kafka UI for topic inspection | *Internal Docker Image* |
| **mongo** | Database for microservices | *Internal Docker Image* |

---
## ✅ Spring Cloud Core Services
| Service              | Folder (Compose)     | Description                                | Repository |
|----------------------|----------------------|--------------------------------------------|------------|
| **config-repo**      | `./config-repo`      | Centralized configuration archive and docs | https://github.com/mjimbenz/config-repo|
| **config-server**    | `./config-server`    | Centralized configuration service          | https://github.com/mjimbenz/config-server|
| **registry-service** | `./registry-service` | Eureka Service Discovery                   | https://github.com/mjimbenz/registry-service |
| **gateway-service**  | `./gateway-service`  | API Gateway routing all traffic            | https://github.com/mjimbenz/api-gateway |

---
## ✅ Business Microservices
| Service | Folder (Compose) | Description | Repository |
|--------|------------------|-------------|------------|
| **customer-service** | `./customer-service` | Manages customer data | https://github.com/mjimbenz/customer-service |
| **passive-product-service** | `./passive-product-service` | Savings, current accounts, fixed term | https://github.com/mjimbenz/passive-product-service |
| **active-product-service** | `./active-product-service` | Credits, loans, credit cards | https://github.com/mjimbenz/active-product-service |
| **movement-service** | `./movement-service` | Records all customer product movements | https://github.com/mjimbenz/movement-service |

## 📁 Folder Structure Required for Docker Compose
```
/project-root
│── docker-compose.yml
│
│── config-server/
│   ├── Dockerfile
│   └── src/...
│
│── registry-service/
│   ├── Dockerfile
│   └── src/...
│
│── gateway-service/
│   ├── Dockerfile
│   └── src/...
│
│── customer-service/
│   ├── Dockerfile
│   └── src/...
│
│── passive-product-service/
│   ├── Dockerfile
│   └── src/...
│
│── active-product-service/
│   ├── Dockerfile
│   └── src/...
│
│── movement-service/
│   ├── Dockerfile
│   └── src/...
│
│── config-repo/
│   ├── customer-service.yml
│   ├── passive-product-service.yml
│   ├── active-product-service.yml
│   ├── movement-service.yml
│   ├── gateway-service.yml
│   ├── registry-service.yml
│   ├── application.yml
│   └── config-server.yml
│
└── README.md
```


---
# 🚀 Running the Project
To start the full system:
```bash
docker compose up -d
```

---
## 🌐 Access Points

👉 Banking [Microservices](docs/Collection.json) Collection


---
# 🛑 Stopping the System
```bash
docker compose down
```
To remove volumes:
```bash
docker compose down -v
```

---
# 📝 Notes
- All services load configuration from **Config Server**.
- All services register automatically in **Eureka Server**.
- `movement-service` records every transaction for any customer product.
- Kafka is available for event-driven expansion.

---
# 👨‍💻 Author
Miguel A. J. B.
Architecture • Microservices • Spring Cloud • Kafka • Docker
