# 17. Docker

> Source range: questions 438–462
## 438. What is Docker?

1. **Question**: What is Docker?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Docker packages an application and its dependencies into isolated containers that share the host kernel.
6. **Detailed explanation**: Docker packages an application and its dependencies into isolated containers that share the host kernel. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “What is Docker?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Docker packages an application and its dependencies into isolated containers that share the host kernel.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 439. Container vs virtual machine?

1. **Question**: Container vs virtual machine?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: A container shares the host kernel and starts quickly with low overhead. A VM includes a guest OS and stronger isolation at higher resource cost.
6. **Detailed explanation**: A container shares the host kernel and starts quickly with low overhead. A VM includes a guest OS and stronger isolation at higher resource cost. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “Container vs virtual machine?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: A container shares the host kernel and starts quickly with low overhead. A VM includes a guest OS and stronger isolation at higher resource cost.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 440. Image vs container?

1. **Question**: Image vs container?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: An image is an immutable layered template; a container is a running instance with a writable layer and runtime configuration.
6. **Detailed explanation**: An image is an immutable layered template; a container is a running instance with a writable layer and runtime configuration. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “Image vs container?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: An image is an immutable layered template; a container is a running instance with a writable layer and runtime configuration.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 441. What is Dockerfile?

1. **Question**: What is Dockerfile?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: A Dockerfile is a declarative build recipe that creates an image from a base and ordered instructions.
6. **Detailed explanation**: A Dockerfile is a declarative build recipe that creates an image from a base and ordered instructions. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “What is Dockerfile?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: A Dockerfile is a declarative build recipe that creates an image from a base and ordered instructions.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 442. Explain common Dockerfile instructions.

1. **Question**: Explain common Dockerfile instructions.
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: FROM chooses a base, RUN executes build commands, COPY/ADD adds files, WORKDIR sets the directory, ENV sets variables, EXPOSE documents ports, USER drops privileges, and CMD/ENTRYPOINT define startup.
6. **Detailed explanation**: FROM chooses a base, RUN executes build commands, COPY/ADD adds files, WORKDIR sets the directory, ENV sets variables, EXPOSE documents ports, USER drops privileges, and CMD/ENTRYPOINT define startup. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “Explain common Dockerfile instructions.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: FROM chooses a base, RUN executes build commands, COPY/ADD adds files, WORKDIR sets the directory, ENV sets variables, EXPOSE documents ports, USER drops privileges, and CMD/ENTRYPOINT define startup.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 443. CMD vs ENTRYPOINT?

1. **Question**: CMD vs ENTRYPOINT?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: ENTRYPOINT defines the executable; CMD supplies default arguments or a default command. Exec form is preferred for signal handling.
6. **Detailed explanation**: ENTRYPOINT defines the executable; CMD supplies default arguments or a default command. Exec form is preferred for signal handling. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “CMD vs ENTRYPOINT?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: ENTRYPOINT defines the executable; CMD supplies default arguments or a default command. Exec form is preferred for signal handling.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 444. COPY vs ADD?

1. **Question**: COPY vs ADD?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: COPY copies local files. ADD also supports URLs and archive extraction; use COPY unless ADD’s extra behavior is required.
6. **Detailed explanation**: COPY copies local files. ADD also supports URLs and archive extraction; use COPY unless ADD’s extra behavior is required. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “COPY vs ADD?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: COPY copies local files. ADD also supports URLs and archive extraction; use COPY unless ADD’s extra behavior is required.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 445. What are Docker layers?

1. **Question**: What are Docker layers?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Each build instruction can create a layer. Immutable layers enable reuse and caching but excessive layers or files increase image size.
6. **Detailed explanation**: Each build instruction can create a layer. Immutable layers enable reuse and caching but excessive layers or files increase image size. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “What are Docker layers?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Each build instruction can create a layer. Immutable layers enable reuse and caching but excessive layers or files increase image size.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 446. How does Docker caching work?

1. **Question**: How does Docker caching work?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Docker reuses a layer when its instruction and inputs match the cache. Put stable dependency steps before frequently changing source steps.
6. **Detailed explanation**: Docker reuses a layer when its instruction and inputs match the cache. Put stable dependency steps before frequently changing source steps. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “How does Docker caching work?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Docker reuses a layer when its instruction and inputs match the cache. Put stable dependency steps before frequently changing source steps.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 447. What is a multi-stage build?

