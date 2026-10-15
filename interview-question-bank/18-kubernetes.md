# 18. Kubernetes

> Source range: questions 463–507
## 463. What is Kubernetes?

1. **Question**: What is Kubernetes?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Kubernetes is a container-orchestration platform that schedules workloads, maintains desired state, provides service discovery, and automates rollout and recovery.
6. **Detailed explanation**: Kubernetes is a container-orchestration platform that schedules workloads, maintains desired state, provides service discovery, and automates rollout and recovery. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is Kubernetes?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Kubernetes is a container-orchestration platform that schedules workloads, maintains desired state, provides service discovery, and automates rollout and recovery.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 464. Why use Kubernetes?

1. **Question**: Why use Kubernetes?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: It provides declarative deployment, scheduling, scaling, service discovery, self-healing, and a consistent platform across environments.
6. **Detailed explanation**: It provides declarative deployment, scheduling, scaling, service discovery, self-healing, and a consistent platform across environments. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “Why use Kubernetes?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: It provides declarative deployment, scheduling, scaling, service discovery, self-healing, and a consistent platform across environments.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 465. Explain Kubernetes architecture.

1. **Question**: Explain Kubernetes architecture.
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A cluster has a control plane that stores desired state and makes decisions, plus worker nodes that run pods through kubelet and a container runtime.
6. **Detailed explanation**: A cluster has a control plane that stores desired state and makes decisions, plus worker nodes that run pods through kubelet and a container runtime. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “Explain Kubernetes architecture.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A cluster has a control plane that stores desired state and makes decisions, plus worker nodes that run pods through kubelet and a container runtime.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 466. What are control plane components?

1. **Question**: What are control plane components?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Control-plane components include kube-apiserver, etcd, scheduler, and controller manager; cloud controllers may integrate provider resources.
6. **Detailed explanation**: Control-plane components include kube-apiserver, etcd, scheduler, and controller manager; cloud controllers may integrate provider resources. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What are control plane components?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Control-plane components include kube-apiserver, etcd, scheduler, and controller manager; cloud controllers may integrate provider resources.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 467. What is kube-apiserver?

1. **Question**: What is kube-apiserver?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: kube-apiserver is the authenticated, authorized HTTP entry point for Kubernetes API operations and admission processing.
6. **Detailed explanation**: kube-apiserver is the authenticated, authorized HTTP entry point for Kubernetes API operations and admission processing. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is kube-apiserver?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: kube-apiserver is the authenticated, authorized HTTP entry point for Kubernetes API operations and admission processing.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 468. What is etcd?

1. **Question**: What is etcd?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: etcd is the strongly consistent key-value store containing cluster state; protect it, back it up, and control access.
6. **Detailed explanation**: etcd is the strongly consistent key-value store containing cluster state; protect it, back it up, and control access. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is etcd?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: etcd is the strongly consistent key-value store containing cluster state; protect it, back it up, and control access.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 469. What is scheduler?

1. **Question**: What is scheduler?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: The scheduler selects a suitable node for unscheduled pods using requests, constraints, affinity, taints, and scoring.
6. **Detailed explanation**: The scheduler selects a suitable node for unscheduled pods using requests, constraints, affinity, taints, and scoring. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is scheduler?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: The scheduler selects a suitable node for unscheduled pods using requests, constraints, affinity, taints, and scoring.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 470. What is controller manager?

1. **Question**: What is controller manager?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: The controller manager runs controllers that compare observed state with desired state and create updates to converge them.
6. **Detailed explanation**: The controller manager runs controllers that compare observed state with desired state and create updates to converge them. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is controller manager?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: The controller manager runs controllers that compare observed state with desired state and create updates to converge them.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 471. What is kubelet?

1. **Question**: What is kubelet?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: kubelet runs on each node, starts containers through the runtime, reports status, and executes probes.
6. **Detailed explanation**: kubelet runs on each node, starts containers through the runtime, reports status, and executes probes. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is kubelet?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: kubelet runs on each node, starts containers through the runtime, reports status, and executes probes.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 472. What is a Pod?

1. **Question**: What is a Pod?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A Pod is the smallest deployable unit and contains one or more co-located containers sharing network and volumes.
6. **Detailed explanation**: A Pod is the smallest deployable unit and contains one or more co-located containers sharing network and volumes. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is a Pod?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A Pod is the smallest deployable unit and contains one or more co-located containers sharing network and volumes.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 473. Pod vs container?

