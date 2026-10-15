# 19. AWS

> Source range: questions 508–544
## 508. What AWS services have you worked with?

1. **Question**: What AWS services have you worked with?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Name only services you have actually used and explain the problem each solved, the architecture, and one operational lesson.
6. **Detailed explanation**: Name only services you have actually used and explain the problem each solved, the architecture, and one operational lesson. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What AWS services have you worked with?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Name only services you have actually used and explain the problem each solved, the architecture, and one operational lesson.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 509. EC2 vs ECS vs EKS vs Lambda?

1. **Question**: EC2 vs ECS vs EKS vs Lambda?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: EC2 provides virtual machines, ECS orchestrates containers, EKS provides managed Kubernetes, and Lambda runs event-driven functions without managing servers.
6. **Detailed explanation**: EC2 provides virtual machines, ECS orchestrates containers, EKS provides managed Kubernetes, and Lambda runs event-driven functions without managing servers. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “EC2 vs ECS vs EKS vs Lambda?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: EC2 provides virtual machines, ECS orchestrates containers, EKS provides managed Kubernetes, and Lambda runs event-driven functions without managing servers.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 510. What is EC2?

1. **Question**: What is EC2?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: EC2 is a resizable virtual machine service with configurable instance types, storage, networking, IAM roles, and lifecycle.
6. **Detailed explanation**: EC2 is a resizable virtual machine service with configurable instance types, storage, networking, IAM roles, and lifecycle. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is EC2?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: EC2 is a resizable virtual machine service with configurable instance types, storage, networking, IAM roles, and lifecycle.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 511. What is an AMI?

1. **Question**: What is an AMI?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: An AMI is a machine-image template containing an operating system and software used to launch EC2 instances.
6. **Detailed explanation**: An AMI is a machine-image template containing an operating system and software used to launch EC2 instances. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is an AMI?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: An AMI is a machine-image template containing an operating system and software used to launch EC2 instances.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 512. What is Auto Scaling?

1. **Question**: What is Auto Scaling?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Auto Scaling adjusts instance count based on demand, health, and policy while maintaining minimum, desired, and maximum capacity.
6. **Detailed explanation**: Auto Scaling adjusts instance count based on demand, health, and policy while maintaining minimum, desired, and maximum capacity. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is Auto Scaling?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Auto Scaling adjusts instance count based on demand, health, and policy while maintaining minimum, desired, and maximum capacity.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 513. What is an ALB?

1. **Question**: What is an ALB?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: An ALB is a Layer-7 HTTP load balancer supporting host/path routing, TLS termination, target health, and integration with services.
6. **Detailed explanation**: An ALB is a Layer-7 HTTP load balancer supporting host/path routing, TLS termination, target health, and integration with services. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is an ALB?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: An ALB is a Layer-7 HTTP load balancer supporting host/path routing, TLS termination, target health, and integration with services.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 514. ALB vs NLB?

1. **Question**: ALB vs NLB?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: ALB is Layer 7 and understands HTTP. NLB is Layer 4, handles very high throughput and static IP use cases, and supports TCP/TLS/UDP patterns.
6. **Detailed explanation**: ALB is Layer 7 and understands HTTP. NLB is Layer 4, handles very high throughput and static IP use cases, and supports TCP/TLS/UDP patterns. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “ALB vs NLB?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: ALB is Layer 7 and understands HTTP. NLB is Layer 4, handles very high throughput and static IP use cases, and supports TCP/TLS/UDP patterns.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 515. What is S3?

1. **Question**: What is S3?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: S3 is durable object storage organized into buckets and keys, with policy, versioning, lifecycle, encryption, and event integrations.
6. **Detailed explanation**: S3 is durable object storage organized into buckets and keys, with policy, versioning, lifecycle, encryption, and event integrations. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is S3?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: S3 is durable object storage organized into buckets and keys, with policy, versioning, lifecycle, encryption, and event integrations.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 516. What are S3 storage classes?

1. **Question**: What are S3 storage classes?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Storage classes trade access cost and retrieval latency, from frequently accessed Standard to infrequent, archival, and intelligent tiering classes.
6. **Detailed explanation**: Storage classes trade access cost and retrieval latency, from frequently accessed Standard to infrequent, archival, and intelligent tiering classes. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What are S3 storage classes?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Storage classes trade access cost and retrieval latency, from frequently accessed Standard to infrequent, archival, and intelligent tiering classes.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 517. What is S3 versioning?

1. **Question**: What is S3 versioning?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Versioning keeps multiple object versions so accidental overwrite or deletion can be recovered; it increases storage cost.
6. **Detailed explanation**: Versioning keeps multiple object versions so accidental overwrite or deletion can be recovered; it increases storage cost. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is S3 versioning?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Versioning keeps multiple object versions so accidental overwrite or deletion can be recovered; it increases storage cost.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 518. What is S3 lifecycle management?

