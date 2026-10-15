# 11. REST API & Backend Design

> Source range: questions 261–286
## 261. What is REST?

1. **Question**: What is REST?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: REST is an architectural style that models resources and uses a uniform, stateless HTTP interface to manipulate representations.
6. **Detailed explanation**: REST is an architectural style that models resources and uses a uniform, stateless HTTP interface to manipulate representations. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “What is REST?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: REST is an architectural style that models resources and uses a uniform, stateless HTTP interface to manipulate representations.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 262. What are REST principles?

1. **Question**: What are REST principles?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: REST emphasizes client-server separation, stateless requests, cacheable responses, a uniform interface, layered systems, and optional code-on-demand.
6. **Detailed explanation**: REST emphasizes client-server separation, stateless requests, cacheable responses, a uniform interface, layered systems, and optional code-on-demand. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “What are REST principles?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: REST emphasizes client-server separation, stateless requests, cacheable responses, a uniform interface, layered systems, and optional code-on-demand.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 263. GET vs POST vs PUT vs PATCH vs DELETE?

1. **Question**: GET vs POST vs PUT vs PATCH vs DELETE?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: GET reads, POST creates or triggers non-idempotent processing, PUT replaces a resource, PATCH partially updates it, and DELETE removes it.
6. **Detailed explanation**: GET reads, POST creates or triggers non-idempotent processing, PUT replaces a resource, PATCH partially updates it, and DELETE removes it. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “GET vs POST vs PUT vs PATCH vs DELETE?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: GET reads, POST creates or triggers non-idempotent processing, PUT replaces a resource, PATCH partially updates it, and DELETE removes it.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 264. PUT vs PATCH?

1. **Question**: PUT vs PATCH?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: PUT supplies a complete replacement and is idempotent by contract. PATCH applies partial changes and may be idempotent depending on the operation.
6. **Detailed explanation**: PUT supplies a complete replacement and is idempotent by contract. PATCH applies partial changes and may be idempotent depending on the operation. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “PUT vs PATCH?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: PUT supplies a complete replacement and is idempotent by contract. PATCH applies partial changes and may be idempotent depending on the operation.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 265. What is idempotency?

1. **Question**: What is idempotency?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: An operation is idempotent when repeating the same request has the same intended effect as sending it once, even if responses differ.
6. **Detailed explanation**: An operation is idempotent when repeating the same request has the same intended effect as sending it once, even if responses differ. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “What is idempotency?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: An operation is idempotent when repeating the same request has the same intended effect as sending it once, even if responses differ.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 266. Which HTTP methods are idempotent?

1. **Question**: Which HTTP methods are idempotent?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: GET, HEAD, PUT, DELETE, OPTIONS, and TRACE are defined as idempotent; POST is not inherently idempotent.
6. **Detailed explanation**: GET, HEAD, PUT, DELETE, OPTIONS, and TRACE are defined as idempotent; POST is not inherently idempotent. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “Which HTTP methods are idempotent?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: GET, HEAD, PUT, DELETE, OPTIONS, and TRACE are defined as idempotent; POST is not inherently idempotent.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 267. What HTTP status codes do you commonly use?

1. **Question**: What HTTP status codes do you commonly use?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: Use 200 for success, 201 for creation, 202 for accepted asynchronous work, 204 for success without a body, 400 for malformed input, 401 for missing/invalid authentication, 403 for denied access, 404 for missing resources, 409 for conflicts, 422 for semantically invalid input, and 5xx for server failures.
6. **Detailed explanation**: Use 200 for success, 201 for creation, 202 for accepted asynchronous work, 204 for success without a body, 400 for malformed input, 401 for missing/invalid authentication, 403 for denied access, 404 for missing resources, 409 for conflicts, 422 for semantically invalid input, and 5xx for server failures. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “What HTTP status codes do you commonly use?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: Use 200 for success, 201 for creation, 202 for accepted asynchronous work, 204 for success without a body, 400 for malformed input, 401 for missing/invalid authentication, 403 for denied access, 404 for missing resources, 409 for conflicts, 422 for semantically invalid input, and 5xx for server failures.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 268. 401 vs 403?

1. **Question**: 401 vs 403?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: 401 means authentication is missing or invalid; 403 means the caller is authenticated but lacks permission.
6. **Detailed explanation**: 401 means authentication is missing or invalid; 403 means the caller is authenticated but lacks permission. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “401 vs 403?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: 401 means authentication is missing or invalid; 403 means the caller is authenticated but lacks permission.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 269. 400 vs 422?

1. **Question**: 400 vs 422?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: 400 means the request is malformed or cannot be parsed. 422 means it is syntactically valid but fails semantic or domain validation.
6. **Detailed explanation**: 400 means the request is malformed or cannot be parsed. 422 means it is syntactically valid but fails semantic or domain validation. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “400 vs 422?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: 400 means the request is malformed or cannot be parsed. 422 means it is syntactically valid but fails semantic or domain validation.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 270. 200 vs 201 vs 202?

