# 8. Spring Framework

> Source range: questions 176–200
## 176. What is Spring Framework?

1. **Question**: What is Spring Framework?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: Spring is a modular Java framework that provides IoC/DI, configuration, AOP, transactions, web support, and integration abstractions.
6. **Detailed explanation**: Spring is a modular Java framework that provides IoC/DI, configuration, AOP, transactions, web support, and integration abstractions. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “What is Spring Framework?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: Spring is a modular Java framework that provides IoC/DI, configuration, AOP, transactions, web support, and integration abstractions.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 177. What is IoC?

1. **Question**: What is IoC?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: IoC means object creation and dependency wiring are controlled by the Spring container rather than application classes constructing everything themselves.
6. **Detailed explanation**: IoC means object creation and dependency wiring are controlled by the Spring container rather than application classes constructing everything themselves. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “What is IoC?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: IoC means object creation and dependency wiring are controlled by the Spring container rather than application classes constructing everything themselves.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 178. What is Dependency Injection?

1. **Question**: What is Dependency Injection?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: Dependency Injection supplies a class with its collaborators through constructors, setters, or fields. It separates policy from object assembly and improves testing.
6. **Detailed explanation**: Dependency Injection supplies a class with its collaborators through constructors, setters, or fields. It separates policy from object assembly and improves testing. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “What is Dependency Injection?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: Dependency Injection supplies a class with its collaborators through constructors, setters, or fields. It separates policy from object assembly and improves testing.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 179. Constructor injection vs setter injection vs field injection?

1. **Question**: Constructor injection vs setter injection vs field injection?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: Constructor injection makes required dependencies explicit and supports immutability. Setter injection suits optional dependencies. Field injection hides dependencies and is harder to test.
6. **Detailed explanation**: Constructor injection makes required dependencies explicit and supports immutability. Setter injection suits optional dependencies. Field injection hides dependencies and is harder to test. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “Constructor injection vs setter injection vs field injection?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: Constructor injection makes required dependencies explicit and supports immutability. Setter injection suits optional dependencies. Field injection hides dependencies and is harder to test.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 180. Why is constructor injection generally preferred?

1. **Question**: Why is constructor injection generally preferred?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: Constructor injection is preferred because required dependencies are visible, objects can be immutable, and invalid construction is prevented.
6. **Detailed explanation**: Constructor injection is preferred because required dependencies are visible, objects can be immutable, and invalid construction is prevented. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “Why is constructor injection generally preferred?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: Constructor injection is preferred because required dependencies are visible, objects can be immutable, and invalid construction is prevented.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 181. What is a Spring Bean?

1. **Question**: What is a Spring Bean?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: A Spring Bean is an object instantiated, configured, and managed by an ApplicationContext according to its scope and lifecycle callbacks.
6. **Detailed explanation**: A Spring Bean is an object instantiated, configured, and managed by an ApplicationContext according to its scope and lifecycle callbacks. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “What is a Spring Bean?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: A Spring Bean is an object instantiated, configured, and managed by an ApplicationContext according to its scope and lifecycle callbacks.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 182. What are Spring Bean scopes?

1. **Question**: What are Spring Bean scopes?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: Common scopes are singleton, prototype, request, session, application, and websocket. Web scopes require an appropriate web-aware context.
6. **Detailed explanation**: Common scopes are singleton, prototype, request, session, application, and websocket. Web scopes require an appropriate web-aware context. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “What are Spring Bean scopes?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: Common scopes are singleton, prototype, request, session, application, and websocket. Web scopes require an appropriate web-aware context.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 183. Explain the Spring Bean lifecycle.

1. **Question**: Explain the Spring Bean lifecycle.
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: Spring creates the bean, injects dependencies, applies post-processors and proxies, invokes initialization callbacks, and later runs destruction callbacks when the context closes.
6. **Detailed explanation**: Spring creates the bean, injects dependencies, applies post-processors and proxies, invokes initialization callbacks, and later runs destruction callbacks when the context closes. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “Explain the Spring Bean lifecycle.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: Spring creates the bean, injects dependencies, applies post-processors and proxies, invokes initialization callbacks, and later runs destruction callbacks when the context closes.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 184. `@Component` vs `@Service` vs `@Repository`?

1. **Question**: `@Component` vs `@Service` vs `@Repository`?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: All are stereotype annotations: Component is generic, Service expresses service-layer intent, and Repository expresses persistence intent and enables exception translation.
6. **Detailed explanation**: All are stereotype annotations: Component is generic, Service expresses service-layer intent, and Repository expresses persistence intent and enables exception translation. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “`@Component` vs `@Service` vs `@Repository`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: All are stereotype annotations: Component is generic, Service expresses service-layer intent, and Repository expresses persistence intent and enables exception translation.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 185. `@Bean` vs `@Component`?

