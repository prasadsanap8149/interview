# 24. Design Patterns

> Source range: questions 628–646
## 628. What are design patterns?

1. **Question**: What are design patterns?
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Design patterns are reusable, named approaches to recurring design problems. They are guidance, not mandatory templates.
6. **Detailed explanation**: Design patterns are reusable, named approaches to recurring design problems. They are guidance, not mandatory templates. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “What are design patterns?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Design patterns are reusable, named approaches to recurring design problems. They are guidance, not mandatory templates.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 629. Creational vs structural vs behavioral patterns?

1. **Question**: Creational vs structural vs behavioral patterns?
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Creational patterns manage object creation, structural patterns compose objects, and behavioral patterns organize communication and responsibility.
6. **Detailed explanation**: Creational patterns manage object creation, structural patterns compose objects, and behavioral patterns organize communication and responsibility. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Creational vs structural vs behavioral patterns?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Creational patterns manage object creation, structural patterns compose objects, and behavioral patterns organize communication and responsibility.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 630. Explain Singleton.

1. **Question**: Explain Singleton.
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Singleton restricts a type to one instance and provides access to it. It can hide dependencies and create global state, so dependency injection is often safer.
6. **Detailed explanation**: Singleton restricts a type to one instance and provides access to it. It can hide dependencies and create global state, so dependency injection is often safer. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain Singleton.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Singleton restricts a type to one instance and provides access to it. It can hide dependencies and create global state, so dependency injection is often safer.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 631. How do you make Singleton thread-safe?

