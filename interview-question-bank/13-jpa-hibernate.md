# 13. JPA / Hibernate

> Source range: questions 319–348
## 319. What is ORM?

1. **Question**: What is ORM?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: ORM maps objects to relational tables and translates object operations into SQL while managing identity, relationships, and persistence state.
6. **Detailed explanation**: ORM maps objects to relational tables and translates object operations into SQL while managing identity, relationships, and persistence state. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is ORM?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: ORM maps objects to relational tables and translates object operations into SQL while managing identity, relationships, and persistence state.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 320. JPA vs Hibernate?

1. **Question**: JPA vs Hibernate?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: JPA is the standard API and specification; Hibernate is a popular implementation that adds provider-specific features.
6. **Detailed explanation**: JPA is the standard API and specification; Hibernate is a popular implementation that adds provider-specific features. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “JPA vs Hibernate?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: JPA is the standard API and specification; Hibernate is a popular implementation that adds provider-specific features.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 321. What is an Entity?

1. **Question**: What is an Entity?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: An entity is a persistent domain object identified by a stable primary key and managed by a persistence context.
6. **Detailed explanation**: An entity is a persistent domain object identified by a stable primary key and managed by a persistence context. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is an Entity?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: An entity is a persistent domain object identified by a stable primary key and managed by a persistence context.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 322. Entity lifecycle states?

1. **Question**: Entity lifecycle states?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: Entity states are transient, managed, detached, and removed. Operations and transaction boundaries move entities between these states.
6. **Detailed explanation**: Entity states are transient, managed, detached, and removed. Operations and transaction boundaries move entities between these states. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “Entity lifecycle states?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: Entity states are transient, managed, detached, and removed. Operations and transaction boundaries move entities between these states.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 323. `persist()` vs `merge()`?

1. **Question**: `persist()` vs `merge()`?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: persist makes a new entity managed. merge copies detached state into a managed instance and returns that managed instance; it does not reattach the original object.
6. **Detailed explanation**: persist makes a new entity managed. merge copies detached state into a managed instance and returns that managed instance; it does not reattach the original object. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “`persist()` vs `merge()`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: persist makes a new entity managed. merge copies detached state into a managed instance and returns that managed instance; it does not reattach the original object.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 324. `save()` vs `saveAndFlush()`?

1. **Question**: `save()` vs `saveAndFlush()`?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: save persists through a repository and may defer SQL. saveAndFlush forces the persistence context to synchronize with the database immediately, not necessarily commit.
6. **Detailed explanation**: save persists through a repository and may defer SQL. saveAndFlush forces the persistence context to synchronize with the database immediately, not necessarily commit. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “`save()` vs `saveAndFlush()`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: save persists through a repository and may defer SQL. saveAndFlush forces the persistence context to synchronize with the database immediately, not necessarily commit.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 325. What is dirty checking?

1. **Question**: What is dirty checking?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: Dirty checking compares managed entity state and generates updates at flush time without requiring an explicit update call.
6. **Detailed explanation**: Dirty checking compares managed entity state and generates updates at flush time without requiring an explicit update call. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is dirty checking?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: Dirty checking compares managed entity state and generates updates at flush time without requiring an explicit update call.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 326. What is first-level cache?

1. **Question**: What is first-level cache?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: The first-level cache is the persistence context, scoped normally to a transaction/session, ensuring one managed instance per identity.
6. **Detailed explanation**: The first-level cache is the persistence context, scoped normally to a transaction/session, ensuring one managed instance per identity. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is first-level cache?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: The first-level cache is the persistence context, scoped normally to a transaction/session, ensuring one managed instance per identity.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 327. What is second-level cache?

1. **Question**: What is second-level cache?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: The second-level cache is shared across sessions and must be configured carefully for consistency and useful read patterns.
6. **Detailed explanation**: The second-level cache is shared across sessions and must be configured carefully for consistency and useful read patterns. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is second-level cache?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: The second-level cache is shared across sessions and must be configured carefully for consistency and useful read patterns.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 328. Lazy vs eager loading?