1. **Question**: `@Bean` vs `@Component`?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: @Component discovers a class through scanning. @Bean declares an object returned by a configuration method, useful for third-party or programmatic construction.
6. **Detailed explanation**: @Component discovers a class through scanning. @Bean declares an object returned by a configuration method, useful for third-party or programmatic construction. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “`@Bean` vs `@Component`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: @Component discovers a class through scanning. @Bean declares an object returned by a configuration method, useful for third-party or programmatic construction.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 186. `@Configuration`?

1. **Question**: `@Configuration`?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: @Configuration marks a class that declares bean definitions. Spring enhances it so calls between @Bean methods respect container-managed singleton semantics.
6. **Detailed explanation**: @Configuration marks a class that declares bean definitions. Spring enhances it so calls between @Bean methods respect container-managed singleton semantics. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “`@Configuration`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: @Configuration marks a class that declares bean definitions. Spring enhances it so calls between @Bean methods respect container-managed singleton semantics.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 187. `@Autowired`?

1. **Question**: `@Autowired`?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: @Autowired asks Spring to resolve and inject a dependency by type, using qualifiers or primary beans when multiple candidates exist.
6. **Detailed explanation**: @Autowired asks Spring to resolve and inject a dependency by type, using qualifiers or primary beans when multiple candidates exist. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “`@Autowired`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: @Autowired asks Spring to resolve and inject a dependency by type, using qualifiers or primary beans when multiple candidates exist.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 188. `@Qualifier`?

1. **Question**: `@Qualifier`?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: @Qualifier selects a specific bean when several match the required type.
6. **Detailed explanation**: @Qualifier selects a specific bean when several match the required type. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “`@Qualifier`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: @Qualifier selects a specific bean when several match the required type.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 189. `@Primary`?

1. **Question**: `@Primary`?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: @Primary marks one candidate as the default when multiple beans match and no qualifier is supplied.
6. **Detailed explanation**: @Primary marks one candidate as the default when multiple beans match and no qualifier is supplied. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “`@Primary`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: @Primary marks one candidate as the default when multiple beans match and no qualifier is supplied.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 190. What is circular dependency?

1. **Question**: What is circular dependency?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: Circular dependency occurs when bean A requires B while B requires A, preventing straightforward construction and often indicating excessive coupling.
6. **Detailed explanation**: Circular dependency occurs when bean A requires B while B requires A, preventing straightforward construction and often indicating excessive coupling. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “What is circular dependency?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: Circular dependency occurs when bean A requires B while B requires A, preventing straightforward construction and often indicating excessive coupling.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 191. How do you resolve circular dependencies?

1. **Question**: How do you resolve circular dependencies?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: Refactor responsibilities, introduce an interface or mediator, use events, or defer an optional dependency. Constructor injection exposes cycles early.
6. **Detailed explanation**: Refactor responsibilities, introduce an interface or mediator, use events, or defer an optional dependency. Constructor injection exposes cycles early. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “How do you resolve circular dependencies?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: Refactor responsibilities, introduce an interface or mediator, use events, or defer an optional dependency. Constructor injection exposes cycles early.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 192. What is Spring AOP?

1. **Question**: What is Spring AOP?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: Spring AOP applies cross-cutting behavior such as transactions, security, logging, and metrics through proxies or weaving.
6. **Detailed explanation**: Spring AOP applies cross-cutting behavior such as transactions, security, logging, and metrics through proxies or weaving. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “What is Spring AOP?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: Spring AOP applies cross-cutting behavior such as transactions, security, logging, and metrics through proxies or weaving.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 193. What are Aspect, Advice, JoinPoint, and Pointcut?

1. **Question**: What are Aspect, Advice, JoinPoint, and Pointcut?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: An aspect groups cross-cutting logic; advice is the action, a join point is an execution point, and a pointcut selects join points.
6. **Detailed explanation**: An aspect groups cross-cutting logic; advice is the action, a join point is an execution point, and a pointcut selects join points. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “What are Aspect, Advice, JoinPoint, and Pointcut?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: An aspect groups cross-cutting logic; advice is the action, a join point is an execution point, and a pointcut selects join points.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 194. What is a Spring proxy?

1. **Question**: What is a Spring proxy?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: A Spring proxy wraps a target and intercepts method calls to apply advice before delegating to the target.
6. **Detailed explanation**: A Spring proxy wraps a target and intercepts method calls to apply advice before delegating to the target. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “What is a Spring proxy?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: A Spring proxy wraps a target and intercepts method calls to apply advice before delegating to the target.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 195. JDK dynamic proxy vs CGLIB?

1. **Question**: JDK dynamic proxy vs CGLIB?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: JDK proxies implement interfaces. CGLIB creates a subclass for concrete classes; final classes or methods limit subclass proxying.
6. **Detailed explanation**: JDK proxies implement interfaces. CGLIB creates a subclass for concrete classes; final classes or methods limit subclass proxying. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “JDK dynamic proxy vs CGLIB?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: JDK proxies implement interfaces. CGLIB creates a subclass for concrete classes; final classes or methods limit subclass proxying.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 196. How does `@Transactional` work internally?

