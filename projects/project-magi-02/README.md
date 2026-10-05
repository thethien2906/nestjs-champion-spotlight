# PROJECT MAGI-02 — Tactical Telemetry & Combat Room

**Status:** Planned  
**Architecture:** NestJS WebSocket gateway with Redis state and cache

## Mission

Stream live Eva and Tokyo-3 telemetry between cockpits, the command deck, and the three MAGI computers: Melchior-1, Balthasar-2, and Casper-3.

## Learning objectives

- Authenticate WebSocket connections and organize clients into rooms.
- Manage fast-changing shared state and cached feeds in Redis.
- Decouple application behavior with in-process events.
- Schedule recurring maintenance work.

## Operational behavior

- Broadcast pilot synchronization changes to the relevant room at the specified 500 ms cadence.
- Track the five-minute internal battery countdown after an umbilical cable is severed.
- Collect MAGI votes (`AGREE`, `DENY`, or `CONDITIONAL`) and publish the consensus result.
- Broadcast Tokyo-3 alert transitions from `NORMAL` through `CONDITION_YELLOW` to `EMERGENCY_STATE_RED`.

## Implementation checklist

- [ ] Create an authenticated `@WebSocketGateway()` using JWT handshake credentials.
- [ ] Partition socket traffic into Eva cockpit and command-deck rooms.
- [ ] Store high-frequency pilot vitals and Angel coordinates in Redis.
- [ ] Emit and handle domain events such as `EvaWentBerserkEvent` and `UmbilicalSeveredEvent`.
- [ ] Implement MAGI voting and alert-state transitions.
- [ ] Add scheduled sensor-health checks and stale-connection cleanup with `@nestjs/schedule`.
- [ ] Define cache keys, expiry, and invalidation behavior for telemetry feeds.

## Completion criteria

- Authenticated clients receive the telemetry and alerts for their rooms.
- Presence and short-lived tactical state survive across gateway operations through Redis.
- Consensus and state transitions are emitted as clear, testable events.

## Learning references

- [Roadmap](../../roadmap.md) — Project 2
- [Project dossier](../../projects.md) — PROJECT MAGI-02
- [NestJS checklist](../../checklist.md) — Sections 12–14
