# PROJECT DOGMA-01 — NestJS Prerequisite Checklist

> **The Scope:** Strictly NestJS concepts required to build Project 1.  
> Each level is a single NestJS building block. Master them in order before assembling the full NERV Central Dogma API.

---

### Level 1: The App Root & Bootstrapping
- [ ] **1. `main.ts` & `NestFactory`:** Bootstrapping the app with `NestFactory.create(AppModule)` and starting the listener on a port. — [Docs: First Steps](https://docs.nestjs.com/first-steps)
- [ ] **2. The Root Module (`AppModule`):** How `@Module()` acts as the root orchestrator of controllers and providers. — [Docs: Modules](https://docs.nestjs.com/modules)

---

### Level 2: Controllers & Request Handling
- [ ] **3. `@Controller()`:** Defining route prefixes (e.g., `@Controller('pilots')`). — [Docs: Controllers](https://docs.nestjs.com/controllers)
- [ ] **4. Route Handlers:** Mapping HTTP verbs to methods (`@Get()`, `@Post()`, `@Patch()`, `@Delete()`). — [Docs: Routing](https://docs.nestjs.com/controllers#routing)
- [ ] **5. Parameter Extraction:** Using `@Param('id')`, `@Query()`, and `@Body()` to read incoming HTTP data. — [Docs: Request Object](https://docs.nestjs.com/controllers#request-object)
- [ ] **6. Status Codes & Responses:** Returning plain objects (automatic JSON serialization) and setting `@HttpCode()`. — [Docs: Status Code](https://docs.nestjs.com/controllers#status-code)

---

### Level 3: Providers & Dependency Injection (DI)
- [ ] **7. `@Injectable()`:** Marking a class as a provider that NestJS can manage and inject. — [Docs: Providers](https://docs.nestjs.com/providers)
- [ ] **8. Provider Registration:** Adding a service to a module's `providers: [PilotsService]`. — [Docs: Services](https://docs.nestjs.com/providers#services)
- [ ] **9. Constructor Injection:** Injecting dependencies via `constructor(private readonly pilotsService: PilotsService) {}`. — [Docs: Dependency Injection](https://docs.nestjs.com/providers#dependency-injection)
- [ ] **10. Resolving DI Errors:** Understanding and fixing `"Nest can't resolve dependencies of the..."`. — [Docs: Common Errors](https://docs.nestjs.com/faq/common-errors)

---

### Level 4: Feature Modules & Boundaries
- [ ] **11. Feature Modules:** Encapsulating a domain (`PilotsModule`, `EvaModule`) into its own `@Module()`. — [Docs: Feature Modules](https://docs.nestjs.com/modules#feature-modules)
- [ ] **12. Module Imports & Exports:** Exporting providers from Module B and importing Module B into Module A. — [Docs: Shared Modules](https://docs.nestjs.com/modules#shared-modules)

---

### Level 5: DTOs & Validation (The Input Boundary)
- [ ] **13. DTO Classes:** Why NestJS uses TypeScript classes (not interfaces) so they exist at runtime. — [Docs: Request Payloads](https://docs.nestjs.com/controllers#request-payloads)
- [ ] **14. Global `ValidationPipe`:** Enabling `app.useGlobalPipes(new ValidationPipe())` in `main.ts`. — [Docs: ValidationPipe](https://docs.nestjs.com/techniques/validation#using-the-built-in-validationpipe)
- [ ] **15. `class-validator` Decorators:** Validating payload fields (`@IsString()`, `@IsNumber()`, `@Min()`, `@Max()`, `@IsEnum()`). — [Docs: Auto-validation](https://docs.nestjs.com/techniques/validation#auto-validation)
- [ ] **16. Stripping Malicious Fields:** Configuring `whitelist: true` and `forbidNonWhitelisted: true` to reject unknown body properties. — [Docs: Stripping Properties](https://docs.nestjs.com/techniques/validation#stripping-properties)

---

### Level 6: Error Handling (Exceptions)
- [ ] **17. Built-in HTTP Exceptions:** Throwing `NotFoundException`, `BadRequestException`, `ForbiddenException`, and `UnauthorizedException`. — [Docs: Built-in Exceptions](https://docs.nestjs.com/exception-filters#built-in-http-exceptions)
- [ ] **18. Centralized Exception Responses:** How NestJS catches unhandled exceptions and formats the JSON error envelope. — [Docs: Exception Filters](https://docs.nestjs.com/exception-filters)

---

### Level 7: Configuration & Environment
- [ ] **19. `@nestjs/config`:** Registering `ConfigModule.forRoot({ isGlobal: true })` to load `.env`. — [Docs: Configuration](https://docs.nestjs.com/techniques/configuration)
- [ ] **20. `ConfigService`:** Injecting `ConfigService` to read database URLs and JWT secrets safely. — [Docs: Using ConfigService](https://docs.nestjs.com/techniques/configuration#using-the-configservice)

---

### Level 8: Database & Persistence Integration
- [ ] **21. Database Provider:** Creating a database service (e.g., `PrismaService` or `TypeOrmModule`) as an injectable provider. — [Docs: Prisma Recipe](https://docs.nestjs.com/recipes/prisma)
- [ ] **22. Lifecycle Hooks:** Implementing `onModuleInit` to connect to the database when the NestJS module starts. — [Docs: Lifecycle Events](https://docs.nestjs.com/fundamentals/lifecycle-events)
- [ ] **23. Service-to-Database CRUD:** Querying the database inside service methods and returning entities to controllers. — [Docs: Prisma Service Usage](https://docs.nestjs.com/recipes/prisma#use-prisma-client-in-your-nestjs-services)

---

### Level 9: Guards & Authorization (Security)
- [ ] **24. `CanActivate` Guards:** Creating a class implementing `CanActivate` and returning a boolean or throwing an exception. — [Docs: Guards](https://docs.nestjs.com/guards)
- [ ] **25. Binding Guards:** Applying guards with `@UseGuards(AuthGuard)` at controller or route level. — [Docs: Binding Guards](https://docs.nestjs.com/guards#binding-guards)
- [ ] **26. Custom Metadata & Reflector:** Using `@SetMetadata('roles', ['COMMANDER'])` and `Reflector` to read required roles in a Guard. — [Docs: Reflection & Metadata](https://docs.nestjs.com/guards#putting-it-all-together)

---

### Level 10: Assembly (Executing PROJECT DOGMA-01)
- [ ] **27. Modules:** `AuthModule`, `PersonnelModule`, `EvaModule`, `SortieModule`. — [Docs: Modules](https://docs.nestjs.com/modules)
- [ ] **28. Endpoints:** CRUD for Pilots, Evas, and Sorties with DTO validation. — [Docs: Controllers](https://docs.nestjs.com/controllers)
- [ ] **29. Security:** JWT guard + NERV clearance roles (`SUPREME_COMMANDER`, `TACTICAL_CHIEF`, `CHILDREN_PILOT`). — [Docs: Authentication](https://docs.nestjs.com/security/authentication)
- [ ] **30. Documentation:** `@nestjs/swagger` with `@ApiTags()` and `@ApiOperation()` at `/api/docs`. — [Docs: OpenAPI (Swagger)](https://docs.nestjs.com/openapi/introduction)
