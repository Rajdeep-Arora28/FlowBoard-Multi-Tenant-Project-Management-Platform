# FlowBoard — Multi-Tenant Project Management Platform

FlowBoard is a full-stack SaaS project management platform designed to help teams organize projects, manage tasks, collaborate in real time, and manage organization-level access through a centralized workspace.

The platform combines a modern Next.js frontend with a NestJS backend, PostgreSQL persistence, Redis caching, background job processing, and real-time communication.

## Key Features

- **Multi-Tenant Architecture:** Organization-scoped workspaces and data access.
- **Authentication & Authorization:** JWT-based authentication, refresh tokens, and role-based access control (RBAC).
- **Project Management:** Create and organize projects within workspaces.
- **Kanban Task Management:** Manage task workflows using a visual board with drag-and-drop interactions.
- **Real-Time Notifications:** Socket.IO integration for live updates.
- **Team Collaboration:** Organization members, invitations, and role management.
- **Background Processing:** Redis and BullMQ for asynchronous job processing.
- **Email Workflows:** SMTP-based email functionality using Nodemailer.
- **Subscription Billing:** Stripe integration architecture.
- **Caching & Performance:** Redis-backed caching and cache invalidation.
- **Auditability:** Activity tracking and structured application logging.
- **Developer Workflow:** Docker support and GitHub Actions CI workflows.

## Technology Stack

| Layer | Technologies |
|---|---|
| Frontend | Next.js 15, React 19, TypeScript |
| Styling | Tailwind CSS 4 |
| State Management | Zustand, TanStack React Query |
| Drag and Drop | dnd-kit |
| Backend | NestJS 11, TypeScript |
| Database | PostgreSQL, TypeORM |
| Caching | Redis, ioredis |
| Background Jobs | BullMQ |
| Real-Time Communication | Socket.IO |
| Authentication | JWT, Passport, argon2 |
| Email | Nodemailer, SMTP |
| Payments | Stripe SDK |
| Logging | Pino |
| Infrastructure | Docker, GitHub Actions |

## Architecture

```text
                 ┌─────────────────────────┐
                 │   Next.js Frontend      │
                 │   React + TypeScript    │
                 └────────────┬────────────┘
                              │
                    REST API / Socket.IO
                              │
                 ┌────────────▼────────────┐
                 │     NestJS Backend      │
                 │ Auth, RBAC, Projects,    │
                 │ Tasks, Organizations    │
                 └──────┬─────────┬────────┘
                        │         │
                ┌───────▼───┐ ┌───▼──────────┐
                │ PostgreSQL│ │    Redis     │
                │ Persistent│ │ Cache/Queues │
                │   Data    │ └──────┬───────┘
                └───────────┘        │
                              ┌──────▼───────┐
                              │ BullMQ Worker│
                              │ Background   │
                              │ Processing   │
                              └──────────────┘
```

## Project