1. **Question**: What is S3 lifecycle management?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Lifecycle rules transition or expire objects based on age, tags, prefixes, or versions.
6. **Detailed explanation**: Lifecycle rules transition or expire objects based on age, tags, prefixes, or versions. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is S3 lifecycle management?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Lifecycle rules transition or expire objects based on age, tags, prefixes, or versions.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 519. What is IAM?

1. **Question**: What is IAM?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: IAM controls authentication and authorization through principals, policies, roles, and conditions.
6. **Detailed explanation**: IAM controls authentication and authorization through principals, policies, roles, and conditions. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is IAM?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: IAM controls authentication and authorization through principals, policies, roles, and conditions.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 520. User vs Role vs Policy?

1. **Question**: User vs Role vs Policy?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: A user is a long-lived identity, a role is assumable temporary identity, and a policy is a document granting or denying actions on resources.
6. **Detailed explanation**: A user is a long-lived identity, a role is assumable temporary identity, and a policy is a document granting or denying actions on resources. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “User vs Role vs Policy?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: A user is a long-lived identity, a role is assumable temporary identity, and a policy is a document granting or denying actions on resources.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 521. What is least-privilege access?

1. **Question**: What is least-privilege access?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Least privilege grants only required actions and resources for the required time and context, reducing blast radius.
6. **Detailed explanation**: Least privilege grants only required actions and resources for the required time and context, reducing blast radius. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is least-privilege access?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Least privilege grants only required actions and resources for the required time and context, reducing blast radius.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 522. What is VPC?

1. **Question**: What is VPC?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: A VPC is an isolated virtual network with subnets, route tables, gateways, security controls, and endpoints.
6. **Detailed explanation**: A VPC is an isolated virtual network with subnets, route tables, gateways, security controls, and endpoints. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is VPC?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: A VPC is an isolated virtual network with subnets, route tables, gateways, security controls, and endpoints.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 523. Public vs private subnet?

1. **Question**: Public vs private subnet?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Public subnets have a route to an internet gateway. Private subnets do not expose instances directly and use NAT or endpoints for outbound access.
6. **Detailed explanation**: Public subnets have a route to an internet gateway. Private subnets do not expose instances directly and use NAT or endpoints for outbound access. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “Public vs private subnet?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Public subnets have a route to an internet gateway. Private subnets do not expose instances directly and use NAT or endpoints for outbound access.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 524. Security Group vs NACL?

1. **Question**: Security Group vs NACL?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Security groups are stateful instance or ENI firewalls. NACLs are stateless subnet-level rules evaluated in both directions.
6. **Detailed explanation**: Security groups are stateful instance or ENI firewalls. NACLs are stateless subnet-level rules evaluated in both directions. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “Security Group vs NACL?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Security groups are stateful instance or ENI firewalls. NACLs are stateless subnet-level rules evaluated in both directions.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 525. What is Internet Gateway?

1. **Question**: What is Internet Gateway?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: An Internet Gateway connects a VPC to the internet for resources with public routes and addresses.
6. **Detailed explanation**: An Internet Gateway connects a VPC to the internet for resources with public routes and addresses. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is Internet Gateway?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: An Internet Gateway connects a VPC to the internet for resources with public routes and addresses.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 526. What is NAT Gateway?

1. **Question**: What is NAT Gateway?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: A NAT Gateway provides outbound internet access for private-subnet resources without allowing unsolicited inbound connections.
6. **Detailed explanation**: A NAT Gateway provides outbound internet access for private-subnet resources without allowing unsolicited inbound connections. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is NAT Gateway?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: A NAT Gateway provides outbound internet access for private-subnet resources without allowing unsolicited inbound connections.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 527. What is Route 53?

1. **Question**: What is Route 53?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Route 53 provides DNS hosting, health checks, routing policies, and domain registration.
6. **Detailed explanation**: Route 53 provides DNS hosting, health checks, routing policies, and domain registration. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is Route 53?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Route 53 provides DNS hosting, health checks, routing policies, and domain registration.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 528. What is RDS?

1. **Question**: What is RDS?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: RDS is managed relational database service with backups, patching, monitoring, Multi-AZ, replicas, and engine choices.
6. **Detailed explanation**: RDS is managed relational database service with backups, patching, monitoring, Multi-AZ, replicas, and engine choices. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is RDS?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: RDS is managed relational database service with backups, patching, monitoring, Multi-AZ, replicas, and engine choices.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 529. RDS Multi-AZ vs Read Replica?