1. **Question**: Pod vs container?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A pod provides lifecycle, networking, and storage context; a container is one process environment inside that pod.
6. **Detailed explanation**: A pod provides lifecycle, networking, and storage context; a container is one process environment inside that pod. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “Pod vs container?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A pod provides lifecycle, networking, and storage context; a container is one process environment inside that pod.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 474. What is Deployment?

1. **Question**: What is Deployment?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A Deployment manages replicated stateless pods through ReplicaSets and supports rolling updates and rollback.
6. **Detailed explanation**: A Deployment manages replicated stateless pods through ReplicaSets and supports rolling updates and rollback. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is Deployment?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A Deployment manages replicated stateless pods through ReplicaSets and supports rolling updates and rollback.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 475. Deployment vs StatefulSet?

1. **Question**: Deployment vs StatefulSet?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A StatefulSet provides stable identities and ordered storage/lifecycle for stateful workloads; a Deployment treats replicas as interchangeable.
6. **Detailed explanation**: A StatefulSet provides stable identities and ordered storage/lifecycle for stateful workloads; a Deployment treats replicas as interchangeable. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “Deployment vs StatefulSet?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A StatefulSet provides stable identities and ordered storage/lifecycle for stateful workloads; a Deployment treats replicas as interchangeable.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 476. Deployment vs DaemonSet?

1. **Question**: Deployment vs DaemonSet?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A DaemonSet ensures a pod runs on selected nodes, commonly for agents. A Deployment manages a desired replica count independent of node count.
6. **Detailed explanation**: A DaemonSet ensures a pod runs on selected nodes, commonly for agents. A Deployment manages a desired replica count independent of node count. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “Deployment vs DaemonSet?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A DaemonSet ensures a pod runs on selected nodes, commonly for agents. A Deployment manages a desired replica count independent of node count.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 477. What is ReplicaSet?

1. **Question**: What is ReplicaSet?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A ReplicaSet maintains a specified number of matching pod replicas and is normally managed by a Deployment.
6. **Detailed explanation**: A ReplicaSet maintains a specified number of matching pod replicas and is normally managed by a Deployment. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is ReplicaSet?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A ReplicaSet maintains a specified number of matching pod replicas and is normally managed by a Deployment.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 478. What is Service?

1. **Question**: What is Service?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A Service provides a stable virtual IP and DNS name that selects matching pods and load-balances traffic.
6. **Detailed explanation**: A Service provides a stable virtual IP and DNS name that selects matching pods and load-balances traffic. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is Service?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A Service provides a stable virtual IP and DNS name that selects matching pods and load-balances traffic.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 479. ClusterIP vs NodePort vs LoadBalancer?

1. **Question**: ClusterIP vs NodePort vs LoadBalancer?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: ClusterIP is internal, NodePort exposes a port on nodes, and LoadBalancer requests an external provider load balancer.
6. **Detailed explanation**: ClusterIP is internal, NodePort exposes a port on nodes, and LoadBalancer requests an external provider load balancer. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “ClusterIP vs NodePort vs LoadBalancer?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: ClusterIP is internal, NodePort exposes a port on nodes, and LoadBalancer requests an external provider load balancer.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 480. What is Ingress?

1. **Question**: What is Ingress?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Ingress defines HTTP routing rules implemented by an ingress controller; it is not itself a data-plane load balancer.
6. **Detailed explanation**: Ingress defines HTTP routing rules implemented by an ingress controller; it is not itself a data-plane load balancer. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is Ingress?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Ingress defines HTTP routing rules implemented by an ingress controller; it is not itself a data-plane load balancer.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 481. Ingress vs LoadBalancer?

1. **Question**: Ingress vs LoadBalancer?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A LoadBalancer exposes a service externally, usually at transport level. Ingress provides host/path routing and TLS for HTTP.
6. **Detailed explanation**: A LoadBalancer exposes a service externally, usually at transport level. Ingress provides host/path routing and TLS for HTTP. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “Ingress vs LoadBalancer?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A LoadBalancer exposes a service externally, usually at transport level. Ingress provides host/path routing and TLS for HTTP.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 482. ConfigMap vs Secret?

1. **Question**: ConfigMap vs Secret?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: ConfigMap stores non-sensitive configuration. Secret stores sensitive values but still requires encryption at rest and access control.
6. **Detailed explanation**: ConfigMap stores non-sensitive configuration. Secret stores sensitive values but still requires encryption at rest and access control. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “ConfigMap vs Secret?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: ConfigMap stores non-sensitive configuration. Secret stores sensitive values but still requires encryption at rest and access control.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 483. What is PersistentVolume?

