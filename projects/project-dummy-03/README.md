# PROJECT DUMMY-03 — Classified Ingestion & Pattern Analysis Pipeline

**Status:** Planned  
**Architecture:** NestJS upload API, BullMQ workers, Redis, and file streams

## Mission

Ingest large sortie recordings and biological scans without blocking HTTP requests. Queue analysis work, track its progress, and produce classified debrief reports.

## Learning objectives

- Validate and stream multipart uploads efficiently.
- Separate queue producers from background consumers.
- Handle retries, failed jobs, progress reporting, and graceful shutdown.
- Expose long-running job status through Server-Sent Events.

## Pipeline outline

1. Accept a flight-log or cockpit-media upload and return `202 Accepted` with a job ID.
2. Stream and parse the asset in a worker, identifying requested patterns such as Blue Blood signatures.
3. Generate a classified debrief PDF and extract key-frame snapshots where applicable.
4. Send job progress updates to clients over SSE.

## Implementation checklist

- [ ] Add multipart upload handling with file-size and MIME-type validation.
- [ ] Configure BullMQ producers and consumers backed by Redis.
- [ ] Implement streaming parsing and analysis for supported input formats.
- [ ] Report job IDs and progress, including an SSE progress endpoint.
- [ ] Configure exponential retry backoff and a dead-letter path for corrupted logs.
- [ ] Generate a debrief artifact from completed jobs.
- [ ] Drain or safely pause active jobs from `onApplicationShutdown`.

## Completion criteria

- Upload requests enqueue work and return promptly with a trackable job ID.
- Progress and failures are visible to clients, and retry behavior is bounded and observable.
- Shutdown does not leave active jobs or files in a corrupt state.

## Learning references

- [Roadmap](../../roadmap.md) — Project 3
- [Project dossier](../../projects.md) — PROJECT DUMMY-03
- [NestJS checklist](../../checklist.md) — Sections 4, 12, and 14
