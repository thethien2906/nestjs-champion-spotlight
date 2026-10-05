# PROJECT DOGMA-01 — NERV Personnel & Eva Registry API

**Status:** Planned  
**Architecture:** Secure modular NestJS REST API

## Mission

Build the administrative backbone for NERV Central Dogma. The API manages personnel, pilots, Evangelion units, and classified sortie records, with access limited by role and clearance.

## Learning objectives

- Organize a NestJS application into feature modules and providers.
- Build validated REST endpoints with DTOs and consistent error responses.
- Persist relational data and manage schema changes.
- Apply authentication, role checks, and resource clearance rules.
- Document and test an API contract.

## Domain outline

- **Pilot:** identity, blood type, assigned Eva, clearance, and synchronization history.
- **Eva unit:** designation, operational status, soul signature, and current synchronization rate.
- **Sortie record:** mission, Angel target, deployed Eva, pilot, duration, and outcome.

## Implementation checklist

- [ ] Set up `AuthModule`, `PersonnelModule`, `EvaModule`, and `SortieModule`.
- [ ] Define DTOs and validate inputs, including synchronization rates from `0` to `400` and supported blood types.
- [ ] Configure PostgreSQL with Prisma or TypeORM, migrations, and seed data.
- [ ] Add password hashing and JWT access/refresh tokens.
- [ ] Enforce role and clearance policies with guards and metadata decorators.
- [ ] Publish the API contract with Swagger at `/api/docs`.
- [ ] Add unit coverage for synchronization calculations and E2E coverage for forbidden access, including a pilot receiving `403 Forbidden` on commander-only routes.

## Completion criteria

- Personnel, Eva, and sortie data persist in the relational database.
- Requests are validated and authorization is enforced before protected data is returned.
- The documented API and automated checks cover its core security boundaries.

## Learning references

- [Roadmap](../../roadmap.md) — Project 1
- [Project dossier](../../projects.md) — PROJECT DOGMA-01
- [NestJS checklist](../../checklist.md) — Sections 1–11
