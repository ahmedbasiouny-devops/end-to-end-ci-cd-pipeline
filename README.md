# VProfile Web Application Multi-Tier Stack

A multi-tier Java Spring web application setup including MySQL database, Memcached, RabbitMQ, Tomcat, and NGINX components. This repository contains the configurations required for containerized local development via **Docker Compose**, production orchestration on **Kubernetes**, and automated **CI/CD via Jenkins**.

---

## 🏗️ Architecture Overview

The system consists of the following interconnected services:

* **`vproweb`**: NGINX Web Server acting as a reverse proxy or entry point.
* **`vproapp`**: Spring MVC Java web application hosted on Apache Tomcat.
* **`vprodb`**: MySQL database backend storing persistent user data.
* **`vprocache01`**: Memcached cluster/instance for caching data.
* **`vpromq01`**: RabbitMQ message broker for async task handling.

---

## 📁 Repository Structure

```text
.
├── Docker-files/
│   ├── app/                 # Dockerfile and configs for Tomcat App
│   ├── db/                  # Dockerfile and init scripts for MySQL
│   └── web/                 # Dockerfile for NGINX
├── docker-compose.yml       # Local multi-container development environment
├── Jenkinsfile              # CI/CD pipeline definition
├── pom.xml                  # Maven dependencies & build configuration
└── k8s/                     # Kubernetes manifests
    ├── app-secret.yml
    ├── db-CIP.yml
    ├── mc-CIP.yml
    ├── mcdep.yml
    ├── rmq-CIP-service.yml
    ├── rmq-dep.yml
    ├── vproapp-service.yml
    ├── vproappdep.yml
    └── vprodbdep.yml

