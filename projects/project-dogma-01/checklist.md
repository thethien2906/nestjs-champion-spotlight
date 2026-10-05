# PROJECT DOGMA-01 — Prerequisite & Mastery Checklist

> **The Philosophy:** Project 1 is Calculus (Derivatives). You cannot solve derivatives without first mastering arithmetic, algebra, functions, and limits.  
> Work through these foundational tiers in order. Each tier represents a non-negotiable building block required to understand *why* the code in Project 1 works.

---

## Tier 1: JavaScript Runtime & Core Mechanics (Arithmetic & Rules)

- [ ] **1. Value vs. Reference Types:** Stack vs. Heap allocation; primitives (string, number, boolean, null, undefined, symbol) vs. Objects and Arrays.
- [ ] **2. Equality Semantics:** `==` (type coercion) vs. `===` (strict equality) and object reference comparison (`{} === {}` is false).
- [ ] **3. Truthy & Falsy Values:** How conditionals evaluate non-boolean values; the 8 falsy values in JS.
- [ ] **4. Object & Array Immutability:** Spread operator (`...`), rest parameters, destructuring assignment, and shallow vs. deep cloning.
- [ ] **5. Array Functional Iterators:** `map()`, `filter()`, `reduce()`, `find()`, `some()`, `every()` without mutating the original array.
- [ ] **6. Scope & Lexical Environment:** Global scope, function scope, block scope (`let`/`const` vs `var`), and variable hoisting.
- [ ] **7. Execution Context & Call Stack:** How the JS engine executes lines, pushes frame onto stack, and pops them off upon return.
- [ ] **8. Closures:** How functions retain access to their outer lexical scope after the outer function has returned.
- [ ] **9. Error Throwing & Handling:** `try`, `catch`, `finally`, custom `Error` classes, and synchronous error propagation.

---

## Tier 2: Asynchronous Execution & Node.js (Fractions & Exponents)

- [ ] **10. Synchronous vs. Asynchronous:** Why blocking the single thread freezes the entire server process.
- [ ] **11. The Event Loop:** Call Stack, Node.js libuv thread pool, Microtask queue (`Promises`), and Macrotask queue (`setTimeout`, I/O).
- [ ] **12. The Callback Pattern:** How async was originally handled and why nested callbacks cause "callback hell."
- [ ] **13. Promises:** The three states (`pending`, `fulfilled`, `rejected`), chaining `.then()`, `.catch()`, and `.finally()`.
- [ ] **14. `async` / `await` Syntax:** Syntactic sugar over Promises; how `await` suspends execution within an async function without blocking the thread.
- [ ] **15. Asynchronous Error Handling:** Using `try / catch` with `await` and catching unhandled Promise rejections.
- [ ] **16. Concurrent Asynchronous Operations:** `Promise.all()` (fail-fast), `Promise.allSettled()`, and parallel vs. sequential loops.
- [ ] **17. Node.js Environment & Process:** `process.env`, loading environment variables, and the process lifecycle (`process.on('SIGINT')`).
- [ ] **18. Module Systems:** CommonJS (`require` / `module.exports`) vs. ECMAScript Modules (`import` / `export`).

---

## Tier 3: Object-Oriented Programming (Algebra & Polynomials)

- [ ] **19. Classes as Blueprints:** What a class is; constructor functions; instantiating objects with `new`.
- [ ] **20. The `this` Keyword:** How `this` is bound at call-site in regular functions vs. lexically captured in arrow functions.
- [ ] **21. Class Fields & Methods:** Instance properties, instance methods, static properties, and static factory methods.
- [ ] **22. Access Modifiers (TS):** `public`, `private`, `protected`, and `readonly` property definitions.
- [ ] **23. Parameter Properties:** TypeScript shortcut: declaring and assigning constructor arguments (`constructor(private name: string)`).
- [ ] **24. Inheritance & Polymorphism:** `extends`, calling `super()`, method overriding, and subtype polymorphism.
- [ ] **25. Abstract Classes:** Defining contracts that cannot be instantiated directly and must be implemented by subclasses.
- [ ] **26. Composition over Inheritance:** Why combining smaller objects is preferred over deep class inheritance trees.

---

## Tier 4: TypeScript Type System (Functions, Domain & Range)

- [ ] **27. Compile-Time vs. Runtime:** Type erasure; why TypeScript types vanish completely after `tsc` compiles to JavaScript.
- [ ] **28. Type Annotations & Type Inference:** When to let the compiler infer types vs. when to write explicit annotations.
- [ ] **29. Interfaces vs. Type Aliases:** When to use `interface` (declaration merging, object shapes) vs. `type` (unions, primitives).
- [ ] **30. Structural Typing (Duck Typing):** Why TypeScript compares shapes, not nominal identities (`If it walks like a duck...`).
- [ ] **31. Union & Intersection Types:** Combining types with `|` and `&`; discriminating unions with tag fields.
- [ ] **32. Optionality & Nullability:** Optional properties (`?`), strict null checks, optional chaining (`?.`), and nullish coalescing (`??`).
- [ ] **33. Generics:** Generic functions, generic classes, and generic interfaces (`Repository<T>`, `Promise<T>`).
- [ ] **34. Enums:** Numeric vs. String enums; run-time footprints vs. literal union types (`'ADMIN' | 'PILOT'`).
- [ ] **35. Utility Types:** `Partial<T>`, `Required<T>`, `Pick<T, K>`, `Omit<T, K>`, `Record<K, T>`, and `Readonly<T>`.
- [ ] **36. Type Narrowing & Guards:** `typeof`, `instanceof`, user-defined type predicates (`is`), and exhaustive checking (`never`).

