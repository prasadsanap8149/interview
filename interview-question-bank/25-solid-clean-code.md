# 25. SOLID & Clean Code

> Source range: questions 647–662
## 647. Explain SRP.

1. **Question**: Explain SRP.
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: SRP says a class or module should have one reason to change, which keeps responsibilities cohesive.
6. **Detailed explanation**: SRP says a class or module should have one reason to change, which keeps responsibilities cohesive. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain SRP.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: SRP says a class or module should have one reason to change, which keeps responsibilities cohesive.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 648. Explain OCP.

1. **Question**: Explain OCP.
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: OCP says software should be open for extension but closed for modification through stable abstractions and composition.
6. **Detailed explanation**: OCP says software should be open for extension but closed for modification through stable abstractions and composition. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain OCP.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: OCP says software should be open for extension but closed for modification through stable abstractions and composition.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 649. Explain LSP.

1. **Question**: Explain LSP.
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: LSP says subtypes must be usable wherever the base type is expected without weakening its behavioral contract.
6. **Detailed explanation**: LSP says subtypes must be usable wherever the base type is expected without weakening its behavioral contract. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain LSP.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: LSP says subtypes must be usable wherever the base type is expected without weakening its behavioral contract.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 650. Explain ISP.

1. **Question**: Explain ISP.
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: ISP says clients should not depend on methods they do not use; prefer focused interfaces over large ones.
6. **Detailed explanation**: ISP says clients should not depend on methods they do not use; prefer focused interfaces over large ones. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain ISP.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: ISP says clients should not depend on methods they do not use; prefer focused interfaces over large ones.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 651. Explain DIP.

1. **Question**: Explain DIP.
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: DIP says high-level policy and low-level details should depend on abstractions, with dependencies supplied from outside.
6. **Detailed explanation**: DIP says high-level policy and low-level details should depend on abstractions, with dependencies supplied from outside. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Explain DIP.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: DIP says high-level policy and low-level details should depend on abstractions, with dependencies supplied from outside.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 652. What is clean code?

1. **Question**: What is clean code?
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Clean code is readable, intention-revealing, cohesive, testable, and simple enough that changes are localized.
6. **Detailed explanation**: Clean code is readable, intention-revealing, cohesive, testable, and simple enough that changes are localized. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “What is clean code?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Clean code is readable, intention-revealing, cohesive, testable, and simple enough that changes are localized.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 653. What are code smells?

1. **Question**: What are code smells?
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Code smells are symptoms such as duplication, long methods, god classes, feature envy, hidden coupling, or excessive conditionals that suggest design debt.
6. **Detailed explanation**: Code smells are symptoms such as duplication, long methods, god classes, feature envy, hidden coupling, or excessive conditionals that suggest design debt. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “What are code smells?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Code smells are symptoms such as duplication, long methods, god classes, feature envy, hidden coupling, or excessive conditionals that suggest design debt.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 654. What is technical debt?

1. **Question**: What is technical debt?
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Technical debt is the future cost created by shortcuts, outdated design, or deferred quality work; it should be tracked and prioritized by risk.
6. **Detailed explanation**: Technical debt is the future cost created by shortcuts, outdated design, or deferred quality work; it should be tracked and prioritized by risk. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “What is technical debt?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Technical debt is the future cost created by shortcuts, outdated design, or deferred quality work; it should be tracked and prioritized by risk.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 655. How do you refactor legacy code safely?

1. **Question**: How do you refactor legacy code safely?
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Refactor safely by adding characterization tests, making small changes, preserving behavior, reviewing diffs, and measuring production impact.
6. **Detailed explanation**: Refactor safely by adding characterization tests, making small changes, preserving behavior, reviewing diffs, and measuring production impact. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “How do you refactor legacy code safely?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Refactor safely by adding characterization tests, making small changes, preserving behavior, reviewing diffs, and measuring production impact.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 656. How do you avoid duplicate code?

