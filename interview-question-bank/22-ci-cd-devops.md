# 22. CI/CD & DevOps

> Source range: questions 587–604
## 587. What is CI/CD?

1. **Question**: What is CI/CD?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: CI/CD automates integration, testing, packaging, and delivery so changes receive fast, repeatable feedback.
6. **Detailed explanation**: CI/CD automates integration, testing, packaging, and delivery so changes receive fast, repeatable feedback. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What is CI/CD?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: CI/CD automates integration, testing, packaging, and delivery so changes receive fast, repeatable feedback.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 588. Continuous Integration vs Continuous Delivery vs Continuous Deployment?

1. **Question**: Continuous Integration vs Continuous Delivery vs Continuous Deployment?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Continuous Integration merges and validates frequently. Continuous Delivery keeps changes deployable with a manual release decision. Continuous Deployment releases automatically after gates pass.
6. **Detailed explanation**: Continuous Integration merges and validates frequently. Continuous Delivery keeps changes deployable with a manual release decision. Continuous Deployment releases automatically after gates pass. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “Continuous Integration vs Continuous Delivery vs Continuous Deployment?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Continuous Integration merges and validates frequently. Continuous Delivery keeps changes deployable with a manual release decision. Continuous Deployment releases automatically after gates pass.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 589. Describe your CI/CD pipeline.

1. **Question**: Describe your CI/CD pipeline.
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: A typical pipeline checks out code, restores dependencies, runs static and unit tests, builds an artifact/image, scans it, runs integration tests, deploys progressively, verifies health, and records results.
6. **Detailed explanation**: A typical pipeline checks out code, restores dependencies, runs static and unit tests, builds an artifact/image, scans it, runs integration tests, deploys progressively, verifies health, and records results. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “Describe your CI/CD pipeline.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: A typical pipeline checks out code, restores dependencies, runs static and unit tests, builds an artifact/image, scans it, runs integration tests, deploys progressively, verifies health, and records results.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 590. What stages should a production pipeline contain?

1. **Question**: What stages should a production pipeline contain?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Include source validation, unit/integration tests, quality and security scans, artifact creation, migration checks, deployment, smoke tests, monitoring, and rollback.
6. **Detailed explanation**: Include source validation, unit/integration tests, quality and security scans, artifact creation, migration checks, deployment, smoke tests, monitoring, and rollback. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What stages should a production pipeline contain?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Include source validation, unit/integration tests, quality and security scans, artifact creation, migration checks, deployment, smoke tests, monitoring, and rollback.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 591. How do you run automated tests in CI/CD?

1. **Question**: How do you run automated tests in CI/CD?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Run deterministic tests in isolated environments, publish results, fail the stage on defined thresholds, and quarantine flaky tests with ownership.
6. **Detailed explanation**: Run deterministic tests in isolated environments, publish results, fail the stage on defined thresholds, and quarantine flaky tests with ownership. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you run automated tests in CI/CD?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Run deterministic tests in isolated environments, publish results, fail the stage on defined thresholds, and quarantine flaky tests with ownership.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 592. How do you perform security scanning?

1. **Question**: How do you perform security scanning?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Run SAST, dependency and secret scanning, container/IaC scans, license checks, and DAST where appropriate; triage findings by exploitability and severity.
6. **Detailed explanation**: Run SAST, dependency and secret scanning, container/IaC scans, license checks, and DAST where appropriate; triage findings by exploitability and severity. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you perform security scanning?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Run SAST, dependency and secret scanning, container/IaC scans, license checks, and DAST where appropriate; triage findings by exploitability and severity.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 593. How do you manage environment-specific deployments?

1. **Question**: How do you manage environment-specific deployments?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Promote the same immutable artifact through environments with externalized configuration and environment-specific approvals or policies.
6. **Detailed explanation**: Promote the same immutable artifact through environments with externalized configuration and environment-specific approvals or policies. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you manage environment-specific deployments?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Promote the same immutable artifact through environments with externalized configuration and environment-specific approvals or policies.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 594. How do you manage secrets in CI/CD?

1. **Question**: How do you manage secrets in CI/CD?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Use the CI/CD platform secret store or a cloud secret manager, short-lived credentials, masking, rotation, and least privilege.
6. **Detailed explanation**: Use the CI/CD platform secret store or a cloud secret manager, short-lived credentials, masking, rotation, and least privilege. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you manage secrets in CI/CD?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Use the CI/CD platform secret store or a cloud secret manager, short-lived credentials, masking, rotation, and least privilege.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 595. What is artifact management?

1. **Question**: What is artifact management?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Artifact management stores immutable, traceable build outputs and metadata so deployments use exactly what was tested.
6. **Detailed explanation**: Artifact management stores immutable, traceable build outputs and metadata so deployments use exactly what was tested. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What is artifact management?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Artifact management stores immutable, traceable build outputs and metadata so deployments use exactly what was tested.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 596. What is blue-green deployment?

