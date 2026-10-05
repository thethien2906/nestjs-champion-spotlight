# PROJECT DOGMA-01 — NestJS Prerequisite Checklist

> **The Scope:** Strictly NestJS concepts required to build Project 1.  
> Each level is a single NestJS building block. Master them in order before assembling the full NERV Central Dogma API.

---

### Level 1: The App Root & Bootstrapping
- [ ] **1. `main.ts` & `NestFactory`:** Bootstrapping the app with `NestFactory.create(AppModule)` and starting the listener on a port.
- [ ] **2. The Root Module (`AppModule`):** How `@Module()` acts as the root orchestrator of controllers and providers.

---

### Level 2: Controllers & Request Handling
- [ ] **3. `@Controller()`:** Defining route prefixes (e.g., `@Controller('pilots')`).
- [ ] **4. Route Handlers:** Mapping HTTP verbs to methods (`@Get()`, `@Post()`, `@Patch()`, `@Delete()`).
- [ ] **5. Parameter Extraction:** Using `@Param('id')`, `@Query()`, and `@Body()` to read incoming HTTP data.
- [ ] **6. Status Codes & Responses:** Returning plain objects (automatic JSON serialization) and setting `@HttpCode(HttpStatus.CREATED)`.

---

### Level 3: Providers & Dependency Injection (DI)
- [ ] **7. `@Injectable()`:** Marking a class as a provider that NestJS can manage and inject.
- [ ] **8. Provider Registration:** Adding a service to a module's `providers: [PilotsService]`.
- [ ] **9. Constructor Injection:** Injecting dependencies via `constructor(private readonly pilotsService: PilotsService) {}`.
- [ ] **10. Resolving DI Errors:** Understanding and fixing `"Nest can't resolve dependencies of the..."`.

---

### Level 4: Feature Modules & Boundaries
- [ ] **11. Feature Modules:** Encapsulating a domain (`PilotsModule`, `EvaModule`) into its own `@Module()`.
- [ ] **12. Module Imports & Exports:** When module A needs a service from module B:
  - Module B adds it to `exports: [BService]`.
  - Module A adds Module B to `imports: [ModuleB]`.

---

### Level 5: DTOs & Validation (The Input Boundary)
- [ ] **13. DTO Classes:** Why NestJS uses TypeScript classes (not interfaces) so they exist at runtime.
- [ ] **14. Global `ValidationPipe`:** Enabling `app.useGlobalPipes(new ValidationPipe())` in `main.ts`.
- [ ] **15. `class-validator` Decorators:** Validating payload fields (`@IsString()`, `@IsNumber()`, `@Min()`, `@Max()`, `@IsEnum()`).
- [ ] **16. Stripping Malicious Fields:** Configuring `whitelist: true` and `forbidNonWhitelisted: true` to reject unknown body properties.

---

### Level 6: Error Handling (Exceptions)
- [ ] **17. Built-in HTTP Exceptions:** Throwing `NotFoundException`, `BadRequestException`, `ForbiddenException`, and `UnauthorizedException`.
- [ ] **18. Centralized Exception Responses:** How NestJS catches unhandled exceptions and formats the JSON error envelope.

---

### Level 7: Configuration & Environment
- [ ] **19. `@nestjs/config`:** Registering `ConfigModule.forRoot({ isGlobal: true })` to load `.env`.
- [ ] **20. `ConfigService`:** Injecting `ConfigService` to read database URLs and JWT secrets safely.

---

### Level 8: Database & Persistence Integration
- [ ] **21. Database Provider:** Creating a database service (e.g., `PrismaService` or `TypeOrmModule`) as an injectable provider.
- [ ] **22. Lifecycle Hooks:** Implementing `onModuleInit` to connect to the database when the NestJS module starts.
- [ ] **23. Service-to-Database CRUD:** Querying the database inside service methods and returning entities to controllers.

---

### Level 9: Guards & Authorization (Security)
- [ ] **24. `CanActivate` Guards:** Creating a class implementing `CanActivate` and returning `true` (allow) or `false` / `UnauthorizedException` (block).
- [ ] **25. Binding Guards:** Applying guards with `@UseGuards(AuthGuard)` at controller or route level.
- [ ] **26. Custom Metadata & Reflector:** Using `@SetMetadata('roles', ['COMMANDER'])` and Nest's `Reflector` to read required roles in a Guard.

---

### Level 10: Assembly (Executing PROJECT DOGMA-01)
- [ ] **27. Modules:** `AuthModule`, `PersonnelModule`, `EvaModule`, `SortieModule`.
- [ ] **28. Endpoints:** CRUD for Pilots, Evas, and Sorties with DTO validation.
- [ ] **29. Security:** JWT guard + NERV clearance roles (`SUPREME_COMMANDER`, `TACTICAL_CHIEF`, `CHILDREN_PILOT`).
- [ ] **30. Documentation:** `@nestjs/swagger` with `@ApiTags()` and `@ApiOperation()` at `/api/docs`.