1. **Question**: What is PersistentVolume?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A PersistentVolume represents provisioned storage with capacity and access modes independent of a pod.
6. **Detailed explanation**: A PersistentVolume represents provisioned storage with capacity and access modes independent of a pod. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is PersistentVolume?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A PersistentVolume represents provisioned storage with capacity and access modes independent of a pod.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 484. PV vs PVC?

1. **Question**: PV vs PVC?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A PVC is a request for storage that binds to a suitable PV and is consumed by a pod.
6. **Detailed explanation**: A PVC is a request for storage that binds to a suitable PV and is consumed by a pod. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “PV vs PVC?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A PVC is a request for storage that binds to a suitable PV and is consumed by a pod.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 485. What are namespaces?

1. **Question**: What are namespaces?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Namespaces provide logical isolation and scopes for names, policies, quotas, and access.
6. **Detailed explanation**: Namespaces provide logical isolation and scopes for names, policies, quotas, and access. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What are namespaces?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Namespaces provide logical isolation and scopes for names, policies, quotas, and access.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 486. What are labels and selectors?

1. **Question**: What are labels and selectors?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Labels attach identifying metadata; selectors choose objects by label for controllers and services.
6. **Detailed explanation**: Labels attach identifying metadata; selectors choose objects by label for controllers and services. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What are labels and selectors?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Labels attach identifying metadata; selectors choose objects by label for controllers and services.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 487. What are annotations?

1. **Question**: What are annotations?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Annotations store non-identifying metadata for tools and controllers and are not normally used for selection.
6. **Detailed explanation**: Annotations store non-identifying metadata for tools and controllers and are not normally used for selection. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What are annotations?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Annotations store non-identifying metadata for tools and controllers and are not normally used for selection.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 488. What are liveness, readiness, and startup probes?

1. **Question**: What are liveness, readiness, and startup probes?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Startup probes delay liveness/readiness checks until initialization completes. Liveness restarts unhealthy containers; readiness removes them from service endpoints.
6. **Detailed explanation**: Startup probes delay liveness/readiness checks until initialization completes. Liveness restarts unhealthy containers; readiness removes them from service endpoints. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What are liveness, readiness, and startup probes?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Startup probes delay liveness/readiness checks until initialization completes. Liveness restarts unhealthy containers; readiness removes them from service endpoints.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 489. What happens if a readiness probe fails?

1. **Question**: What happens if a readiness probe fails?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A failed readiness probe marks the pod unready, so traffic is removed while the container continues running.
6. **Detailed explanation**: A failed readiness probe marks the pod unready, so traffic is removed while the container continues running. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What happens if a readiness probe fails?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A failed readiness probe marks the pod unready, so traffic is removed while the container continues running.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 490. What happens if a liveness probe fails?

1. **Question**: What happens if a liveness probe fails?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A failed liveness probe causes kubelet to restart the container after the configured failure threshold.
6. **Detailed explanation**: A failed liveness probe causes kubelet to restart the container after the configured failure threshold. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What happens if a liveness probe fails?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A failed liveness probe causes kubelet to restart the container after the configured failure threshold.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 491. What are resource requests and limits?

1. **Question**: What are resource requests and limits?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Requests influence scheduling and guaranteed capacity; limits cap runtime resource use and can trigger throttling or termination.
6. **Detailed explanation**: Requests influence scheduling and guaranteed capacity; limits cap runtime resource use and can trigger throttling or termination. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What are resource requests and limits?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Requests influence scheduling and guaranteed capacity; limits cap runtime resource use and can trigger throttling or termination.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 492. What happens when a container exceeds its memory limit?

1. **Question**: What happens when a container exceeds its memory limit?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Exceeding a memory limit can cause the kernel to kill the container; CPU limits generally throttle instead.
6. **Detailed explanation**: Exceeding a memory limit can cause the kernel to kill the container; CPU limits generally throttle instead. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What happens when a container exceeds its memory limit?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Exceeding a memory limit can cause the kernel to kill the container; CPU limits generally throttle instead.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 493. What is OOMKilled?

1. **Question**: What is OOMKilled?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: OOMKilled means the container was terminated because it exceeded its memory limit or the node experienced memory pressure.
6. **Detailed explanation**: OOMKilled means the container was terminated because it exceeded its memory limit or the node experienced memory pressure. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is OOMKilled?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: OOMKilled means the container was terminated because it exceeded its memory limit or the node experienced memory pressure.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 494. What is CrashLoopBackOff?