1. **Question**: RDS Multi-AZ vs Read Replica?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Multi-AZ provides synchronous standby failover for availability. Read replicas serve read traffic asynchronously and can scale reads.
6. **Detailed explanation**: Multi-AZ provides synchronous standby failover for availability. Read replicas serve read traffic asynchronously and can scale reads. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “RDS Multi-AZ vs Read Replica?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Multi-AZ provides synchronous standby failover for availability. Read replicas serve read traffic asynchronously and can scale reads.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 530. What is AWS Lambda?

1. **Question**: What is AWS Lambda?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Lambda runs short-lived event-driven functions with managed scaling, execution limits, and pay-per-use pricing.
6. **Detailed explanation**: Lambda runs short-lived event-driven functions with managed scaling, execution limits, and pay-per-use pricing. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is AWS Lambda?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Lambda runs short-lived event-driven functions with managed scaling, execution limits, and pay-per-use pricing.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 531. What is API Gateway?

1. **Question**: What is API Gateway?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: API Gateway exposes and governs APIs with routing, authentication, throttling, transformation, and monitoring.
6. **Detailed explanation**: API Gateway exposes and governs APIs with routing, authentication, throttling, transformation, and monitoring. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is API Gateway?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: API Gateway exposes and governs APIs with routing, authentication, throttling, transformation, and monitoring.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 532. What is CloudWatch?

1. **Question**: What is CloudWatch?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: CloudWatch provides metrics, logs, alarms, dashboards, and events for operational monitoring.
6. **Detailed explanation**: CloudWatch provides metrics, logs, alarms, dashboards, and events for operational monitoring. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is CloudWatch?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: CloudWatch provides metrics, logs, alarms, dashboards, and events for operational monitoring.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 533. What is CloudTrail?

1. **Question**: What is CloudTrail?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: CloudTrail records API activity for audit, security investigation, and governance.
6. **Detailed explanation**: CloudTrail records API activity for audit, security investigation, and governance. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is CloudTrail?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: CloudTrail records API activity for audit, security investigation, and governance.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 534. What is Secrets Manager?

1. **Question**: What is Secrets Manager?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Secrets Manager stores and rotates sensitive secrets with controlled retrieval and audit.
6. **Detailed explanation**: Secrets Manager stores and rotates sensitive secrets with controlled retrieval and audit. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is Secrets Manager?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Secrets Manager stores and rotates sensitive secrets with controlled retrieval and audit.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 535. Secrets Manager vs Parameter Store?

1. **Question**: Secrets Manager vs Parameter Store?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Secrets Manager focuses on secret storage and rotation; Parameter Store provides configuration parameters and optional encryption, often at lower cost.
6. **Detailed explanation**: Secrets Manager focuses on secret storage and rotation; Parameter Store provides configuration parameters and optional encryption, often at lower cost. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “Secrets Manager vs Parameter Store?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Secrets Manager focuses on secret storage and rotation; Parameter Store provides configuration parameters and optional encryption, often at lower cost.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 536. What is SQS?

1. **Question**: What is SQS?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: SQS is a managed queue that decouples producers and consumers with visibility timeouts, retries, and dead-letter queues.
6. **Detailed explanation**: SQS is a managed queue that decouples producers and consumers with visibility timeouts, retries, and dead-letter queues. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is SQS?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: SQS is a managed queue that decouples producers and consumers with visibility timeouts, retries, and dead-letter queues.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 537. What is SNS?

1. **Question**: What is SNS?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: SNS is a pub/sub notification service that fans messages out to subscribed endpoints such as queues, functions, or HTTP consumers.
6. **Detailed explanation**: SNS is a pub/sub notification service that fans messages out to subscribed endpoints such as queues, functions, or HTTP consumers. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is SNS?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: SNS is a pub/sub notification service that fans messages out to subscribed endpoints such as queues, functions, or HTTP consumers.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 538. SQS vs SNS?

1. **Question**: SQS vs SNS?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: SQS provides pull-based durable work queues; SNS pushes a message to multiple subscribers for fan-out.
6. **Detailed explanation**: SQS provides pull-based durable work queues; SNS pushes a message to multiple subscribers for fan-out. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “SQS vs SNS?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: SQS provides pull-based durable work queues; SNS pushes a message to multiple subscribers for fan-out.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 539. What is dead-letter queue?

1. **Question**: What is dead-letter queue?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: A dead-letter queue receives messages that exceed delivery attempts so they can be inspected and replayed safely.
6. **Detailed explanation**: A dead-letter queue receives messages that exceed delivery attempts so they can be inspected and replayed safely. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is dead-letter queue?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: A dead-letter queue receives messages that exceed delivery attempts so they can be inspected and replayed safely.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 540. What is ECR?