1. **Question**: What is a multi-stage build?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: A multi-stage build compiles in one stage and copies only runtime artifacts into a smaller final image.
6. **Detailed explanation**: A multi-stage build compiles in one stage and copies only runtime artifacts into a smaller final image. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “What is a multi-stage build?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: A multi-stage build compiles in one stage and copies only runtime artifacts into a smaller final image.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 448. How do you reduce Docker image size?

1. **Question**: How do you reduce Docker image size?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Use a minimal runtime base, multi-stage builds, .dockerignore, dependency cleanup, non-root users, and pinned versions.
6. **Detailed explanation**: Use a minimal runtime base, multi-stage builds, .dockerignore, dependency cleanup, non-root users, and pinned versions. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “How do you reduce Docker image size?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Use a minimal runtime base, multi-stage builds, .dockerignore, dependency cleanup, non-root users, and pinned versions.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 449. What are Docker volumes?

1. **Question**: What are Docker volumes?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Volumes are Docker-managed persistent storage independent of a container lifecycle.
6. **Detailed explanation**: Volumes are Docker-managed persistent storage independent of a container lifecycle. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “What are Docker volumes?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Volumes are Docker-managed persistent storage independent of a container lifecycle.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 450. Volume vs bind mount?

1. **Question**: Volume vs bind mount?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: A volume is managed by Docker; a bind mount maps a host path and is useful for development but couples the container to host layout.
6. **Detailed explanation**: A volume is managed by Docker; a bind mount maps a host path and is useful for development but couples the container to host layout. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “Volume vs bind mount?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: A volume is managed by Docker; a bind mount maps a host path and is useful for development but couples the container to host layout.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 451. What are Docker networks?

1. **Question**: What are Docker networks?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Docker networks provide isolated virtual networks and DNS-based service discovery between containers.
6. **Detailed explanation**: Docker networks provide isolated virtual networks and DNS-based service discovery between containers. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “What are Docker networks?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Docker networks provide isolated virtual networks and DNS-based service discovery between containers.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 452. How do containers communicate?

1. **Question**: How do containers communicate?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Containers communicate over shared networks using service names and exposed internal ports; publish ports only when external access is needed.
6. **Detailed explanation**: Containers communicate over shared networks using service names and exposed internal ports; publish ports only when external access is needed. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “How do containers communicate?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Containers communicate over shared networks using service names and exposed internal ports; publish ports only when external access is needed.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 453. What is Docker Compose?

1. **Question**: What is Docker Compose?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Compose defines multi-container applications, networks, volumes, and environment configuration in a declarative file.
6. **Detailed explanation**: Compose defines multi-container applications, networks, volumes, and environment configuration in a declarative file. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “What is Docker Compose?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Compose defines multi-container applications, networks, volumes, and environment configuration in a declarative file.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 454. How do you containerize a Spring Boot application?

1. **Question**: How do you containerize a Spring Boot application?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Build the JAR in a builder stage, copy it into a JRE/JDK runtime image, expose the application port, run as non-root, and configure health and memory limits.
6. **Detailed explanation**: Build the JAR in a builder stage, copy it into a JRE/JDK runtime image, expose the application port, run as non-root, and configure health and memory limits. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “How do you containerize a Spring Boot application?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Build the JAR in a builder stage, copy it into a JRE/JDK runtime image, expose the application port, run as non-root, and configure health and memory limits.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 455. How do you pass environment variables?

1. **Question**: How do you pass environment variables?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Pass non-secret configuration through environment variables or files; use a secret manager for credentials.
6. **Detailed explanation**: Pass non-secret configuration through environment variables or files; use a secret manager for credentials. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “How do you pass environment variables?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Pass non-secret configuration through environment variables or files; use a secret manager for credentials.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 456. How do you manage secrets?

1. **Question**: How do you manage secrets?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Inject secrets at runtime through orchestration or secret stores; do not bake them into images or layers.
6. **Detailed explanation**: Inject secrets at runtime through orchestration or secret stores; do not bake them into images or layers. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “How do you manage secrets?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Inject secrets at runtime through orchestration or secret stores; do not bake them into images or layers.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 457. How do you check container logs?

