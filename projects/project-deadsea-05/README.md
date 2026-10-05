# PROJECT DEADSEA-05 — Dead Sea Scrolls Lore Knowledge Graph

**Status:** Planned  
**Architecture:** Code-first NestJS GraphQL gateway

## Mission

Provide researchers with a flexible API over Angels, historical events, Eva units, pilots, organizations, and classified lore. Clients can query related records without making a chain of REST requests.

## Learning objectives

- Define a GraphQL schema using NestJS and TypeScript decorators.
- Implement resolvers, inputs, queries, mutations, and custom scalars.
- Use DataLoader to batch nested data access and prevent N+1 queries.
- Apply authorization to GraphQL operations and fields.
- Publish real-time research updates through subscriptions.

## Knowledge graph outline

An Angel is connected to its first encounter and location, the Eva unit that defeated it, that unit's pilot, the pilot's profile, and the responsible organization.

## Implementation checklist

- [ ] Configure `@nestjs/graphql` in code-first mode with Apollo Server.
- [ ] Define object types, inputs, enums, queries, mutations, and `DateTime`/`JSON` scalars.
- [ ] Implement resolvers for the lore and entity relationships.
- [ ] Add DataLoader batching for nested Angel → Eva → Pilot lookups.
- [ ] Protect mutations and restricted lore with authentication and clearance-aware guards.
- [ ] Add subscriptions for newly published classified lore and research papers.
- [ ] Set query complexity or depth controls appropriate to the graph.

## Completion criteria

- A client can query nested lore and entity relationships in one GraphQL operation.
- Related records are batched rather than fetched with an N+1 query pattern.
- Restricted fields and publishing events follow the defined clearance policy.

## Learning references

- [Roadmap](../../roadmap.md) — Project 5
- [Project dossier](../../projects.md) — PROJECT DEADSEA-05
- [NestJS checklist](../../checklist.md) — Sections 5 and 13