---

## Tier 5: Decorators & Metadata (Trigonometry & Composite Functions)

- [ ] **37. Higher-Order Functions:** Functions that take functions as arguments or return functions.
- [ ] **38. What a Decorator Is:** A pure function called at runtime with details about a class, method, property, or parameter.
- [ ] **39. Decorator Factories:** Functions that take options/configuration and return the actual decorator function (`@Roles('ADMIN')`).
- [ ] **40. Class Decorators:** Modifying or recording metadata for a class definition (`@Controller()`, `@Injectable()`, `@Module()`).
- [ ] **41. Method & Property Decorators:** Modifying method descriptors or attaching property metadata (`@Get()`, `@Post()`, `@IsString()`).
- [ ] **42. Parameter Decorators:** Recording parameter index metadata for framework extraction (`@Body()`, `@Param()`, `@Req()`).
- [ ] **43. The `reflect-metadata` Library:** Defining metadata (`Reflect.defineMetadata`) and retrieving it at runtime (`Reflect.getMetadata`).

---

## Tier 6: HTTP Protocol & Web Networking (Limits & Continuity)

- [ ] **44. Client-Server Architecture:** The request/response transaction lifecycle over TCP/IP.
- [ ] **45. HTTP Request Anatomy:** Method, URL/Path, Query parameters (`?sort=asc`), Headers, and Request Body.
- [ ] **46. HTTP Response Anatomy:** Status code, Status message, Headers (`Content-Type`), and Response Body.
- [ ] **47. HTTP Status Code Categories:**
  - `2xx`: Success (`200 OK`, `201 Created`, `204 No Content`)
  - `4xx`: Client Error (`400 Bad Request`, `401 Unauthorized`, `403 Forbidden`, `404 Not Found`)
  - `5xx`: Server Error (`500 Internal Server Error`, `502 Bad Gateway`)
- [ ] **48. HTTP Methods & Semantics:** `GET` (safe/idempotent), `POST` (non-idempotent), `PUT` (full replace), `PATCH` (partial update), `DELETE` (idempotent).
- [ ] **49. JSON Serialization:** Serialization (`JSON.stringify`) vs. Deserialization (`JSON.parse`) across the HTTP boundary.
- [ ] **50. Statelessness & Authentication:** Why HTTP has no memory; passing identity via Bearer Tokens in the `Authorization` header.

---

## Tier 7: System Architecture Principles (The Fundamental Theorem)

- [ ] **51. Separation of Concerns (SoC):** Dividing an application into distinct sections, each addressing a separate concern.
- [ ] **52. Tight Coupling vs. Loose Coupling:** Why hardcoding `new Database()` inside a class makes it impossible to test or modify.
- [ ] **53. Inversion of Control (IoC):** Letting an external container control object lifecycle and dependency assembly instead of the object itself.
- [ ] **54. Dependency Injection (DI):** Passing required dependencies into an object (via constructor) rather than letting the object create them.
- [ ] **55. Layered Architecture (Controller-Service-Repository):**
  - **Controller:** Transport layer (HTTP parsing, status codes, routing).
  - **Service:** Domain layer (business rules, orchestration).
  - **Repository / ORM:** Persistence layer (database queries, transactions).
- [ ] **56. Data Transfer Object (DTO) Pattern:** Plain objects defining the exact contract of data crossing the network boundary.
- [ ] **57. Compile-Time Types vs. Runtime Validation:** Why `interface UserDto { age: number }` does NOT prevent a client from sending `"age": "invalid"` at runtime.
- [ ] **58. Authentication vs. Authorization:** *Authentication* = "Who are you?" (JWT verify); *Authorization* = "Are you allowed to do this?" (Role/Permission check).

---

## Tier 8: The Derivative (Executing PROJECT DOGMA-01)

*Only begin this tier when Tiers 1 through 7 are understood.*

- [ ] **59. Project Bootstrap:** Initialize NestJS application with `NestFactory` and modular structure.
- [ ] **60. Module Wiring:** Create `PersonnelModule`, `EvaModule`, `SortieModule`, and `AuthModule` with explicit imports and exports.
- [ ] **61. Thin Controllers:** Implement HTTP routes (`@Get`, `@Post`, `@Patch`) delegating pure work to services.
- [ ] **62. DTO Validation:** Bind `ValidationPipe`, `class-validator` decorators (`@IsString`, `@Min`, `@Max`), and sanitize incoming payloads.
- [ ] **63. Database Modeling:** Design relational schema (Pilots, Evas, Sorties) with Prisma/TypeORM and run migrations.
- [ ] **64. Persistence Integration:** Inject repositories/database clients into services and perform relational CRUD.
- [ ] **65. Centralized Error Handling:** Use built-in HTTP exceptions (`NotFoundException`, `ForbiddenException`) and exception filters.
- [ ] **66. Security & Guards:** Implement JWT strategy, `@Roles()` decorator, and clearance-level verification guard.
- [ ] **67. Swagger Documentation:** Decorate endpoints and DTOs with `@ApiProperty()` to publish the OpenAPI contract.
- [ ] **68. Automated Verification:** Write unit tests for business logic and E2E tests for the security boundary.
