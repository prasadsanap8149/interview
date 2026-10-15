# 23. Testing

> Source range: questions 605–627
## 605. Unit testing vs integration testing?

1. **Question**: Unit testing vs integration testing?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Unit tests isolate a small unit; integration tests verify collaboration with real or realistic infrastructure.
6. **Detailed explanation**: Unit tests isolate a small unit; integration tests verify collaboration with real or realistic infrastructure. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “Unit testing vs integration testing?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Unit tests isolate a small unit; integration tests verify collaboration with real or realistic infrastructure.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 606. What is JUnit?

1. **Question**: What is JUnit?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: JUnit is the Java testing framework providing test discovery, assertions, lifecycle, parameterization, and extensions.
6. **Detailed explanation**: JUnit is the Java testing framework providing test discovery, assertions, lifecycle, parameterization, and extensions. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What is JUnit?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: JUnit is the Java testing framework providing test discovery, assertions, lifecycle, parameterization, and extensions.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 607. JUnit 4 vs JUnit 5?

1. **Question**: JUnit 4 vs JUnit 5?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: JUnit 5 uses the Jupiter programming model and platform with modern extensions and parameterized tests; JUnit 4 uses the older runner/rule model.
6. **Detailed explanation**: JUnit 5 uses the Jupiter programming model and platform with modern extensions and parameterized tests; JUnit 4 uses the older runner/rule model. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “JUnit 4 vs JUnit 5?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: JUnit 5 uses the Jupiter programming model and platform with modern extensions and parameterized tests; JUnit 4 uses the older runner/rule model.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 608. What is Mockito?

1. **Question**: What is Mockito?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Mockito creates test doubles and verifies interactions so a unit can be tested without real dependencies.
6. **Detailed explanation**: Mockito creates test doubles and verifies interactions so a unit can be tested without real dependencies. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What is Mockito?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Mockito creates test doubles and verifies interactions so a unit can be tested without real dependencies.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 609. Mock vs Spy?

1. **Question**: Mock vs Spy?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: A mock is a configurable fake whose interactions can be verified. A spy wraps a real object and selectively stubs behavior.
6. **Detailed explanation**: A mock is a configurable fake whose interactions can be verified. A spy wraps a real object and selectively stubs behavior. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “Mock vs Spy?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: A mock is a configurable fake whose interactions can be verified. A spy wraps a real object and selectively stubs behavior.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 610. `@Mock` vs `@InjectMocks`?

1. **Question**: `@Mock` vs `@InjectMocks`?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: @Mock creates a mock. @InjectMocks creates the class under test and injects available mocks by constructor, setter, or field.
6. **Detailed explanation**: @Mock creates a mock. @InjectMocks creates the class under test and injects available mocks by constructor, setter, or field. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “`@Mock` vs `@InjectMocks`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: @Mock creates a mock. @InjectMocks creates the class under test and injects available mocks by constructor, setter, or field.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 611. What is `@MockBean`?

1. **Question**: What is `@MockBean`?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: @MockBean adds or replaces a bean in a Spring test ApplicationContext; it is useful for slice tests but can increase context complexity.
6. **Detailed explanation**: @MockBean adds or replaces a bean in a Spring test ApplicationContext; it is useful for slice tests but can increase context complexity. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What is `@MockBean`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: @MockBean adds or replaces a bean in a Spring test ApplicationContext; it is useful for slice tests but can increase context complexity.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 612. How do you test Spring Boot controllers?

1. **Question**: How do you test Spring Boot controllers?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Use MockMvc or WebTestClient to send requests, assert status/headers/body, validate input, and mock service dependencies in a focused slice.
6. **Detailed explanation**: Use MockMvc or WebTestClient to send requests, assert status/headers/body, validate input, and mock service dependencies in a focused slice. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you test Spring Boot controllers?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Use MockMvc or WebTestClient to send requests, assert status/headers/body, validate input, and mock service dependencies in a focused slice.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 613. What is MockMvc?