1. **Question**: How do you make Singleton thread-safe?
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Use an enum singleton, a static holder, or correct double-checked locking with volatile. Ensure serialization and reflection concerns are addressed.
6. **Detailed explanation**: Use an enum singleton, a static holder, or correct double-checked locking with volatile. Ensure serialization and reflection concerns are addressed. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “How do you make Singleton thread-safe?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (ExecutorService executor = Executors.newFixedThreadPool(2)) {
    Future<Integer> result = executor.submit(() -> 42);
    System.out.println(result.get(1, TimeUnit.SECONDS));
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Use an enum singleton, a static holder, or correct double-checked locking with volatile. Ensure serialization and reflection concerns are addressed.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 632. Explain Factory Pattern.

1. **Question**: Explain Factory Pattern.
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Factory centralizes object creation and returns an abstraction, allowing callers to avoid concrete construction decisions.
6. **Detailed explanation**: Factory centralizes object creation and returns an abstraction, allowing callers to avoid concrete construction decisions. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain Factory Pattern.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Factory centralizes object creation and returns an abstraction, allowing callers to avoid concrete construction decisions.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 633. Factory vs Abstract Factory?

1. **Question**: Factory vs Abstract Factory?
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Factory creates one product hierarchy; Abstract Factory creates related families of products that must work together.
6. **Detailed explanation**: Factory creates one product hierarchy; Abstract Factory creates related families of products that must work together. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Factory vs Abstract Factory?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Factory creates one product hierarchy; Abstract Factory creates related families of products that must work together.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 634. Explain Builder Pattern.

1. **Question**: Explain Builder Pattern.
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Builder constructs complex objects step by step and makes optional parameters readable, often ending in an immutable object.
6. **Detailed explanation**: Builder constructs complex objects step by step and makes optional parameters readable, often ending in an immutable object. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain Builder Pattern.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Builder constructs complex objects step by step and makes optional parameters readable, often ending in an immutable object.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 635. Why is Builder useful for immutable objects?

1. **Question**: Why is Builder useful for immutable objects?
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Builder validates and sets all constructor state before publication, avoiding telescoping constructors and partially initialized mutable objects.
6. **Detailed explanation**: Builder validates and sets all constructor state before publication, avoiding telescoping constructors and partially initialized mutable objects. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Why is Builder useful for immutable objects?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Builder validates and sets all constructor state before publication, avoiding telescoping constructors and partially initialized mutable objects.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 636. Explain Strategy Pattern.

1. **Question**: Explain Strategy Pattern.
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Strategy encapsulates interchangeable algorithms behind an interface so behavior can be selected or changed without conditional branches.
6. **Detailed explanation**: Strategy encapsulates interchangeable algorithms behind an interface so behavior can be selected or changed without conditional branches. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain Strategy Pattern.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Strategy encapsulates interchangeable algorithms behind an interface so behavior can be selected or changed without conditional branches.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 637. Explain Observer Pattern.

1. **Question**: Explain Observer Pattern.
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Observer publishes state changes to registered listeners. It is useful for events but needs lifecycle, ordering, and failure management.
6. **Detailed explanation**: Observer publishes state changes to registered listeners. It is useful for events but needs lifecycle, ordering, and failure management. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain Observer Pattern.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Observer publishes state changes to registered listeners. It is useful for events but needs lifecycle, ordering, and failure management.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 638. Explain Adapter Pattern.

1. **Question**: Explain Adapter Pattern.
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Adapter converts one interface into another expected by the client, isolating incompatible external or legacy APIs.
6. **Detailed explanation**: Adapter converts one interface into another expected by the client, isolating incompatible external or legacy APIs. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain Adapter Pattern.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Adapter converts one interface into another expected by the client, isolating incompatible external or legacy APIs.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 639. Explain Decorator Pattern.

1. **Question**: Explain Decorator Pattern.
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Decorator wraps an object to add behavior dynamically while preserving its interface, avoiding subclass combinations.
6. **Detailed explanation**: Decorator wraps an object to add behavior dynamically while preserving its interface, avoiding subclass combinations. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain Decorator Pattern.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Decorator wraps an object to add behavior dynamically while preserving its interface, avoiding subclass combinations.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 640. Explain Proxy Pattern.

1. **Question**: Explain Proxy Pattern.
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Proxy controls access to another object for concerns such as security, lazy loading, caching, remoting, or transactions.
6. **Detailed explanation**: Proxy controls access to another object for concerns such as security, lazy loading, caching, remoting, or transactions. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain Proxy Pattern.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Proxy controls access to another object for concerns such as security, lazy loading, caching, remoting, or transactions.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 641. Explain Template Method Pattern.

1. **Question**: Explain Template Method Pattern.
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Template Method defines an algorithm skeleton in a base class and lets subclasses customize selected steps.
6. **Detailed explanation**: Template Method defines an algorithm skeleton in a base class and lets subclasses customize selected steps. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain Template Method Pattern.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Template Method defines an algorithm skeleton in a base class and lets subclasses customize selected steps.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 642. Explain Chain of Responsibility.

1. **Question**: Explain Chain of Responsibility.
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Chain of Responsibility passes a request through handlers until one handles it or the chain ends.
6. **Detailed explanation**: Chain of Responsibility passes a request through handlers until one handles it or the chain ends. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain Chain of Responsibility.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Chain of Responsibility passes a request through handlers until one handles it or the chain ends.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 643. Explain Repository Pattern.

1. **Question**: Explain Repository Pattern.
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Repository abstracts persistence operations around an aggregate or domain model, keeping storage details outside business logic.
6. **Detailed explanation**: Repository abstracts persistence operations around an aggregate or domain model, keeping storage details outside business logic. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain Repository Pattern.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Repository abstracts persistence operations around an aggregate or domain model, keeping storage details outside business logic.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 644. Explain Dependency Injection Pattern.

1. **Question**: Explain Dependency Injection Pattern.
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Dependency Injection supplies collaborators from outside the class, reducing construction coupling and improving testability.
6. **Detailed explanation**: Dependency Injection supplies collaborators from outside the class, reducing construction coupling and improving testability. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain Dependency Injection Pattern.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Dependency Injection supplies collaborators from outside the class, reducing construction coupling and improving testability.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 645. Which patterns are used internally by Spring?

1. **Question**: Which patterns are used internally by Spring?
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Spring uses dependency injection, factory, proxy, template method, strategy, observer/event publisher, adapter, and repository patterns internally.
6. **Detailed explanation**: Spring uses dependency injection, factory, proxy, template method, strategy, observer/event publisher, adapter, and repository patterns internally. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Which patterns are used internally by Spring?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@Service
final class ExampleService {
    private final ExampleRepository repository;
    ExampleService(ExampleRepository repository) { this.repository = repository; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Spring uses dependency injection, factory, proxy, template method, strategy, observer/event publisher, adapter, and repository patterns internally.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 646. Which patterns have you used in your projects?

1. **Question**: Which patterns have you used in your projects?
2. **Difficulty**: Intermediate
3. **Topic**: Design Patterns
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Name patterns you actually used, the problem they solved, alternatives considered, and the measurable result.
6. **Detailed explanation**: Name patterns you actually used, the problem they solved, alternatives considered, and the measurable result. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Which patterns have you used in your projects?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Strategy { String apply(String input); }
final class Processor {
    private final Strategy strategy;
    Processor(Strategy strategy) { this.strategy = strategy; }
}
```




10. **Time & space complexity**: Report the concrete algorithm cost and any allocation, lookup, indirection, or synchronization overhead introduced.
11. **Real-world/project usage**: These patterns support Spring components, integrations, domain rules, object construction, and test seams.
12. **Common mistakes**: Applying a pattern mechanically, hiding simple logic behind abstractions, or creating global mutable state.
13. **Advantages**: Shared vocabulary, separation of responsibilities, extensibility, and easier testing when the fit is real.
14. **Limitations**: More types and indirection, learning cost, and accidental complexity when overused.
15. **Comparison with related concepts**: Compare the pattern with composition, inheritance, dependency injection, and simpler direct implementations.
16. **Production considerations**: Keep contracts clear, avoid unnecessary allocation or global state, test lifecycle and concurrency, and document ownership.
17. **Possible follow-up questions**: What changes when the number of implementations grows, state is shared, or calls are concurrent?
18. **Senior-level follow-up questions**: How would you evaluate whether the abstraction reduced coupling and how would you remove it safely if requirements changed?
19. **Scenario-based question**: A pattern-heavy module is difficult to change and debug. Explain how you would identify the actual problem and simplify it without breaking behavior.
20. **One-line revision note**: Name patterns you actually used, the problem they solved, alternatives considered, and the measurable result.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---