1. **Question**: Lazy vs eager loading?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: Lazy loading fetches associations when accessed; eager loading fetches them immediately. Lazy is usually safer for large graphs but requires an open context or explicit fetch.
6. **Detailed explanation**: Lazy loading fetches associations when accessed; eager loading fetches them immediately. Lazy is usually safer for large graphs but requires an open context or explicit fetch. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “Lazy vs eager loading?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: Lazy loading fetches associations when accessed; eager loading fetches them immediately. Lazy is usually safer for large graphs but requires an open context or explicit fetch.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 329. What is the N+1 query problem?

1. **Question**: What is the N+1 query problem?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: N+1 issues occur when one query loads parents and then one query per parent loads children, causing excessive round trips.
6. **Detailed explanation**: N+1 issues occur when one query loads parents and then one query per parent loads children, causing excessive round trips. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is the N+1 query problem?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: N+1 issues occur when one query loads parents and then one query per parent loads children, causing excessive round trips.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 330. How do you solve N+1?

1. **Question**: How do you solve N+1?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: Use fetch joins, entity graphs, batch fetching, projections, or carefully designed queries to load the required data in predictable SQL.
6. **Detailed explanation**: Use fetch joins, entity graphs, batch fetching, projections, or carefully designed queries to load the required data in predictable SQL. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “How do you solve N+1?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: Use fetch joins, entity graphs, batch fetching, projections, or carefully designed queries to load the required data in predictable SQL.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 331. What is JOIN FETCH?

1. **Question**: What is JOIN FETCH?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: JOIN FETCH loads an association in the same JPQL query and avoids lazy round trips, but pagination over collection fetch joins needs care.
6. **Detailed explanation**: JOIN FETCH loads an association in the same JPQL query and avoids lazy round trips, but pagination over collection fetch joins needs care. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is JOIN FETCH?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: JOIN FETCH loads an association in the same JPQL query and avoids lazy round trips, but pagination over collection fetch joins needs care.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 332. What is EntityGraph?

1. **Question**: What is EntityGraph?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: EntityGraph declares which attributes to fetch for a repository query without hard-coding every query variant.
6. **Detailed explanation**: EntityGraph declares which attributes to fetch for a repository query without hard-coding every query variant. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is EntityGraph?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: EntityGraph declares which attributes to fetch for a repository query without hard-coding every query variant.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 333. What is cascade?

1. **Question**: What is cascade?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: Cascade propagates persistence operations such as persist, merge, or remove from a parent to associated entities.
6. **Detailed explanation**: Cascade propagates persistence operations such as persist, merge, or remove from a parent to associated entities. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is cascade?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: Cascade propagates persistence operations such as persist, merge, or remove from a parent to associated entities.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 334. What is orphanRemoval?

1. **Question**: What is orphanRemoval?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: orphanRemoval deletes a child removed from an owned relationship; use it only when the child lifecycle truly belongs to the parent.
6. **Detailed explanation**: orphanRemoval deletes a child removed from an owned relationship; use it only when the child lifecycle truly belongs to the parent. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is orphanRemoval?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: orphanRemoval deletes a child removed from an owned relationship; use it only when the child lifecycle truly belongs to the parent.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 335. OneToOne, OneToMany, ManyToOne, ManyToMany?

1. **Question**: OneToOne, OneToMany, ManyToOne, ManyToMany?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: Relationship annotations model cardinality. Choose ownership and cascade based on aggregate boundaries and database foreign keys.
6. **Detailed explanation**: Relationship annotations model cardinality. Choose ownership and cascade based on aggregate boundaries and database foreign keys. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “OneToOne, OneToMany, ManyToOne, ManyToMany?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: Relationship annotations model cardinality. Choose ownership and cascade based on aggregate boundaries and database foreign keys.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 336. Owning side vs inverse side?

1. **Question**: Owning side vs inverse side?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: The owning side writes the foreign-key relationship. The inverse side uses mappedBy and does not own the update.
6. **Detailed explanation**: The owning side writes the foreign-key relationship. The inverse side uses mappedBy and does not own the update. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “Owning side vs inverse side?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: The owning side writes the foreign-key relationship. The inverse side uses mappedBy and does not own the update.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 337. What is `mappedBy`?

