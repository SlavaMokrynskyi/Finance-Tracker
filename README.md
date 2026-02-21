# Finance Tracker

Finance Tracker is a web application for managing personal finances: income, expenses, categories, budgets, and analytics by time period.

This project was built as a pet project to practice **backend development with Rust (Axum)** and **frontend development with React + TypeScript**.

## Features

- User registration / login
- JWT authentication
- Create and manage transactions (income / expense)
- Transaction categories
- Accounts (e.g. Cash, Card, Bank Account)
- Filters by date / category / type
- Category budgets
- Analytics:
  - total income/expenses by period
  - balance
  - expenses by category
  - daily/monthly trend
- Swagger / OpenAPI (optional)

---

## Tech Stack

### Backend
- **Rust**
- **Axum** (HTTP API)
- **Tokio** (async runtime)
- **SQLx** (PostgreSQL access)
- **PostgreSQL**
- **Serde** (JSON serialization)
- **jsonwebtoken** (JWT)
- **argon2** (password hashing)
- **tracing** / `tracing-subscriber` (logging)
- **validator** (DTO validation)
- **uuid**
- **chrono** (date/time)
- **rust_decimal** (precise money calculations)

### Frontend
- **React**
- **TypeScript**
- **React Router**
- **TanStack Query**
- **React Hook Form**
- **Zod**
- **Tailwind CSS** (or CSS Modules depending on your implementation)

---

## Architecture (Overview)

The project is split into 2 parts:

- `backend/` — REST API built with Rust + Axum
- `frontend/` — client application built with React + TypeScript

The frontend communicates with the backend via HTTP API (JSON).

---

## Project Structure (Example)

```txt
finance-tracker/
├─ backend/
│  ├─ src/
│  │  ├─ main.rs
│  │  ├─ app_state.rs
│  │  ├─ config/
│  │  │  └─ mod.rs
│  │  ├─ routes/
│  │  │  ├─ mod.rs
│  │  │  ├─ auth.rs
│  │  │  ├─ transactions.rs
│  │  │  ├─ categories.rs
│  │  │  ├─ accounts.rs
│  │  │  ├─ budgets.rs
│  │  │  └─ reports.rs
│  │  ├─ handlers/
│  │  ├─ services/
│  │  ├─ repositories/
│  │  ├─ models/
│  │  ├─ dto/
│  │  ├─ middleware/
│  │  ├─ auth/
│  │  ├─ errors/
│  │  └─ utils/
│  ├─ migrations/
│  ├─ .env.example
│  ├─ Cargo.toml
│  └─ Dockerfile
│
├─ frontend/
│  ├─ src/
│  │  ├─ app/
│  │  ├─ pages/
│  │  ├─ components/
│  │  ├─ features/
│  │  │  ├─ auth/
│  │  │  ├─ transactions/
│  │  │  ├─ categories/
│  │  │  ├─ budgets/
│  │  │  └─ reports/
│  │  ├─ lib/
│  │  ├─ hooks/
│  │  ├─ api/
│  │  ├─ types/
│  │  └─ main.tsx
│  ├─ .env.example
│  ├─ package.json
│  └─ Dockerfile
│
├─ docker-compose.yml
├─ .gitignore
└─ README.md