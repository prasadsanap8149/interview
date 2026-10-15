# Answer Progress Tracker

Companion checklist for questions.md (175 questions). Full answers live in answer.md.

Legend: [x] = full answer written in answer.md | [ ] = still to prepare

**Progress: 20 / 175 answered**


## 1. Core Java & Backend Engineering (Advanced)

- [x] 1. Explain the `equals()` and `hashCode()` contract. What breaks if it’s violated?
- [x] 2. How does Java memory management work (Heap, Stack, Metaspace)?
- [x] 3. Difference between `volatile`, `synchronized`, and `Atomic` classes.
- [x] 4. How does garbage collection work in G1 vs ZGC?
- [x] 5. What happens if an exception is thrown inside a `finally` block?
- [x] 6. How do you design immutable objects in Java?
- [x] 7. Explain class loading in Java. How do custom class loaders work?
- [x] 8. What are memory leaks in Java? Give real examples from production.
- [x] 9. How do you debug OutOfMemoryError in a running JVM?
- [x] 10. Difference between checked and unchecked exceptions—real-world use cases.
- [x] 11. How does Spring Boot auto-configuration work internally?
- [x] 12. What is the difference between `@Component`, `@Service`, and `@Repository`?
- [x] 13. How does Spring manage dependency injection lifecycle?
- [x] 14. What is `@Transactional`? How does propagation work?
- [x] 15. When does `@Transactional` NOT work?
- [x] 16. Explain lazy vs eager loading in Spring Data JPA.
- [x] 17. How do you handle N+1 query issues?
- [x] 18. Difference between `JpaRepository` and `CrudRepository`.
- [x] 19. How do you implement pagination and sorting efficiently?
- [x] 20. How do you secure Spring Boot applications?

## 2. Microservices Architecture

- [ ] 21. What problems do microservices solve—and what problems do they create?
- [ ] 22. How do you decide service boundaries?
- [ ] 23. Monolith vs Microservices—when would you **not** use microservices?
- [ ] 24. How do you manage inter-service communication?
- [ ] 25. REST vs gRPC vs Messaging—when to use what?
- [ ] 26. How do you handle versioning of APIs?
- [ ] 27. How do you avoid tight coupling between services?
- [ ] 28. What is the Strangler Pattern?
- [ ] 29. How do you migrate from monolith to microservices?
- [ ] 30. How do you design for backward compatibility?
- [ ] 31. What is CAP theorem? How does it apply in real systems?
- [ ] 32. What is eventual consistency?
- [ ] 33. How do you handle distributed transactions?
- [ ] 34. Saga pattern vs Two-Phase Commit.
- [ ] 35. What happens when one microservice goes down?
- [ ] 36. How do retries cause cascading failures?
- [ ] 37. How do circuit breakers work?
- [ ] 38. How do you design idempotent APIs?
- [ ] 39. How do you prevent duplicate processing?
- [ ] 40. How do you ensure data consistency across services?

## 3. Event-Driven Architecture (Kafka, RabbitMQ)

- [ ] 41. Kafka vs RabbitMQ—key differences.
- [ ] 42. What guarantees does Kafka provide?
- [ ] 43. How does Kafka ensure message ordering?
- [ ] 44. What is consumer group rebalancing?
- [ ] 45. How do you handle poison messages?
- [ ] 46. How do you design exactly-once processing?
- [ ] 47. What happens if a consumer crashes mid-processing?
- [ ] 48. How do you scale Kafka consumers?
- [ ] 49. How do you handle schema evolution?
- [ ] 50. How do you secure Kafka?
- [ ] 51. How would you design an event-driven audit logging system?
- [ ] 52. How do you replay events safely?
- [ ] 53. How do you handle message duplication in Kafka?
- [ ] 54. What happens when producers are faster than consumers?
- [ ] 55. How do you monitor Kafka lag?

## 4. Security, Authentication & Cybersecurity (VERY IMPORTANT)

- [ ] 56. OAuth 2.0 vs OpenID Connect.
- [ ] 57. Explain OAuth flow step-by-step.
- [ ] 58. What is Azure AD B2C?
- [ ] 59. How do refresh tokens work?
- [ ] 60. How do you revoke tokens?
- [ ] 61. JWT vs opaque tokens.
- [ ] 62. How do you store tokens securely?
- [ ] 63. How do you implement RBAC?
- [ ] 64. How do you protect APIs from abuse?
- [ ] 65. How do you secure SPAs?
- [ ] 66. What is OWASP Top 10?
- [ ] 67. How do you prevent SQL Injection?
- [ ] 68. How do you prevent XSS in SPAs?
- [ ] 69. How do you secure REST APIs?
- [ ] 70. How do you handle secrets?
- [ ] 71. What is CSRF and how do you prevent it?
- [ ] 72. How do you protect file uploads?
- [ ] 73. How do you do input validation correctly?
- [ ] 74. How do you log securely?
- [ ] 75. How do you handle PII data?

## 5. Cloud (Azure, OCI, AWS)