1. **Question**: What is `mappedBy`?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: mappedBy identifies the field on the owning entity and prevents JPA from creating a second relationship mapping.
6. **Detailed explanation**: mappedBy identifies the field on the owning entity and prevents JPA from creating a second relationship mapping. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is `mappedBy`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: mappedBy identifies the field on the owning entity and prevents JPA from creating a second relationship mapping.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 338. JPQL vs native query?

1. **Question**: JPQL vs native query?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: JPQL queries entities and attributes independent of table names. Native SQL uses database-specific syntax and is useful for advanced or performance-critical queries.
6. **Detailed explanation**: JPQL queries entities and attributes independent of table names. Native SQL uses database-specific syntax and is useful for advanced or performance-critical queries. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “JPQL vs native query?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: JPQL queries entities and attributes independent of table names. Native SQL uses database-specific syntax and is useful for advanced or performance-critical queries.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 339. What is Criteria API?

1. **Question**: What is Criteria API?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: Criteria API builds type-safe or dynamic queries programmatically, but can be verbose; specifications or query builders may be clearer.
6. **Detailed explanation**: Criteria API builds type-safe or dynamic queries programmatically, but can be verbose; specifications or query builders may be clearer. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is Criteria API?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: Criteria API builds type-safe or dynamic queries programmatically, but can be verbose; specifications or query builders may be clearer.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 340. What is optimistic locking?

1. **Question**: What is optimistic locking?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: Optimistic locking assumes conflicts are rare and detects them at update using a version value.
6. **Detailed explanation**: Optimistic locking assumes conflicts are rare and detects them at update using a version value. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is optimistic locking?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (ExecutorService executor = Executors.newFixedThreadPool(2)) {
    Future<Integer> result = executor.submit(() -> 42);
    System.out.println(result.get(1, TimeUnit.SECONDS));
}
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: Optimistic locking assumes conflicts are rare and detects them at update using a version value.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 341. What is pessimistic locking?

1. **Question**: What is pessimistic locking?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: Pessimistic locking obtains a database lock during the transaction to prevent conflicting access, reducing concurrency but protecting critical updates.
6. **Detailed explanation**: Pessimistic locking obtains a database lock during the transaction to prevent conflicting access, reducing concurrency but protecting critical updates. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is pessimistic locking?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (ExecutorService executor = Executors.newFixedThreadPool(2)) {
    Future<Integer> result = executor.submit(() -> 42);
    System.out.println(result.get(1, TimeUnit.SECONDS));
}
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: Pessimistic locking obtains a database lock during the transaction to prevent conflicting access, reducing concurrency but protecting critical updates.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 342. What does `@Version` do?

1. **Question**: What does `@Version` do?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: @Version adds a version column; an update succeeds only if the version is unchanged, otherwise an optimistic-lock exception is raised.
6. **Detailed explanation**: @Version adds a version column; an update succeeds only if the version is unchanged, otherwise an optimistic-lock exception is raised. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What does `@Version` do?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: @Version adds a version column; an update succeeds only if the version is unchanged, otherwise an optimistic-lock exception is raised.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 343. What happens when two users update the same record?

1. **Question**: What happens when two users update the same record?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: With optimistic locking, one update succeeds and the other fails with a conflict; the application can retry or report the conflict.
6. **Detailed explanation**: With optimistic locking, one update succeeds and the other fails with a conflict; the application can retry or report the conflict. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What happens when two users update the same record?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
var result = List.of(1, 2, 3).stream()
    .filter(n -> n > 1)
    .map(n -> n * 2)
    .toList();
System.out.println(result);
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: With optimistic locking, one update succeeds and the other fails with a conflict; the application can retry or report the conflict.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 344. How do you implement pagination with JPA?