1. **Question**: What is blue-green deployment?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Blue-green deployment runs old and new environments side by side and switches traffic, enabling fast rollback at extra capacity cost.
6. **Detailed explanation**: Blue-green deployment runs old and new environments side by side and switches traffic, enabling fast rollback at extra capacity cost. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What is blue-green deployment?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Blue-green deployment runs old and new environments side by side and switches traffic, enabling fast rollback at extra capacity cost.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 597. What is canary deployment?

1. **Question**: What is canary deployment?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Canary deployment sends a small percentage of traffic to the new version and expands it based on health and business metrics.
6. **Detailed explanation**: Canary deployment sends a small percentage of traffic to the new version and expands it based on health and business metrics. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What is canary deployment?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Canary deployment sends a small percentage of traffic to the new version and expands it based on health and business metrics.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 598. Rolling vs blue-green vs canary?

1. **Question**: Rolling vs blue-green vs canary?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Rolling updates replace instances gradually; blue-green switches between complete environments; canary controls exposure by traffic percentage.
6. **Detailed explanation**: Rolling updates replace instances gradually; blue-green switches between complete environments; canary controls exposure by traffic percentage. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “Rolling vs blue-green vs canary?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Rolling updates replace instances gradually; blue-green switches between complete environments; canary controls exposure by traffic percentage.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 599. How do you rollback a failed deployment?

1. **Question**: How do you rollback a failed deployment?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Stop promotion, preserve evidence, shift traffic back or restore the previous release, validate data compatibility, and communicate impact.
6. **Detailed explanation**: Stop promotion, preserve evidence, shift traffic back or restore the previous release, validate data compatibility, and communicate impact. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you rollback a failed deployment?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Stop promotion, preserve evidence, shift traffic back or restore the previous release, validate data compatibility, and communicate impact.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 600. How do you implement zero-downtime deployments?

1. **Question**: How do you implement zero-downtime deployments?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Use backward-compatible APIs and schemas, readiness and health checks, connection draining, multiple replicas, and a controlled rollout.
6. **Detailed explanation**: Use backward-compatible APIs and schemas, readiness and health checks, connection draining, multiple replicas, and a controlled rollout. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you implement zero-downtime deployments?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Use backward-compatible APIs and schemas, readiness and health checks, connection draining, multiple replicas, and a controlled rollout.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 601. How do database migrations fit into CI/CD?

1. **Question**: How do database migrations fit into CI/CD?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Run migrations as versioned, reviewed, observable steps coordinated with application compatibility.
6. **Detailed explanation**: Run migrations as versioned, reviewed, observable steps coordinated with application compatibility. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do database migrations fit into CI/CD?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Run migrations as versioned, reviewed, observable steps coordinated with application compatibility.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 602. How do you handle backward-incompatible DB changes?

1. **Question**: How do you handle backward-incompatible DB changes?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Use expand-and-contract: add compatible schema first, deploy code that supports both, migrate data, then remove old structures later.
6. **Detailed explanation**: Use expand-and-contract: add compatible schema first, deploy code that supports both, migrate data, then remove old structures later. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you handle backward-incompatible DB changes?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Use expand-and-contract: add compatible schema first, deploy code that supports both, migrate data, then remove old structures later.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 603. What checks should happen before production deployment?

1. **Question**: What checks should happen before production deployment?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Check tests, security, artifact provenance, migrations, capacity, observability, rollback, approvals, and change communication.
6. **Detailed explanation**: Check tests, security, artifact provenance, migrations, capacity, observability, rollback, approvals, and change communication. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “What checks should happen before production deployment?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Check tests, security, artifact provenance, migrations, capacity, observability, rollback, approvals, and change communication.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---

## 604. How do you decide whether an AI-generated code change is production-ready?

1. **Question**: How do you decide whether an AI-generated code change is production-ready?
2. **Difficulty**: Advanced
3. **Topic**: CI/CD & DevOps
4. **What interviewer is testing**: Whether you can make the engineering process reliable, secure, repeatable, and measurable.
5. **Short interview answer (30–60 seconds)**: Review requirements, design, security, tests, dependencies, observability, performance, and rollback; run the code and verify behavior rather than trusting generation.
6. **Detailed explanation**: Review requirements, design, security, tests, dependencies, observability, performance, and rollback; run the code and verify behavior rather than trusting generation. The triggers, controls, evidence, and rollback behavior define the delivery safeguard.
7. **How it works internally**: The toolchain builds artifacts, runs checks, stores results, and promotes versioned outputs through controlled environments.
8. **Example**:

For “How do you decide whether an AI-generated code change is production-ready?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

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
20. **One-line revision note**: Review requirements, design, security, tests, dependencies, observability, performance, and rollback; run the code and verify behavior rather than trusting generation.
21. **Image visuals (if required)**: A pipeline or deployment-strategy diagram is useful.

---