1. **Question**: How does `@Transactional` work internally?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: @Transactional is applied by a proxy that starts or joins a transaction before invocation and commits or rolls back according to configured rules.
6. **Detailed explanation**: @Transactional is applied by a proxy that starts or joins a transaction before invocation and commits or rolls back according to configured rules. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “How does `@Transactional` work internally?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: @Transactional is applied by a proxy that starts or joins a transaction before invocation and commits or rolls back according to configured rules.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 197. Why might `@Transactional` not work during self-invocation?

1. **Question**: Why might `@Transactional` not work during self-invocation?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: Self-invocation calls this.method() directly and bypasses the proxy, so proxy-based advice such as @Transactional is not applied.
6. **Detailed explanation**: Self-invocation calls this.method() directly and bypasses the proxy, so proxy-based advice such as @Transactional is not applied. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “Why might `@Transactional` not work during self-invocation?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: Self-invocation calls this.method() directly and bypasses the proxy, so proxy-based advice such as @Transactional is not applied.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 198. What are transaction propagation types?

1. **Question**: What are transaction propagation types?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: Propagation defines how a method participates in transactions: REQUIRED joins or creates, REQUIRES_NEW suspends and creates, and SUPPORTS joins if present.
6. **Detailed explanation**: Propagation defines how a method participates in transactions: REQUIRED joins or creates, REQUIRES_NEW suspends and creates, and SUPPORTS joins if present. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “What are transaction propagation types?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: Propagation defines how a method participates in transactions: REQUIRED joins or creates, REQUIRES_NEW suspends and creates, and SUPPORTS joins if present.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 199. What are transaction isolation levels?

1. **Question**: What are transaction isolation levels?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: Isolation controls visibility of concurrent changes. READ_COMMITTED, REPEATABLE_READ, SERIALIZABLE, and database-specific levels trade consistency for concurrency.
6. **Detailed explanation**: Isolation controls visibility of concurrent changes. READ_COMMITTED, REPEATABLE_READ, SERIALIZABLE, and database-specific levels trade consistency for concurrency. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “What are transaction isolation levels?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: Isolation controls visibility of concurrent changes. READ_COMMITTED, REPEATABLE_READ, SERIALIZABLE, and database-specific levels trade consistency for concurrency.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---

## 200. What is the Spring ApplicationContext?

1. **Question**: What is the Spring ApplicationContext?
2. **Difficulty**: Advanced
3. **Topic**: Spring Framework
4. **What interviewer is testing**: Whether you understand container behavior, proxy boundaries, lifecycle, and production-safe framework usage.
5. **Short interview answer (30–60 seconds)**: ApplicationContext is Spring’s IoC container and provides bean creation, dependency resolution, configuration, events, resources, and lifecycle management.
6. **Detailed explanation**: ApplicationContext is Spring’s IoC container and provides bean creation, dependency resolution, configuration, events, resources, and lifecycle management. The annotation, lifecycle point, proxy boundary, and failure mode define the behavior at runtime.
7. **How it works internally**: The ApplicationContext scans or registers definitions, resolves dependencies, applies BeanPostProcessors, and creates proxies where advisors match.
8. **Example**:

For “What is the Spring ApplicationContext?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Framework wiring is startup work; business-operation cost includes proxy, transaction, lookup, and downstream I/O overhead.
11. **Real-world/project usage**: Use Spring for service composition, persistence boundaries, cross-cutting policies, and testable application modules.
12. **Common mistakes**: Relying on field injection, misunderstanding proxy scope, creating cycles, using self-invocation, or placing business logic in configuration.
13. **Advantages**: Loose coupling, declarative infrastructure, testability, lifecycle management, and a mature ecosystem.
14. **Limitations**: Startup and proxy overhead, hidden wiring, configuration complexity, and behavior that depends on boundaries and context.
15. **Comparison with related concepts**: Compare constructor/setter/field injection, JDK/CGLIB proxies, and local/global cross-cutting approaches.
16. **Production considerations**: Keep bean graphs simple, verify proxy behavior with integration tests, configure transactions explicitly, and monitor startup and runtime failures.
17. **Possible follow-up questions**: What happens with multiple beans, self-invocation, circular dependencies, or context shutdown?
18. **Senior-level follow-up questions**: How would you diagnose startup or proxy issues and evolve the module without breaking transactional behavior?
19. **Scenario-based question**: An annotation appears to have no effect in production. Explain how you would inspect bean registration, proxy type, invocation path, and configuration.
20. **One-line revision note**: ApplicationContext is Spring’s IoC container and provides bean creation, dependency resolution, configuration, events, resources, and lifecycle management.
21. **Image visuals (if required)**: Bean lifecycle or proxy/interceptor diagrams help explain framework internals.

---