1. **Question**: What is MockMvc?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: MockMvc tests Spring MVC request handling without starting a real server, including routing, validation, serialization, and advice.
6. **Detailed explanation**: MockMvc tests Spring MVC request handling without starting a real server, including routing, validation, serialization, and advice. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What is MockMvc?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: MockMvc tests Spring MVC request handling without starting a real server, including routing, validation, serialization, and advice.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 614. How do you test service layers?

1. **Question**: How do you test service layers?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Unit-test service rules with mocks, then add integration tests for transactions, repositories, and important collaborators.
6. **Detailed explanation**: Unit-test service rules with mocks, then add integration tests for transactions, repositories, and important collaborators. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you test service layers?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Unit-test service rules with mocks, then add integration tests for transactions, repositories, and important collaborators.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 615. How do you test repositories?

1. **Question**: How do you test repositories?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Use repository slice tests or Testcontainers with a real database to validate mappings, queries, constraints, and transaction behavior.
6. **Detailed explanation**: Use repository slice tests or Testcontainers with a real database to validate mappings, queries, constraints, and transaction behavior. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you test repositories?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Use repository slice tests or Testcontainers with a real database to validate mappings, queries, constraints, and transaction behavior.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 616. What is `@SpringBootTest`?

1. **Question**: What is `@SpringBootTest`?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: @SpringBootTest loads the full application context and is useful for broad integration tests but is slower and more coupled.
6. **Detailed explanation**: @SpringBootTest loads the full application context and is useful for broad integration tests but is slower and more coupled. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What is `@SpringBootTest`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: @SpringBootTest loads the full application context and is useful for broad integration tests but is slower and more coupled.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 617. `@WebMvcTest` vs `@SpringBootTest`?

1. **Question**: `@WebMvcTest` vs `@SpringBootTest`?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: @WebMvcTest loads MVC components only; @SpringBootTest loads the application and is appropriate for end-to-end integration within the service.
6. **Detailed explanation**: @WebMvcTest loads MVC components only; @SpringBootTest loads the application and is appropriate for end-to-end integration within the service. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “`@WebMvcTest` vs `@SpringBootTest`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: @WebMvcTest loads MVC components only; @SpringBootTest loads the application and is appropriate for end-to-end integration within the service.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 618. What is Testcontainers?

1. **Question**: What is Testcontainers?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Testcontainers starts disposable real services in containers for integration tests.
6. **Detailed explanation**: Testcontainers starts disposable real services in containers for integration tests. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What is Testcontainers?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Testcontainers starts disposable real services in containers for integration tests.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 619. Why use Testcontainers?

1. **Question**: Why use Testcontainers?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: They test against real database or broker behavior, reducing differences from production while keeping tests isolated and reproducible.
6. **Detailed explanation**: They test against real database or broker behavior, reducing differences from production while keeping tests isolated and reproducible. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “Why use Testcontainers?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: They test against real database or broker behavior, reducing differences from production while keeping tests isolated and reproducible.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 620. How do you test database transactions?

1. **Question**: How do you test database transactions?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Use transactional integration tests, explicit commit/rollback assertions, isolation tests, and a real database where behavior is vendor-specific.
6. **Detailed explanation**: Use transactional integration tests, explicit commit/rollback assertions, isolation tests, and a real database where behavior is vendor-specific. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you test database transactions?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Use transactional integration tests, explicit commit/rollback assertions, isolation tests, and a real database where behavior is vendor-specific.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 621. How do you test external API integrations?

1. **Question**: How do you test external API integrations?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Use contract tests, mock servers for failure cases, integration tests for serialization/authentication, and a small number of end-to-end tests.
6. **Detailed explanation**: Use contract tests, mock servers for failure cases, integration tests for serialization/authentication, and a small number of end-to-end tests. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you test external API integrations?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Use contract tests, mock servers for failure cases, integration tests for serialization/authentication, and a small number of end-to-end tests.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 622. How do you test asynchronous code?