1. **Question**: How do you implement pagination with JPA?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: Use Spring Data Pageable or keyset/cursor queries with stable ordering, and ensure the count and fetch queries are appropriate for the data size.
6. **Detailed explanation**: Use Spring Data Pageable or keyset/cursor queries with stable ordering, and ensure the count and fetch queries are appropriate for the data size. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “How do you implement pagination with JPA?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: Use Spring Data Pageable or keyset/cursor queries with stable ordering, and ensure the count and fetch queries are appropriate for the data size.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 345. Why can `LazyInitializationException` occur?

1. **Question**: Why can `LazyInitializationException` occur?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: LazyInitializationException occurs when a lazy association is accessed after the persistence context has closed.
6. **Detailed explanation**: LazyInitializationException occurs when a lazy association is accessed after the persistence context has closed. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “Why can `LazyInitializationException` occur?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: LazyInitializationException occurs when a lazy association is accessed after the persistence context has closed.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 346. What is Open Session in View?

1. **Question**: What is Open Session in View?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: Open Session in View keeps a persistence context open through web rendering; it can hide query problems and cause database access outside service boundaries.
6. **Detailed explanation**: Open Session in View keeps a persistence context open through web rendering; it can hide query problems and cause database access outside service boundaries. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “What is Open Session in View?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: Open Session in View keeps a persistence context open through web rendering; it can hide query problems and cause database access outside service boundaries.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 347. Why can `EAGER` fetching cause performance problems?

1. **Question**: Why can `EAGER` fetching cause performance problems?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: EAGER relationships can load large graphs unexpectedly, create joins or extra queries, and make every use case pay the fetch cost.
6. **Detailed explanation**: EAGER relationships can load large graphs unexpectedly, create joins or extra queries, and make every use case pay the fetch cost. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “Why can `EAGER` fetching cause performance problems?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: EAGER relationships can load large graphs unexpectedly, create joins or extra queries, and make every use case pay the fetch cost.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---

## 348. How would you optimize Hibernate performance?

1. **Question**: How would you optimize Hibernate performance?
2. **Difficulty**: Advanced
3. **Topic**: JPA → Hibernate
4. **What interviewer is testing**: Whether you can choose and operate the design safely under failure, scale, and change.
5. **Short interview answer (30–60 seconds)**: Measure SQL and allocations, eliminate N+1, select only needed columns, batch writes, tune fetch sizes, use indexes, and keep transactions short.
6. **Detailed explanation**: Measure SQL and allocations, eliminate N+1, select only needed columns, batch writes, tune fetch sizes, use indexes, and keep transactions short. The trade-off and failure mode determine the boundary where this pattern is appropriate.
7. **How it works internally**: Requests, messages, transactions, retries, and state transitions are coordinated by the participating services, brokers, databases, and resilience components.
8. **Example**:

For “How would you optimize Hibernate performance?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include network calls, serialization, queueing, storage, retries, and recovery work in addition to local algorithmic cost.
11. **Real-world/project usage**: This governs service boundaries, asynchronous workflows, transactions, deployment, observability, and recovery.
12. **Common mistakes**: Unbounded retries, missing timeouts, shared databases, non-idempotent consumers, and assuming distributed operations are atomic.
13. **Advantages**: Independent scaling and deployment, fault isolation, and domain-focused ownership when boundaries are well chosen.
14. **Limitations**: Operational complexity, latency, eventual consistency, distributed debugging, and more failure modes.
15. **Comparison with related concepts**: Compare synchronous/asynchronous calls, choreography/orchestration, retries/circuit breakers, and monolith/service boundaries.
16. **Production considerations**: Add timeouts, bounded retries, idempotency, tracing, metrics, runbooks, schema compatibility, and tested rollback paths.
17. **Possible follow-up questions**: What happens when a dependency is slow, unavailable, duplicated, or partially successful?
18. **Senior-level follow-up questions**: How would you set SLOs, choose consistency, migrate safely, and prove recovery behavior?
19. **Scenario-based question**: A dependency fails during a multi-step business operation. Explain containment, compensation, observability, and reconciliation.
20. **One-line revision note**: Measure SQL and allocations, eliminate N+1, select only needed columns, batch writes, tune fetch sizes, use indexes, and keep transactions short.
21. **Image visuals (if required)**: A service topology, sequence, saga, or failure-state diagram is useful.

---