1. **Question**: What is CrashLoopBackOff?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: CrashLoopBackOff means Kubernetes repeatedly restarted a container and is backing off between attempts.
6. **Detailed explanation**: CrashLoopBackOff means Kubernetes repeatedly restarted a container and is backing off between attempts. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is CrashLoopBackOff?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: CrashLoopBackOff means Kubernetes repeatedly restarted a container and is backing off between attempts.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 495. How do you troubleshoot CrashLoopBackOff?

1. **Question**: How do you troubleshoot CrashLoopBackOff?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Inspect describe output, current and previous logs, exit codes, events, probes, configuration, secrets, dependencies, and resource limits.
6. **Detailed explanation**: Inspect describe output, current and previous logs, exit codes, events, probes, configuration, secrets, dependencies, and resource limits. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “How do you troubleshoot CrashLoopBackOff?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Inspect describe output, current and previous logs, exit codes, events, probes, configuration, secrets, dependencies, and resource limits.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 496. What is ImagePullBackOff?

1. **Question**: What is ImagePullBackOff?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: ImagePullBackOff means the kubelet cannot pull the image and is increasing retry delays; check name, tag, registry credentials, network, and architecture.
6. **Detailed explanation**: ImagePullBackOff means the kubelet cannot pull the image and is increasing retry delays; check name, tag, registry credentials, network, and architecture. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is ImagePullBackOff?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: ImagePullBackOff means the kubelet cannot pull the image and is increasing retry delays; check name, tag, registry credentials, network, and architecture.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 497. What is HPA?

1. **Question**: What is HPA?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: HPA adjusts replica count based on metrics such as CPU, memory, or custom signals within configured bounds.
6. **Detailed explanation**: HPA adjusts replica count based on metrics such as CPU, memory, or custom signals within configured bounds. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is HPA?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: HPA adjusts replica count based on metrics such as CPU, memory, or custom signals within configured bounds.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 498. How does autoscaling work?

1. **Question**: How does autoscaling work?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Autoscaling observes metrics and changes replicas or nodes toward a target, subject to stabilization, requests, limits, and capacity.
6. **Detailed explanation**: Autoscaling observes metrics and changes replicas or nodes toward a target, subject to stabilization, requests, limits, and capacity. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “How does autoscaling work?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Autoscaling observes metrics and changes replicas or nodes toward a target, subject to stabilization, requests, limits, and capacity.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 499. What is rolling deployment?

1. **Question**: What is rolling deployment?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: A rolling deployment gradually replaces old pods while keeping available capacity according to strategy settings.
6. **Detailed explanation**: A rolling deployment gradually replaces old pods while keeping available capacity according to strategy settings. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is rolling deployment?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: A rolling deployment gradually replaces old pods while keeping available capacity according to strategy settings.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 500. How do you perform zero-downtime deployment?

1. **Question**: How do you perform zero-downtime deployment?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Use multiple replicas, readiness probes, graceful termination, backward-compatible changes, capacity headroom, and a controlled rolling or canary strategy.
6. **Detailed explanation**: Use multiple replicas, readiness probes, graceful termination, backward-compatible changes, capacity headroom, and a controlled rolling or canary strategy. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “How do you perform zero-downtime deployment?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Use multiple replicas, readiness probes, graceful termination, backward-compatible changes, capacity headroom, and a controlled rolling or canary strategy.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 501. What is rollback?

1. **Question**: What is rollback?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Rollback restores a prior Deployment revision or release after validating health and impact.
6. **Detailed explanation**: Rollback restores a prior Deployment revision or release after validating health and impact. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is rollback?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Rollback restores a prior Deployment revision or release after validating health and impact.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 502. How do you view Kubernetes logs?

1. **Question**: How do you view Kubernetes logs?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Use kubectl logs, -f, --previous, label selectors, and centralized logging for pod output.
6. **Detailed explanation**: Use kubectl logs, -f, --previous, label selectors, and centralized logging for pod output. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “How do you view Kubernetes logs?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Use kubectl logs, -f, --previous, label selectors, and centralized logging for pod output.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 503. How do you debug a Pod?