1. **Question**: How do you test asynchronous code?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Use deterministic executors, latches, Awaitility, virtual time where possible, and assertions for completion, timeout, cancellation, and failure.
6. **Detailed explanation**: Use deterministic executors, latches, Awaitility, virtual time where possible, and assertions for completion, timeout, cancellation, and failure. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you test asynchronous code?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Use deterministic executors, latches, Awaitility, virtual time where possible, and assertions for completion, timeout, cancellation, and failure.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 623. What is code coverage?

1. **Question**: What is code coverage?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Code coverage measures executed code, branches, or conditions; it indicates scope but not correctness.
6. **Detailed explanation**: Code coverage measures executed code, branches, or conditions; it indicates scope but not correctness. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What is code coverage?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Code coverage measures executed code, branches, or conditions; it indicates scope but not correctness.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 624. Is 100% code coverage sufficient?

1. **Question**: Is 100% code coverage sufficient?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: No. High coverage can miss bad assertions, integration failures, concurrency bugs, security flaws, and untested behavior.
6. **Detailed explanation**: No. High coverage can miss bad assertions, integration failures, concurrency bugs, security flaws, and untested behavior. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “Is 100% code coverage sufficient?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: No. High coverage can miss bad assertions, integration failures, concurrency bugs, security flaws, and untested behavior.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 625. What is mutation testing?

1. **Question**: What is mutation testing?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Mutation testing changes code deliberately and checks whether tests fail, measuring test effectiveness rather than execution volume.
6. **Detailed explanation**: Mutation testing changes code deliberately and checks whether tests fail, measuring test effectiveness rather than execution volume. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What is mutation testing?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Mutation testing changes code deliberately and checks whether tests fail, measuring test effectiveness rather than execution volume.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 626. How do you test microservices?

1. **Question**: How do you test microservices?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Test each service in isolation, contracts between services, critical workflows end to end, resilience behavior, data consistency, and observability.
6. **Detailed explanation**: Test each service in isolation, contracts between services, critical workflows end to end, resilience behavior, data consistency, and observability. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you test microservices?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Test each service in isolation, contracts between services, critical workflows end to end, resilience behavior, data consistency, and observability.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 627. What tests should run before production deployment?

1. **Question**: What tests should run before production deployment?
2. **Difficulty**: Advanced
3. **Topic**: Testing
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Run fast unit checks first, then integration/contract/security tests, migration checks, smoke tests, and production-like acceptance gates.
6. **Detailed explanation**: Run fast unit checks first, then integration/contract/security tests, migration checks, smoke tests, and production-like acceptance gates. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What tests should run before production deployment?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
name: verify
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./mvnw test
```




10. **Time & space complexity**: Include build, test, scan, deployment, and storage costs; optimize feedback without removing essential coverage.
11. **Real-world/project usage**: This governs source control, CI, releases, migrations, secrets, quality gates, and incident recovery.
12. **Common mistakes**: Mutable artifacts, skipped tests, leaked secrets, unsafe migrations, no rollback, and treating coverage as quality by itself.
13. **Advantages**: Repeatability, faster feedback, auditability, and safer delivery.
14. **Limitations**: Pipeline time, maintenance, flaky checks, environment drift, and false confidence from weak gates.
15. **Comparison with related concepts**: Compare delivery strategies, test levels, rollback methods, artifact stores, and security checks.
16. **Production considerations**: Pin dependencies, protect credentials, sign/scan artifacts, use approvals where needed, and verify deployment health.
17. **Possible follow-up questions**: What happens on flaky tests, failed migrations, partial rollout, secret rotation, or rollback?
18. **Senior-level follow-up questions**: How would you measure lead time, change failure rate, recovery time, and confidence in the pipeline?
19. **Scenario-based question**: A deployment passes CI but fails in production. Explain how you would use artifacts, telemetry, rollout controls, and rollback.
20. **One-line revision note**: Run fast unit checks first, then integration/contract/security tests, migration checks, smoke tests, and production-like acceptance gates.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---