1. **Question**: 200 vs 201 vs 202?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: 200 means completed successfully, 201 means a resource was created, and 202 means processing was accepted for later completion.
6. **Detailed explanation**: 200 means completed successfully, 201 means a resource was created, and 202 means processing was accepted for later completion. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “200 vs 201 vs 202?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: 200 means completed successfully, 201 means a resource was created, and 202 means processing was accepted for later completion.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 271. How do you version REST APIs?

1. **Question**: How do you version REST APIs?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: Version through a stable URI, media type, or header strategy. Prefer additive, backward-compatible evolution and publish deprecation timelines.
6. **Detailed explanation**: Version through a stable URI, media type, or header strategy. Prefer additive, backward-compatible evolution and publish deprecation timelines. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “How do you version REST APIs?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: Version through a stable URI, media type, or header strategy. Prefer additive, backward-compatible evolution and publish deprecation timelines.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 272. How do you design pagination?

1. **Question**: How do you design pagination?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: Define stable ordering, bounded page size, filters, sort allowlists, and metadata. Use cursor pagination for large or changing datasets.
6. **Detailed explanation**: Define stable ordering, bounded page size, filters, sort allowlists, and metadata. Use cursor pagination for large or changing datasets. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “How do you design pagination?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: Define stable ordering, bounded page size, filters, sort allowlists, and metadata. Use cursor pagination for large or changing datasets.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 273. Offset pagination vs cursor pagination?

1. **Question**: Offset pagination vs cursor pagination?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: Offset pagination is simple but slows and shifts under changes. Cursor pagination is stable and efficient for large ordered datasets but less flexible to jump to arbitrary pages.
6. **Detailed explanation**: Offset pagination is simple but slows and shifts under changes. Cursor pagination is stable and efficient for large ordered datasets but less flexible to jump to arbitrary pages. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “Offset pagination vs cursor pagination?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: Offset pagination is simple but slows and shifts under changes. Cursor pagination is stable and efficient for large ordered datasets but less flexible to jump to arbitrary pages.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 274. How do you design filtering and sorting?

1. **Question**: How do you design filtering and sorting?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: Use explicit filter syntax, allowlisted sortable fields and directions, validated values, and documented defaults and limits.
6. **Detailed explanation**: Use explicit filter syntax, allowlisted sortable fields and directions, validated values, and documented defaults and limits. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “How do you design filtering and sorting?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: Use explicit filter syntax, allowlisted sortable fields and directions, validated values, and documented defaults and limits.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 275. How do you maintain backward compatibility?

1. **Question**: How do you maintain backward compatibility?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: Add fields rather than changing meaning, tolerate unknown fields where safe, version breaking changes, and contract-test consumers.
6. **Detailed explanation**: Add fields rather than changing meaning, tolerate unknown fields where safe, version breaking changes, and contract-test consumers. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “How do you maintain backward compatibility?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: Add fields rather than changing meaning, tolerate unknown fields where safe, version breaking changes, and contract-test consumers.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 276. How do you design idempotent POST/payment APIs?

1. **Question**: How do you design idempotent POST/payment APIs?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: Require an idempotency key, persist request/result state atomically, return the original result for retries, and enforce uniqueness at the database boundary.
6. **Detailed explanation**: Require an idempotency key, persist request/result state atomically, return the original result for retries, and enforce uniqueness at the database boundary. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “How do you design idempotent POST/payment APIs?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: Require an idempotency key, persist request/result state atomically, return the original result for retries, and enforce uniqueness at the database boundary.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 277. How do you handle duplicate requests?

1. **Question**: How do you handle duplicate requests?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: Use idempotency keys, unique constraints, deduplication records, and transactional state transitions; do not rely only on client behavior.
6. **Detailed explanation**: Use idempotency keys, unique constraints, deduplication records, and transactional state transitions; do not rely only on client behavior. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “How do you handle duplicate requests?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: Use idempotency keys, unique constraints, deduplication records, and transactional state transitions; do not rely only on client behavior.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 278. How do you implement rate limiting?

1. **Question**: How do you implement rate limiting?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: Apply a token bucket, leaky bucket, or sliding-window limit at the gateway or service, keyed by identity and endpoint with clear retry responses.
6. **Detailed explanation**: Apply a token bucket, leaky bucket, or sliding-window limit at the gateway or service, keyed by identity and endpoint with clear retry responses. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “How do you implement rate limiting?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: Apply a token bucket, leaky bucket, or sliding-window limit at the gateway or service, keyed by identity and endpoint with clear retry responses.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 279. How do you handle large API responses?

1. **Question**: How do you handle large API responses?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: Paginate, filter, compress, stream, select fields, and avoid loading unbounded result sets into memory.
6. **Detailed explanation**: Paginate, filter, compress, stream, select fields, and avoid loading unbounded result sets into memory. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “How do you handle large API responses?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: Paginate, filter, compress, stream, select fields, and avoid loading unbounded result sets into memory.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 280. How do you secure public APIs?

1. **Question**: How do you secure public APIs?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: Use TLS, authentication, authorization, validation, rate limiting, safe errors, logging, dependency security, and abuse monitoring.
6. **Detailed explanation**: Use TLS, authentication, authorization, validation, rate limiting, safe errors, logging, dependency security, and abuse monitoring. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “How do you secure public APIs?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: Use TLS, authentication, authorization, validation, rate limiting, safe errors, logging, dependency security, and abuse monitoring.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 281. What is API Gateway?