1. **Question**: How do you avoid duplicate code?
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Avoid duplication by extracting stable shared behavior at the right abstraction level; do not force unrelated code into a premature utility.
6. **Detailed explanation**: Avoid duplication by extracting stable shared behavior at the right abstraction level; do not force unrelated code into a premature utility. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “How do you avoid duplicate code?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Avoid duplication by extracting stable shared behavior at the right abstraction level; do not force unrelated code into a premature utility.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 657. What is separation of concerns?

1. **Question**: What is separation of concerns?
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Separation of concerns assigns distinct responsibilities to layers or modules so changes in one concern do not ripple through others.
6. **Detailed explanation**: Separation of concerns assigns distinct responsibilities to layers or modules so changes in one concern do not ripple through others. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “What is separation of concerns?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Separation of concerns assigns distinct responsibilities to layers or modules so changes in one concern do not ripple through others.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 658. What is high cohesion and low coupling?

1. **Question**: What is high cohesion and low coupling?
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: High cohesion keeps related responsibilities together; low coupling minimizes knowledge and dependency between modules.
6. **Detailed explanation**: High cohesion keeps related responsibilities together; low coupling minimizes knowledge and dependency between modules. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “What is high cohesion and low coupling?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: High cohesion keeps related responsibilities together; low coupling minimizes knowledge and dependency between modules.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 659. How do you structure a large Spring Boot project?

1. **Question**: How do you structure a large Spring Boot project?
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Structure a large Spring Boot project by business capability or bounded context, with clear API, application, domain, infrastructure, and test boundaries.
6. **Detailed explanation**: Structure a large Spring Boot project by business capability or bounded context, with clear API, application, domain, infrastructure, and test boundaries. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “How do you structure a large Spring Boot project?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Structure a large Spring Boot project by business capability or bounded context, with clear API, application, domain, infrastructure, and test boundaries.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 660. DTO vs Entity?

1. **Question**: DTO vs Entity?
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: DTOs define API contracts and can be shaped for clients; entities represent persistence state and lifecycle. Map between them explicitly.
6. **Detailed explanation**: DTOs define API contracts and can be shaped for clients; entities represent persistence state and lifecycle. Map between them explicitly. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “DTO vs Entity?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: DTOs define API contracts and can be shaped for clients; entities represent persistence state and lifecycle. Map between them explicitly.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 661. Why shouldn't entities generally be exposed directly through APIs?

1. **Question**: Why shouldn't entities generally be exposed directly through APIs?
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Exposing entities couples APIs to schema and lazy relationships, leaks internal fields, and makes serialization and security behavior unpredictable.
6. **Detailed explanation**: Exposing entities couples APIs to schema and lazy relationships, leaks internal fields, and makes serialization and security behavior unpredictable. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Why shouldn't entities generally be exposed directly through APIs?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Exposing entities couples APIs to schema and lazy relationships, leaks internal fields, and makes serialization and security behavior unpredictable.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---

## 662. Where should business logic reside?

1. **Question**: Where should business logic reside?
2. **Difficulty**: Intermediate
3. **Topic**: SOLID & Clean Code
4. **What interviewer is testing**: Whether you can recognize a design problem, choose a proportionate solution, and explain its trade-offs.
5. **Short interview answer (30–60 seconds)**: Business rules belong in domain or application services, close to the data and invariants they govern, rather than controllers or repositories.
6. **Detailed explanation**: Business rules belong in domain or application services, close to the data and invariants they govern, rather than controllers or repositories. Explain participants, collaboration, lifecycle, and when the pattern becomes harmful.
7. **How it works internally**: Objects, interfaces, factories, decorators, proxies, or templates collaborate according to the pattern’s structure while preserving the required contract.
8. **Example**:

For “Where should business logic reside?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Business rules belong in domain or application services, close to the data and invariants they govern, rather than controllers or repositories.
21. **Image visuals (if required)**: A UML collaboration diagram is useful for pattern structure.

---