- [ ] 76. How do you design a secure cloud architecture?
- [ ] 77. Difference between IaaS, PaaS, SaaS.
- [ ] 78. How does Azure networking work?
- [ ] 79. Azure Key Vault vs AWS Secrets Manager.
- [ ] 80. How do you implement least privilege?
- [ ] 81. How do you secure cloud storage?
- [ ] 82. How do you handle cloud monitoring?
- [ ] 83. What is cloud shared responsibility model?
- [ ] 84. How do you secure container workloads in cloud?
- [ ] 85. How do you design multi-region deployments?
- [ ] 86. How do you migrate on-prem apps to cloud?
- [ ] 87. Lift-and-shift vs re-architecture.
- [ ] 88. How do you handle legacy systems migration?
- [ ] 89. How do you validate cloud migration success?
- [ ] 90. How do you handle downtime during migration?

## 6. Docker, Kubernetes & Linux

- [ ] 91. Difference between Docker image and container.
- [ ] 92. How do you reduce Docker image size?
- [ ] 93. What is a multi-stage Docker build?
- [ ] 94. How do you scan container images?
- [ ] 95. How do you manage secrets in Docker?
- [ ] 96. What is a Pod?
- [ ] 97. Deployment vs StatefulSet.
- [ ] 98. How does Kubernetes handle scaling?
- [ ] 99. What is a readiness vs liveness probe?
- [ ] 100. How do you secure Kubernetes?
- [ ] 101. What is RBAC in Kubernetes?
- [ ] 102. How do you handle rolling updates?
- [ ] 103. How do you debug a crashing pod?
- [ ] 104. How do you control resource limits?
- [ ] 105. What is a service mesh?

## 7. Frontend & SPA (Angular / React)

- [ ] 106. SPA vs traditional web apps.
- [ ] 107. How do you secure SPAs?
- [ ] 108. How does token storage work in browser?
- [ ] 109. XSS risks in Angular/React.
- [ ] 110. How do you manage environment configs?
- [ ] 111. How do you handle CORS?
- [ ] 112. How do you optimize SPA performance?
- [ ] 113. State management approaches.
- [ ] 114. How do you integrate SPA with OAuth?
- [ ] 115. How do you handle role-based UI rendering?

## 8. DevSecOps & CI/CD

- [ ] 116. DevOps vs DevSecOps.
- [ ] 117. What is shift-left security?
- [ ] 118. How do you integrate security into CI/CD?
- [ ] 119. What security scans do you run in pipeline?
- [ ] 120. How do you handle vulnerabilities found in CI?
- [ ] 121. How do you secure Jenkins/GitHub Actions?
- [ ] 122. How do you manage secrets in CI/CD?
- [ ] 123. How do you enforce security policies?
- [ ] 124. How do you monitor runtime security?
- [ ] 125. How do you do zero-trust architecture?

## 9. Databases & SQL

- [ ] 126. PostgreSQL vs MongoDB.
- [ ] 127. When do you choose NoSQL?
- [ ] 128. Indexing—how does it work?
- [ ] 129. How do you optimize slow queries?
- [ ] 130. ACID properties.
- [ ] 131. Isolation levels.
- [ ] 132. How do you handle database migrations?
- [ ] 133. How do you handle schema changes?
- [ ] 134. How do you secure databases?
- [ ] 135. How do you handle backups and recovery?

## 10. AI, RAG & Automation (Modern Edge)

- [ ] 136. What is Retrieval-Augmented Generation (RAG)?
- [ ] 137. How does RAG improve LLM accuracy?
- [ ] 138. How would you integrate RAG into an application?
- [ ] 139. What is Agentic AI?
- [ ] 140. How do agents communicate?
- [ ] 141. How do you secure AI pipelines?
- [ ] 142. What is LangChain used for?
- [ ] 143. How does n8n help automation?
- [ ] 144. How do you prevent data leakage in AI?
- [ ] 145. How do you log AI decisions?

## 11. Integration & Enterprise Systems

- [ ] 146. How do you integrate with SIEM systems?
- [ ] 147. How do you design audit logs?
- [ ] 148. How do you integrate ERP/CRM safely?
- [ ] 149. How do you handle data transformation?
- [ ] 150. How do you manage API rate limits?
- [ ] 151. How do you handle failures in integrations?
- [ ] 152. How do you ensure data integrity?
- [ ] 153. How do you version integrations?
- [ ] 154. How do you test integrations?
- [ ] 155. How do you secure third-party APIs?

## 12. Agile, SDLC & Project Management

- [ ] 156. Explain SDLC end-to-end.
- [ ] 157. Agile vs Waterfall.
- [ ] 158. How do you estimate tasks?
- [ ] 159. How do you handle changing requirements?
- [ ] 160. How do you manage technical debt?
- [ ] 161. How do you document systems?
- [ ] 162. How do you manage releases?
- [ ] 163. How do you handle production incidents?
- [ ] 164. How do you coordinate cross-functional teams?
- [ ] 165. How do you ensure compliance requirements?

## 13. Behavioral & Scenario Questions (VERY LIKELY)

- [ ] 166. Describe a production outage you handled.
- [ ] 167. A security vulnerability was found in prod—what do you do?
- [ ] 168. How do you handle conflict with security teams?
- [ ] 169. How do you prioritize security vs delivery?
- [ ] 170. How do you handle incomplete requirements?
- [ ] 171. How do you ensure quality under tight deadlines?
- [ ] 172. How do you mentor junior developers?
- [ ] 173. How do you handle remote collaboration?
- [ ] 174. How do you handle on-call stress?
- [ ] 175. Why Help AG?