1. **Question**: How do you check container logs?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Use docker logs, structured application logs, and centralized aggregation for persistent searchable history.
6. **Detailed explanation**: Use docker logs, structured application logs, and centralized aggregation for persistent searchable history. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “How do you check container logs?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Use docker logs, structured application logs, and centralized aggregation for persistent searchable history.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 458. How do you debug a container that keeps restarting?

1. **Question**: How do you debug a container that keeps restarting?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Inspect status and exit code, logs, health checks, configuration, resource limits, and the command actually executed.
6. **Detailed explanation**: Inspect status and exit code, logs, health checks, configuration, resource limits, and the command actually executed. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “How do you debug a container that keeps restarting?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Inspect status and exit code, logs, health checks, configuration, resource limits, and the command actually executed.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 459. Why might a container exit immediately?

1. **Question**: Why might a container exit immediately?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: A container exits when its main process exits, crashes, receives a signal, or is misconfigured; backgrounding the main process is a common mistake.
6. **Detailed explanation**: A container exits when its main process exits, crashes, receives a signal, or is misconfigured; backgrounding the main process is a common mistake. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “Why might a container exit immediately?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: A container exits when its main process exits, crashes, receives a signal, or is misconfigured; backgrounding the main process is a common mistake.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 460. How do you check resource usage?

1. **Question**: How do you check resource usage?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Use docker stats, inspect, events, and host metrics to view CPU, memory, network, disk, and restart behavior.
6. **Detailed explanation**: Use docker stats, inspect, events, and host metrics to view CPU, memory, network, disk, and restart behavior. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “How do you check resource usage?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Use docker stats, inspect, events, and host metrics to view CPU, memory, network, disk, and restart behavior.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 461. How do you secure Docker images?

1. **Question**: How do you secure Docker images?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Use minimal trusted bases, non-root users, pinned dependencies, read-only filesystems where possible, dropped capabilities, and regular patching.
6. **Detailed explanation**: Use minimal trusted bases, non-root users, pinned dependencies, read-only filesystems where possible, dropped capabilities, and regular patching. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “How do you secure Docker images?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Use minimal trusted bases, non-root users, pinned dependencies, read-only filesystems where possible, dropped capabilities, and regular patching.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---

## 462. How do you scan images for vulnerabilities?

1. **Question**: How do you scan images for vulnerabilities?
2. **Difficulty**: Intermediate
3. **Topic**: Docker
4. **What interviewer is testing**: Whether you can build secure, reproducible images and operate containers under realistic constraints.
5. **Short interview answer (30–60 seconds)**: Scan images in CI and registries with vulnerability tools, triage exploitability, update bases, and block defined severity thresholds.
6. **Detailed explanation**: Scan images in CI and registries with vulnerability tools, triage exploitability, update bases, and block defined severity thresholds. Build, runtime, networking, storage, and security determine the operational behavior.
7. **How it works internally**: Docker builds layered images, then the runtime creates namespaces, cgroups, mounts, networks, and a process lifecycle for each container.
8. **Example**:

For “How do you scan images for vulnerabilities?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
USER 10001
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```




10. **Time & space complexity**: Discuss image size, build/cache time, startup time, CPU, memory, storage, and network costs.
11. **Real-world/project usage**: Use containers for local parity, CI builds, service packaging, deployments, and isolated dependencies.
12. **Common mistakes**: Running as root, baking secrets, using oversized bases, ignoring signals, unbounded logs, and relying on mutable latest tags.
13. **Advantages**: Reproducibility, isolation, fast startup, portability, and efficient packaging.
14. **Limitations**: Shared-kernel isolation, image and registry maintenance, storage/network complexity, and operational debugging.
15. **Comparison with related concepts**: Compare containers and VMs, volumes and bind mounts, CMD and ENTRYPOINT, and single- and multi-stage builds.
16. **Production considerations**: Scan images, pin versions, set limits, use health checks, secure runtime permissions, and collect logs and metrics.
17. **Possible follow-up questions**: What happens on restart, signal, image update, storage failure, or resource exhaustion?
18. **Senior-level follow-up questions**: How would you reduce supply-chain risk, optimize build time, and roll out a base-image update safely?
19. **Scenario-based question**: A container repeatedly restarts after deployment. Explain how you would inspect its process, logs, environment, health check, and limits.
20. **One-line revision note**: Scan images in CI and registries with vulnerability tools, triage exploitability, update bases, and block defined severity thresholds.
21. **Image visuals (if required)**: Image-layer and container-runtime diagrams are useful for internals.

---
