# E-Commerce Backend API

A backend e-commerce application built with Go, providing RESTful APIs and supporting infrastructure for managing an online shopping platform. The project demonstrates backend application architecture, database integration, API documentation, containerization, and asynchronous notification processing.

## Overview

This project is designed to provide the backend functionality required by an e-commerce platform. It uses Go and the Gin web framework to expose HTTP APIs, GORM for database operations, and PostgreSQL for persistent data storage.

The application also incorporates supporting infrastructure for local development, including Docker Compose, LocalStack, Mailpit, and a separate notification service.

## Technologies

| Technology | Purpose |
|---|---|
| Go | Backend programming language |
| Gin | HTTP web framework |
| GORM | Object-relational mapping |
| PostgreSQL | Relational database |
| Docker | Application containerization |
| Docker Compose | Multi-service development environment |
| Swagger / OpenAPI | API documentation |
| LocalStack | Local AWS-compatible service emulation |
| Amazon SQS-compatible messaging | Asynchronous message processing |
| Mailpit | Local email testing |
| Make | Development task automation |

## Key Features and Engineering Areas

- **RESTful API Development:** Backend HTTP endpoints implemented using Go and Gin.
- **Database Integration:** PostgreSQL integration using GORM.
- **Database Migrations:** Version-controlled database schema management.
- **API Documentation:** Swagger/OpenAPI documentation for exploring and testing API endpoints.
- **Containerization:** Docker-based application and infrastructure configuration.
- **Asynchronous Processing:** Integration with SQS-compatible messaging infrastructure.
- **Notification Service:** Separate notification service for processing application events.
- **Local Email Testing:** Mailpit integration for capturing and inspecting outgoing development emails.
- **Configuration Management:** Environment-based application configuration.

## Architecture

The project uses a structured Go application layout.

```text
ecommerce_shop/
├── cmd/
│   ├── api/
│   └── notifier/
├── internal/
├── db/
│   └── migrations/
├── docker/
│   └── docker-compose.yml
├── docs/
├── Makefile
├── go.mod
└── go.sum
```

### Architecture Components

- `cmd/api`: Main HTTP API application entry point.
- `cmd/notifier`: Notification service entry point.
- `internal`: Internal application components and business logic.
- `db/migrations`: Database migration files.
- `docker`: Docker Compose configuration and supporting infrastructure.
- `docs`: API documentation.
- `Makefile`: Common development and operational commands.

## Getting Started

### Prerequisites

- Go 1.25 or later, according to the project's Go module requirement.
- PostgreSQL.
- Docker and Docker Compose.
- Git.
- Make (if using the provided Makefile).

### Clone the Repository

```bash
git clone https://github.com/revernelly/ecommerce_shop.git
cd ecommerce_shop
```

### Configure Environment Variables

Create a `.env` file in the project root and configure the required application settings.

Use the project's environment configuration as the source of truth for the exact variable names and required values.

Do not commit credentials, database passwords, JWT secrets or other sensitive configuration to version control.

### Start Supporting Services

```bash
docker compose -f docker/docker-compose.yml up -d
```

### Run Database Migrations

```bash
make migrate-up
```

### Run the API

```bash
go run ./cmd/api
```

### Run the Notification Service

```bash
go run ./cmd/notifier
```

## API Documentation

The project includes Swagger/OpenAPI documentation.

Once the API is running, consult the configured Swagger UI route to explore the available endpoints, request parameters and response structures.

## Development Commands

The project Makefile provides development automation.

Common commands include:

```bash
make build
make run
make lint
make format
make migrate-up
make migrate-down
make docker-up
make docker-down
```

Run `make help` if the project defines a help target, or inspect the Makefile for the complete list of available commands.

## Project Goals

This project serves as practical experience in:

- Building backend applications with Go.
- Designing and organizing REST APIs.
- Integrating relational databases.
- Managing database schema migrations.
- Implementing service separation.
- Working with asynchronous messaging.
- Containerizing backend applications.
- Managing local development infrastructure.

## Author

**Carl Anyanwu**

GitHub: https://github.com/revernelly