1. **Question**: What is API Gateway?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: An API Gateway is an edge service that routes requests and commonly handles TLS, authentication, rate limits, transformations, and observability.
6. **Detailed explanation**: An API Gateway is an edge service that routes requests and commonly handles TLS, authentication, rate limits, transformations, and observability. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “What is API Gateway?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: An API Gateway is an edge service that routes requests and commonly handles TLS, authentication, rate limits, transformations, and observability.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 282. What is correlation ID?

1. **Question**: What is correlation ID?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: A correlation ID identifies a request across logs and services so operators can trace one user operation.
6. **Detailed explanation**: A correlation ID identifies a request across logs and services so operators can trace one user operation. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “What is correlation ID?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: A correlation ID identifies a request across logs and services so operators can trace one user operation.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 283. How do you implement distributed request tracing?

1. **Question**: How do you implement distributed request tracing?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: Propagate trace context such as W3C Trace Context, create spans for service and database calls, and export them to a tracing backend.
6. **Detailed explanation**: Propagate trace context such as W3C Trace Context, create spans for service and database calls, and export them to a tracing backend. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “How do you implement distributed request tracing?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: Propagate trace context such as W3C Trace Context, create spans for service and database calls, and export them to a tracing backend.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 284. REST vs SOAP?

1. **Question**: REST vs SOAP?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: REST uses HTTP resources and representations. SOAP is a stricter XML protocol with formal contracts and enterprise standards such as WS-Security.
6. **Detailed explanation**: REST uses HTTP resources and representations. SOAP is a stricter XML protocol with formal contracts and enterprise standards such as WS-Security. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “REST vs SOAP?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: REST uses HTTP resources and representations. SOAP is a stricter XML protocol with formal contracts and enterprise standards such as WS-Security.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 285. REST vs GraphQL?

1. **Question**: REST vs GraphQL?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: REST exposes resource-oriented endpoints; GraphQL exposes a typed query schema where clients select fields, reducing over-fetching but adding query governance.
6. **Detailed explanation**: REST exposes resource-oriented endpoints; GraphQL exposes a typed query schema where clients select fields, reducing over-fetching but adding query governance. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “REST vs GraphQL?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: REST exposes resource-oriented endpoints; GraphQL exposes a typed query schema where clients select fields, reducing over-fetching but adding query governance.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---

## 286. REST vs gRPC?

1. **Question**: REST vs gRPC?
2. **Difficulty**: Advanced
3. **Topic**: REST API & Backend Design
4. **What interviewer is testing**: Whether you can design clear HTTP contracts that remain correct under retries, scale, failures, and client evolution.
5. **Short interview answer (30–60 seconds)**: REST is broadly interoperable over HTTP; gRPC uses HTTP/2 and Protocol Buffers for efficient typed service-to-service calls and streaming.
6. **Detailed explanation**: REST is broadly interoperable over HTTP; gRPC uses HTTP/2 and Protocol Buffers for efficient typed service-to-service calls and streaming. The contract is defined by its request, response, status code, validation, and compatibility behavior.
7. **How it works internally**: The server parses the request, authenticates it, validates it, applies business logic and persistence, then serializes a response with headers and status.
8. **Example**:

For “REST vs gRPC?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
@GetMapping("/items/{id}")
ResponseEntity<String> get(@PathVariable UUID id) { return ResponseEntity.ok(id.toString()); }
```




10. **Time & space complexity**: Include serialization, validation, database, network, and pagination costs; avoid claiming endpoint complexity without analyzing its data access.
11. **Real-world/project usage**: These rules govern public APIs, internal services, gateways, clients, and operational tooling.
12. **Common mistakes**: Ambiguous status codes, leaking internals, unbounded responses, unstable ordering, missing idempotency, and breaking clients with silent contract changes.
13. **Advantages**: Familiar HTTP semantics, broad tooling, cacheability, observability, and independent client/server evolution.
14. **Limitations**: Network failure, versioning burden, over/under-fetching, and the need for explicit consistency and retry design.
15. **Comparison with related concepts**: Compare HTTP methods, offset/cursor pagination, REST/GraphQL/gRPC, and gateway/service responsibilities.
16. **Production considerations**: Define contracts, validate and rate-limit requests, propagate correlation and trace IDs, secure data, and monitor latency and errors.
17. **Possible follow-up questions**: How do retries, duplicate requests, partial updates, large responses, and client compatibility behave?
18. **Senior-level follow-up questions**: How would you evolve the contract, set SLOs, introduce a gateway, or migrate clients without downtime?
19. **Scenario-based question**: A client retries a slow request and creates duplicate work. Explain how you would diagnose, make the operation idempotent, and communicate the contract.
20. **One-line revision note**: REST is broadly interoperable over HTTP; gRPC uses HTTP/2 and Protocol Buffers for efficient typed service-to-service calls and streaming.
21. **Image visuals (if required)**: A request lifecycle, pagination, or distributed tracing diagram may clarify the design.

---
