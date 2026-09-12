# 🏍️ MotoGP Championship API (`motogp-netcore-api`)

> Domain-driven RESTful Web API built with **ASP.NET Core**, **Entity Framework Core (InMemory)**, comprehensive **Moq unit testing**, and Docker support. Developed as a technical assessment for MotoGP.

---

## 🏛️ Architecture & Highlights

- **Entity Framework Core InMemory Provider** — Enables zero-setup, reproducible execution and lightning-fast automated test runs without requiring external database instances.
- **Service & Repository Layering** — Decoupled architecture where business domain logic resides in dedicated service classes, cleanly isolated from HTTP transport controllers.
- **Unit Testing with Moq** — Dedicated test suite in `MotoGp.Api.Application.Tests` validating business rules, null guards, and repository interaction contracts using **xUnit** and **Moq**.
- **Docker Support** — Containerized runtime with Dockerfile for immediate cross-platform execution.

---

## 📡 API Endpoints

Base route: `/api/motogp`

| Method | Route | Description |
| :--- | :--- | :--- |
| `GET` | `/api/motogp` | Retrieve list of riders, teams, and tournament entries |
| `GET` | `/api/motogp/{id}` | Retrieve specific rider profile by identifier |
| `POST` | `/api/motogp` | Register a new rider or championship participant |
| `PUT` | `/api/motogp/{id}` | Update rider stats, points, or team assignments |
| `DELETE` | `/api/motogp/{id}` | Remove a rider from tournament records |

---

## 🛠️ Tech Stack

- **Framework**: ASP.NET Core Web API
- **Language**: C#
- **ORM / Persistence**: Entity Framework Core (InMemory Provider)
- **Unit Testing**: xUnit, Moq
- **Containerization**: Docker

---

## 🚀 Running & Testing Locally

### Prerequisites
- [.NET SDK](https://dotnet.microsoft.com/download)

### Run Automated Tests

```bash
# Execute test suite with detailed test logger
dotnet test MotoGp.Api.Application.Tests
```

### Run the Web API

```bash
# Restore dependencies and start API
dotnet restore
dotnet run --project MotoGpWebApi
```

The API will bind to `http://localhost:5000` (or `https://localhost:5001`).

### Run via Docker

```bash
docker build -t motogp-api -f MotoGpWebApi/Dockerfile .
docker run -p 5000:80 motogp-api
```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