1. **Question**: How do you debug a Pod?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Use kubectl describe, logs, exec, debug, events, resource metrics, and manifests to isolate scheduling, networking, process, and dependency issues.
6. **Detailed explanation**: Use kubectl describe, logs, exec, debug, events, resource metrics, and manifests to isolate scheduling, networking, process, and dependency issues. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “How do you debug a Pod?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Use kubectl describe, logs, exec, debug, events, resource metrics, and manifests to isolate scheduling, networking, process, and dependency issues.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 504. How do you secure Kubernetes workloads?

1. **Question**: How do you secure Kubernetes workloads?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Use RBAC, network policies, pod security controls, image scanning, non-root containers, secret management, patching, and least privilege.
6. **Detailed explanation**: Use RBAC, network policies, pod security controls, image scanning, non-root containers, secret management, patching, and least privilege. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “How do you secure Kubernetes workloads?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Use RBAC, network policies, pod security controls, image scanning, non-root containers, secret management, patching, and least privilege.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 505. What is RBAC in Kubernetes?

1. **Question**: What is RBAC in Kubernetes?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Kubernetes RBAC grants verbs on resources to subjects through Roles/ClusterRoles and bindings.
6. **Detailed explanation**: Kubernetes RBAC grants verbs on resources to subjects through Roles/ClusterRoles and bindings. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What is RBAC in Kubernetes?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Kubernetes RBAC grants verbs on resources to subjects through Roles/ClusterRoles and bindings.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 506. What are Helm charts?

1. **Question**: What are Helm charts?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: Helm charts package parameterized Kubernetes manifests with versioned releases and upgrade/rollback support.
6. **Detailed explanation**: Helm charts package parameterized Kubernetes manifests with versioned releases and upgrade/rollback support. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What are Helm charts?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: Helm charts package parameterized Kubernetes manifests with versioned releases and upgrade/rollback support.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---

## 507. What happens internally when you execute `kubectl apply`?

1. **Question**: What happens internally when you execute `kubectl apply`?
2. **Difficulty**: Advanced
3. **Topic**: Kubernetes
4. **What interviewer is testing**: Whether you understand declarative orchestration, cluster control flow, workload health, security, and production troubleshooting.
5. **Short interview answer (30–60 seconds)**: kubectl apply calculates the desired object, authenticates to the API server, runs admission, stores the object, and controllers reconcile it toward the desired state.
6. **Detailed explanation**: kubectl apply calculates the desired object, authenticates to the API server, runs admission, stores the object, and controllers reconcile it toward the desired state. Controller, node, networking, and resource behavior determine the operational result.
7. **How it works internally**: The API server stores desired state, controllers reconcile it, the scheduler assigns pods, and kubelet/container runtime enforce execution on nodes.
8. **Example**:

For “What happens internally when you execute `kubectl apply`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app
spec:
  replicas: 2
  selector:
    matchLabels: {app: app}
  template:
    metadata: {labels: {app: app}}
    spec:
      containers:
        - name: app
          image: example/app:1.0.0
```




10. **Time & space complexity**: Include scheduling, reconciliation, image pull, startup, network, storage, and scaling costs where relevant.
11. **Real-world/project usage**: This governs deployment, service discovery, scaling, health, security, configuration, and incident response.
12. **Common mistakes**: Missing requests or probes, exposing secrets, relying on latest tags, ignoring PDBs and termination, and debugging only the application logs.
13. **Advantages**: Declarative recovery, portable deployment, scaling, service discovery, and a rich operational ecosystem.
14. **Limitations**: Significant complexity, control-plane and networking dependencies, resource overhead, and a steep troubleshooting surface.
15. **Comparison with related concepts**: Compare Deployments, StatefulSets, DaemonSets, Services, Ingress, probes, and resource requests/limits.
16. **Production considerations**: Use GitOps or reviewed manifests, least privilege, resource budgets, backups, observability, disruption policy, and tested rollback.
17. **Possible follow-up questions**: What happens when a probe fails, a node dies, a secret is missing, or a rollout stalls?
18. **Senior-level follow-up questions**: How would you design multi-zone availability, upgrade the cluster, or contain a noisy workload?
19. **Scenario-based question**: A deployment shows CrashLoopBackOff or OOMKilled. The diagnosis follows evidence from events, logs, probes, resources, dependencies, and the resulting remediation.
20. **One-line revision note**: kubectl apply calculates the desired object, authenticates to the API server, runs admission, stores the object, and controllers reconcile it toward the desired state.
21. **Image visuals (if required)**: Control-plane, pod-network, rollout, or probe-state diagrams are useful.

---
