# Medical B2B ERP System

A production-grade Medical Domain B2B ERP platform designed for hospitals, distributors, and medical vendors. This project follows a modern microservices architecture with containerized deployment using Docker and Docker Compose.

---

# Project Overview

The system is built with 3 independent Spring Boot microservices and a React frontend. Each microservice has its own dedicated MongoDB database following microservices best practices.

## Features

- User authentication & authorization
- Product and inventory management
- Order processing and billing workflow
- Role-based access control
- Containerized deployment
- Cloud-ready scalable architecture

---

# Architecture Overview

```text
                        React Frontend
                 (Vite + TailwindCSS)

                               │
                               │
                    Docker Compose Network
                               │

        ┌─────────────────────────────────────┐
        │                                     │
        │         Microservices Layer         │
        │                                     │
        └─────────────────────────────────────┘

       ┌───────────────────────────────────────────┐
       │                                           │
       │              user-service                 │
       │                 Port: 8081                │
       │         Authentication / JWT / RBAC       │
       │                                           │
       └───────────────────────────────────────────┘

       ┌───────────────────────────────────────────┐
       │                                           │
       │             product-service               │
       │                Port: 8082                 │
       │         Product & Inventory System        │
       │                                           │
       └───────────────────────────────────────────┘

       ┌───────────────────────────────────────────┐
       │                                           │
       │              order-service                │
       │                Port: 8083                 │
       │          Orders & Billing Workflow        │
       │                                           │
       └───────────────────────────────────────────┘

                               │
                               │

                     MongoDB Atlas Cluster

          users_db      products_db      orders_db
```

---

# Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18 + Vite + TailwindCSS |
| Backend | Spring Boot 3.x |
| Database | MongoDB Atlas |
| Authentication | JWT |
| Containers | Docker |
| Orchestration | Docker Compose |
| API Testing | Postman |
| Build Tool | Maven |
| Reverse Proxy | Nginx |

---

# Microservices

| Service | Port | Responsibilities |
|---|---|---|
| user-service | 8081 | Authentication, JWT, User Management |
| product-service | 8082 | Product Catalog, Inventory Management |
| order-service | 8083 | Orders, Billing, Order Tracking |

---

# Project Structure

```text
med-pharma-erp/
│
├── frontend/
│
├── user-service/
│   ├── src/main
│   ├── Dockerfile
│   └── pom.xml
│
├── product-service/
│   ├── src/main
│   ├── Dockerfile
│   └── pom.xml
│
├── order-service/
│   ├── src/main
│   ├── Dockerfile
│   └── pom.xml
│
├── docker-compose.yml
│
└── README.md
```

---

# Docker Deployment

## Build Containers

```bash
docker compose build
```

## Start All Services

```bash
docker compose up -d
```

## Stop Services

```bash
docker compose down
```

## View Running Containers

```bash
docker ps
```

---

# Environment Variables

Example:

```env
SPRING_DATA_MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/users_db
JWT_SECRET=your_secret_key
SERVER_PORT=8081
```

---

# MongoDB Databases

| Service | Database |
|---|---|
| user-service | users_db |
| product-service | products_db |
| order-service | orders_db |

---

# Frontend Build

```bash
npm install
npm run build
```

---

# Security

- JWT Authentication
- Role-Based Access Control (RBAC)
- Environment Variable Protection
- Secure MongoDB Atlas Connection
- Containerized Isolation

---

# Future Improvements

- Kubernetes Deployment
- Jenkins CI/CD Pipeline
- Terraform Infrastructure
- Monitoring & Logging
- API Gateway Integration

---

# Author

Rushi Dhole

GitHub: https://github.com/rushidholecom