1. **Question**: What is ECR?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: ECR is a managed container image registry integrated with IAM, scanning, lifecycle policies, and ECS/EKS.
6. **Detailed explanation**: ECR is a managed container image registry integrated with IAM, scanning, lifecycle policies, and ECS/EKS. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “What is ECR?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: ECR is a managed container image registry integrated with IAM, scanning, lifecycle policies, and ECS/EKS.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 541. How would you deploy Spring Boot to AWS?

1. **Question**: How would you deploy Spring Boot to AWS?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Package the service, build and scan an image or artifact, deploy to ECS/EKS/EC2 or a managed platform, configure IAM, networking, secrets, health, and observability.
6. **Detailed explanation**: Package the service, build and scan an image or artifact, deploy to ECS/EKS/EC2 or a managed platform, configure IAM, networking, secrets, health, and observability. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “How would you deploy Spring Boot to AWS?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Package the service, build and scan an image or artifact, deploy to ECS/EKS/EC2 or a managed platform, configure IAM, networking, secrets, health, and observability.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 542. How would you design a highly available AWS application?

1. **Question**: How would you design a highly available AWS application?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Use multiple Availability Zones, load balancing, stateless instances, managed databases with failover, replicated storage, autoscaling, backups, and tested recovery.
6. **Detailed explanation**: Use multiple Availability Zones, load balancing, stateless instances, managed databases with failover, replicated storage, autoscaling, backups, and tested recovery. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “How would you design a highly available AWS application?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Use multiple Availability Zones, load balancing, stateless instances, managed databases with failover, replicated storage, autoscaling, backups, and tested recovery.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 543. How would you reduce AWS cost?

1. **Question**: How would you reduce AWS cost?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Right-size resources, use autoscaling and savings plans, turn off idle environments, select storage classes, control data transfer, and monitor cost allocation.
6. **Detailed explanation**: Right-size resources, use autoscaling and savings plans, turn off idle environments, select storage classes, control data transfer, and monitor cost allocation. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “How would you reduce AWS cost?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Right-size resources, use autoscaling and savings plans, turn off idle environments, select storage classes, control data transfer, and monitor cost allocation.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---

## 544. How do you troubleshoot an EC2-hosted API that suddenly becomes slow?

1. **Question**: How do you troubleshoot an EC2-hosted API that suddenly becomes slow?
2. **Difficulty**: Advanced
3. **Topic**: AWS
4. **What interviewer is testing**: Whether you can select, secure, operate, and troubleshoot cloud services using reliability and cost principles.
5. **Short interview answer (30–60 seconds)**: Check latency by layer, CPU/memory, network, disk/DB, load balancer health, logs, recent deploys, dependencies, instance limits, and scaling behavior.
6. **Detailed explanation**: Check latency by layer, CPU/memory, network, disk/DB, load balancer health, logs, recent deploys, dependencies, instance limits, and scaling behavior. Availability, security, scaling, and cost are the relevant trade-offs.
7. **How it works internally**: AWS control planes provision resources and data planes handle traffic, storage, identity, events, and monitoring according to the selected service.
8. **Example**:

For “How do you troubleshoot an EC2-hosted API that suddenly becomes slow?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
services:
  app:
    image: example/app:1.0.0
    environment:
      SPRING_PROFILES_ACTIVE: prod
    restart: unless-stopped
```




10. **Time & space complexity**: Discuss request latency, throughput, scaling limits, storage, transfer, and operational cost rather than only local algorithmic complexity.
11. **Real-world/project usage**: This governs hosting, networking, databases, object storage, messaging, identity, observability, and delivery pipelines.
12. **Common mistakes**: Public exposure, broad IAM, unencrypted data, single-AZ design, unbounded queues, missing backups, and ignoring cost or quotas.
13. **Advantages**: Managed infrastructure, elastic capacity, durable services, broad integrations, and regional availability options.
14. **Limitations**: Vendor coupling, service quotas, distributed failure modes, cost complexity, and configuration risk.
15. **Comparison with related concepts**: Compare EC2/ECS/EKS/Lambda, ALB/NLB, Multi-AZ/replica, SQS/SNS, and Secrets Manager/Parameter Store.
16. **Production considerations**: Use least privilege, private networking, encryption, backups, health checks, alarms, budgets, and tested failover.
17. **Possible follow-up questions**: What fails in one AZ, on credential loss, under a traffic spike, or when a dependency throttles?
18. **Senior-level follow-up questions**: How would you design multi-region recovery, control blast radius, and prove cost and availability objectives?
19. **Scenario-based question**: A production API becomes slow or unavailable on AWS. Metrics, logs, health, scaling, network, database, and recent changes provide the evidence for diagnosis.
20. **One-line revision note**: Check latency by layer, CPU/memory, network, disk/DB, load balancer health, logs, recent deploys, dependencies, instance limits, and scaling behavior.
21. **Image visuals (if required)**: A VPC, multi-AZ, or event-flow diagram helps clarify the architecture.

---
