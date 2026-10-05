# NestJS Learning Checklist

Work through the sections in order. The first sections cover what you need to build a conventional API; the later sections cover advanced patterns and other Nest application types. You do not need to learn every transport or database integration for every project.

For examples and version-specific details, use the [official NestJS documentation](https://docs.nestjs.com/). Its [first steps](https://docs.nestjs.com/first-steps), [overview](https://docs.nestjs.com/controllers), [fundamentals](https://docs.nestjs.com/fundamentals/custom-providers), [techniques](https://docs.nestjs.com/techniques), [security](https://docs.nestjs.com/security/authentication), [testing](https://docs.nestjs.com/fundamentals/testing), and [FAQ](https://docs.nestjs.com/faq/request-lifecycle) sections are good references.

## 1. Prerequisites

- [ ] JavaScript fundamentals: modules, classes, promises, `async`/`await`, exceptions, and array/object operations
- [ ] TypeScript: types, interfaces, unions, generics, enums, access modifiers, decorators, and compiler options
- [ ] Node.js: npm or another package manager, environment variables, modules, event loop, and process lifecycle
- [ ] HTTP basics: methods, status codes, headers, cookies, JSON, REST, and request/response lifecycle
- [ ] Git, command line, package scripts, and reading compiler/runtime errors

## 2. NestJS foundations

- [ ] What NestJS is and how it uses TypeScript, decorators, and metadata
- [ ] Project structure and the role of `main.ts`, the root module, feature modules, controllers, and providers
- [ ] Creating, running, building, and generating code with the Nest CLI
- [ ] Bootstrapping an app with `NestFactory` and configuring the application
- [ ] Decorators and metadata: how `@Module`, `@Controller`, `@Injectable`, and route decorators describe the app
- [ ] The application/module dependency graph and how Nest discovers components
- [ ] The difference between framework conventions and plain Node.js/HTTP adapter behavior

## 3. Modules and dependency injection

- [ ] Modules: `imports`, `controllers`, `providers`, and `exports`
- [ ] Feature modules, shared modules, and root modules; choosing clear module boundaries
- [ ] Provider registration and constructor injection
- [ ] Provider tokens and custom providers: `useValue`, `useClass`, `useFactory`, and `useExisting`
- [ ] Injecting by token with `@Inject()` and using symbols or strings as tokens
- [ ] Asynchronous provider factories and provider initialization order
- [ ] Global modules and why explicit imports/exports are usually easier to follow
- [ ] Dynamic modules and `register()` / `forRoot()` / `forFeature()` patterns
- [ ] Provider scopes: singleton/default, request-scoped, and transient; performance and lifecycle trade-offs
- [ ] Circular dependencies, `forwardRef()`, and how to redesign away from cycles
- [ ] `ModuleRef` for looking up or creating providers dynamically
- [ ] Lazy-loaded modules and discovery of providers, when needed

## 4. Controllers and HTTP APIs

- [ ] Controllers and route decorators: `@Controller`, `@Get`, `@Post`, `@Put`, `@Patch`, and `@Delete`
- [ ] Route parameters, query parameters, request bodies, headers, and cookies
- [ ] Built-in parameter decorators such as `@Param`, `@Query`, `@Body`, `@Headers`, and `@Req`
- [ ] Using typed DTO classes to describe incoming and outgoing data
- [ ] Returning values versus using the response object directly; standard and library-specific response modes
- [ ] Status codes, response headers, redirects, and consistent response shapes
- [ ] REST resource design, CRUD endpoints, pagination, filtering, sorting, and API error conventions
- [ ] Route ordering, wildcard routes, nested routes, and route parameter parsing
- [ ] URI, header, media-type, and custom API versioning
- [ ] Global prefixes, CORS, cookies, sessions, compression, and raw request bodies
- [ ] Choosing and configuring the Express or Fastify HTTP adapter
- [ ] Static assets, server-sent events, streaming, and file upload/download basics
- [ ] MVC and server-rendered views, if building a traditional web application

## 5. Request pipeline and cross-cutting components

- [ ] The request lifecycle and the order middleware, guards, interceptors, pipes, controllers, and exception filters run
- [ ] Middleware for request-level work such as correlation IDs or simple request logging
- [ ] Guards for deciding whether a request may proceed
- [ ] Pipes for validation and transformation of input
- [ ] Interceptors for wrapping execution, mapping results, timing, caching, and response handling
- [ ] Exception filters for shaping and logging unhandled errors
- [ ] Global, controller-level, and route-level registration and scope
- [ ] The `ExecutionContext`, `ArgumentsHost`, and `CallHandler` abstractions
- [ ] Custom parameter decorators and metadata decorators
- [ ] Building reusable decorators by composing other decorators

## 6. Validation, transformation, and errors

- [ ] DTO classes and the difference between compile-time TypeScript types and runtime validation
- [ ] `ValidationPipe`, `class-validator`, and `class-transformer` fundamentals
- [ ] Whitelisting, rejecting unknown fields, transforming values, and validating nested DTOs
- [ ] Optional, partial, nested, array, and mapped DTO types
- [ ] Reusing DTOs safely for create/update operations without leaking persistence models
- [ ] Validation of environment/configuration values at application startup
- [ ] Nest HTTP exceptions, custom exceptions, and consistent error response formats
- [ ] Translating domain or database errors into suitable HTTP responses
- [ ] Avoiding exposure of stack traces, secrets, or internal implementation details

## 7. Configuration and application setup

- [ ] Environment-specific configuration and the `@nestjs/config` package
- [ ] `.env` files versus deployment-provided environment variables; never committing secrets
- [ ] Typed/namespaced configuration and validating required settings at startup
- [ ] Async configuration for modules that depend on configuration values
- [ ] Bootstrap configuration: global pipes, guards, interceptors, filters, prefix, CORS, and shutdown hooks
- [ ] Logging configuration for development, tests, and production
- [ ] Application lifecycle hooks and startup/shutdown ordering
- [ ] Separating configuration from business logic

## 8. Data persistence

- [ ] Connecting Nest modules/providers to a relational or document database
- [ ] Choosing an ORM/query builder or using a database driver directly
- [ ] Entities/models, schemas, repositories, and data-access boundaries
- [ ] CRUD operations and mapping database records to API/domain models
- [ ] Migrations, schema changes, and seed data
- [ ] Transactions, isolation, and handling concurrent updates
- [ ] Indexes, constraints, pagination, connection pools, and query performance
- [ ] Avoiding N+1 queries and understanding eager/lazy loading behavior
- [ ] Database error handling and safe parameterized queries
- [ ] Testing persistence code with a test database or controlled substitutes

## 9. Authentication and security

- [ ] Authentication versus authorization
- [ ] Password storage with a suitable one-way hash and salt; never storing plaintext passwords
- [ ] Sessions and cookies versus token-based authentication
- [ ] Passport integration, strategies, guards, and current-user decorators
- [ ] JWT access/refresh token concepts, expiration, signing keys, and revocation trade-offs
- [ ] Authorization with roles, permissions, claims, and resource ownership policies
- [ ] Public routes, authenticated routes, and default-deny authorization design
- [ ] CORS, CSRF, secure cookies, security headers, and HTTPS
- [ ] Rate limiting/throttling and abuse prevention
- [ ] Input validation, output serialization, secret handling, and dependency updates
- [ ] Encryption versus hashing and key management basics
- [ ] Security review of file uploads, redirects, logs, error messages, and external input

## 10. Testing and code quality

- [ ] Unit testing providers and business logic
- [ ] `@nestjs/testing`, `Test.createTestingModule()`, and compiling a testing module
- [ ] Mocking/replacing providers and overriding guards, pipes, interceptors, or filters
- [ ] Integration tests for database and external service boundaries
- [ ] End-to-end tests for HTTP behavior, often using Supertest
- [ ] Testing validation, authorization, error responses, and edge cases
- [ ] Test configuration, fixtures, factories, and isolation between tests
- [ ] Linting, formatting, type checking, and code coverage as project quality tools
- [ ] Keeping business logic testable without bootstrapping the whole application

## 11. API documentation and serialization

- [ ] OpenAPI/Swagger setup and keeping the API specification accurate
- [ ] Documenting DTOs, parameters, responses, auth schemes, and error cases
- [ ] Serialization and controlling which properties are exposed to clients
- [ ] Excluding secrets/internal fields and handling nested objects
- [ ] API versioning and deprecation strategies
- [ ] Generating or consuming typed API clients from an API contract

## 12. Common application techniques

- [ ] Structured logging and request/correlation IDs
- [ ] Caching: cache keys, TTLs, invalidation, and distributed caches
- [ ] Scheduling recurring and delayed tasks
- [ ] Queues and background jobs: producers, consumers, retries, failures, and idempotent processing
- [ ] Events and event emitters for in-process decoupling
- [ ] Calling external APIs with an HTTP client, timeouts, and error handling
- [ ] File storage, upload limits, validation, streaming, and cloud/object storage
- [ ] Health checks, readiness/liveness, and dependency health
- [ ] Request context and async-local storage where context must cross async calls
- [ ] Graceful shutdown and cleanup of database, queue, and network connections

## 13. Alternative application styles

Learn these when your application needs them:

- [ ] GraphQL: code-first versus schema-first, resolvers, queries, mutations, inputs, scalars, and context
- [ ] GraphQL authorization, subscriptions, DataLoader/N+1 prevention, schema complexity, and federation
- [ ] WebSockets: gateways, adapters, events, rooms, authentication, and error handling
- [ ] Microservices: message patterns, request-response versus event-based communication, and transporters
- [ ] Redis, RabbitMQ, Kafka, NATS, MQTT, and gRPC integrations; choose only the transports your system uses
- [ ] Message validation, acknowledgements, retries, dead-letter handling, idempotency, and schema evolution
- [ ] Hybrid applications that combine HTTP with microservice or WebSocket transports
- [ ] Serverless deployment and adapting bootstrap/lifecycle to a serverless runtime

## 14. Architecture and reliability

- [ ] Organizing by feature/domain instead of creating oversized shared modules
- [ ] Keeping controllers focused on transport concerns and services focused on application logic
- [ ] Separating domain rules from Nest decorators and infrastructure where it helps maintainability
- [ ] Dependency direction, interfaces/tokens, and boundaries between modules
- [ ] Modular monolith versus microservices and the operational cost of distributed systems
- [ ] CQRS: commands, queries, handlers, buses, and when the added structure is useful
- [ ] Resilience: timeouts, retries with backoff, circuit breakers, and bulkheads
- [ ] Idempotency keys and safe handling of repeated requests/messages
- [ ] Distributed locks and coordination risks
- [ ] Transactional outbox and reliable event publication across database/message broker boundaries
- [ ] Observability: logs, metrics, traces, error monitoring, dashboards, and useful service-level indicators
- [ ] Performance profiling, load testing, caching choices, and Fastify/adapter trade-offs

## 15. Build, deployment, and operations

- [ ] Production builds, compiled output, source maps, and runtime entry points
- [ ] Node.js process management and environment-specific settings
- [ ] Docker/container fundamentals and multi-stage builds
- [ ] Health probes, graceful termination, and rolling deployment concerns
- [ ] Database migration strategy during releases
- [ ] Secret management and least-privilege credentials
- [ ] CI workflows for linting, type checks, tests, and builds
- [ ] Logging/metrics/tracing collection in the hosting environment
- [ ] Scaling stateless HTTP services and externalizing shared state
- [ ] Common NestJS troubleshooting: dependency resolution, circular dependencies, missing metadata, and module configuration

## Suggested milestones

- [ ] **Beginner:** Build a REST CRUD API with feature modules, providers, DTO validation, and centralized error handling.
- [ ] **Intermediate:** Add database persistence, authentication/authorization, configuration validation, OpenAPI docs, and unit/e2e tests.
- [ ] **Advanced:** Add queues or events, caching, observability, deployment automation, and resilient integrations.
- [ ] **Specialist:** Learn GraphQL, WebSockets, microservices, CQRS, serverless, or advanced reliability patterns based on project needs.
