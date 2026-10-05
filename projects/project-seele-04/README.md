# PROJECT SEELE-04 — Global Defense Grid & Tactical Microservices

**Status:** Planned  
**Architecture:** Event-driven NestJS microservices with RabbitMQ or gRPC

## Mission

Coordinate NERV bases through independently deployable services. Tokyo-3 operations must remain available when a remote base or the SEELE audit service is unavailable.

## Service topology

- **Gateway service:** public HTTP entry point for tactical commands.
- **Catapult and power-grid service:** manages launch silos, evacuation shafts, and power distribution.
- **SEELE compliance service:** audits mission outcomes against the scenario script.
- **Message transport:** RabbitMQ or gRPC between services; Docker Compose for local orchestration.

## Learning objectives

- Configure NestJS microservice transports and message patterns.
- Design reliable event publication across database and broker boundaries.
- Apply timeouts, retries, and circuit breakers to remote calls.
- Operate multiple services and dependencies as a containerized system.

## Implementation checklist

- [ ] Define service boundaries, message contracts, and transport configuration.
- [ ] Implement the gateway, catapult/power-grid, and compliance services.
- [ ] Add a transactional outbox for durable launch-command publication.
- [ ] Add a circuit breaker so compliance-service outages do not block Eva launches.
- [ ] Create multi-stage Dockerfiles and a Compose setup for services, broker, and databases.
- [ ] Add readiness and liveness endpoints with `@nestjs/terminus`.
- [ ] Handle message validation, retries, idempotency, and service shutdown.

## Completion criteria

- A tactical command can travel from the gateway to the responsible service through the broker.
- Launch commands remain durable during broker interruptions.
- Service health and partial outages are observable and handled without taking down unrelated operations.

## Learning references

- [Roadmap](../../roadmap.md) — Project 4
- [Project dossier](../../projects.md) — PROJECT SEELE-04
- [NestJS checklist](../../checklist.md) — Sections 13–15
