# 🚀 Config Repo
![Git|70](https://img.shields.io/badge/Git-2.43.0-blue)  
## 📌 Overview

This repository serves as the **centralized configuration store** for all microservices in the system, used in conjunction with a Spring Cloud Config Server.

Instead of embedding configuration files inside each microservice, all environment-specific settings (such as `application.yml`, `application-dev.yml`, `application-prod.yml`) are stored here and managed in a single place.

The Config Server pulls these configurations from this repository at runtime and distributes them to the respective microservices.
## 🏗️ Role in the Whole System

### Externalized and centralized configurations store 

```text
1. Microservice (A) starts.

2. During startup, it connects to the Config Server.

3. The microservice requests its external configuration using its application name and active profile.

4. The Config Server retrieves the corresponding configuration file from the Config Repository.

5. The Config Server returns the configuration properties to the microservice.

6. The microservice loads the received configuration and completes its startup process.
```

![Service registration](docs/ConfigServerRole.svg)
## ✨ Features

✅ Externalized and centralized configuration store

✅ Support multiple environments (dev, test, prod)

✅ Support configuration versioning

✅ Easy configuration updates

## 🛠️ Tech Stack

| Technology | Purpose               |
| ---------- | --------------------- |
| Git        | Configuration storage |


## 📂 Project Structure

```text
config-repo/
│
├── common/
│   ├── application.yml
│   ├── application-dev.yml
│   ├── application-test.yml
│   └── application-prod.yml
│
├── service-registry/
│   ├── service-registry.yml
│   ├── service-registry-dev.yml
│   ├── service-registry-test.yml
│   └── service-registry-prod.yml
│
├── x-service/
│   ├── x-service.yml
│   ├── x-service-dev.yml
│   ├── x-service-test.yml
│   └── x-service-prod.yml
│
└── README.md
```
