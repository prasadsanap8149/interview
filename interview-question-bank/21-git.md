# 21. Git

> Source range: questions 569–586
## 569. What is Git?

1. **Question**: What is Git?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: Git is a distributed version-control system that records snapshots of files in commits and supports branching, merging, and collaboration.
6. **Detailed explanation**: Git is a distributed version-control system that records snapshots of files in commits and supports branching, merging, and collaboration. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “What is Git?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: Git is a distributed version-control system that records snapshots of files in commits and supports branching, merging, and collaboration.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 570. Git vs GitHub/GitLab?

1. **Question**: Git vs GitHub/GitLab?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: Git is the version-control tool; GitHub and GitLab are hosted collaboration platforms providing repositories, review, issues, and CI/CD.
6. **Detailed explanation**: Git is the version-control tool; GitHub and GitLab are hosted collaboration platforms providing repositories, review, issues, and CI/CD. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “Git vs GitHub/GitLab?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: Git is the version-control tool; GitHub and GitLab are hosted collaboration platforms providing repositories, review, issues, and CI/CD.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 571. `git fetch` vs `git pull`?

1. **Question**: `git fetch` vs `git pull`?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: fetch downloads remote refs without changing the current branch. pull fetches and then integrates the configured upstream changes.
6. **Detailed explanation**: fetch downloads remote refs without changing the current branch. pull fetches and then integrates the configured upstream changes. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “`git fetch` vs `git pull`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: fetch downloads remote refs without changing the current branch. pull fetches and then integrates the configured upstream changes.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 572. merge vs rebase?

1. **Question**: merge vs rebase?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: merge creates a merge commit or fast-forward preserving branch histories. rebase replays commits on a new base and creates new commit IDs.
6. **Detailed explanation**: merge creates a merge commit or fast-forward preserving branch histories. rebase replays commits on a new base and creates new commit IDs. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “merge vs rebase?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: merge creates a merge commit or fast-forward preserving branch histories. rebase replays commits on a new base and creates new commit IDs.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 573. What is cherry-pick?

1. **Question**: What is cherry-pick?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: cherry-pick applies the changes from selected commits onto the current branch, useful for targeted fixes but requiring conflict and duplicate-history care.
6. **Detailed explanation**: cherry-pick applies the changes from selected commits onto the current branch, useful for targeted fixes but requiring conflict and duplicate-history care. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “What is cherry-pick?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: cherry-pick applies the changes from selected commits onto the current branch, useful for targeted fixes but requiring conflict and duplicate-history care.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 574. What is stash?

1. **Question**: What is stash?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: stash temporarily saves uncommitted changes so you can switch context; apply or pop restores them and may conflict.
6. **Detailed explanation**: stash temporarily saves uncommitted changes so you can switch context; apply or pop restores them and may conflict. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “What is stash?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: stash temporarily saves uncommitted changes so you can switch context; apply or pop restores them and may conflict.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 575. reset vs revert?

1. **Question**: reset vs revert?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: reset moves branch history or the index/worktree depending on mode; revert creates a new commit undoing an existing commit and is safer for shared history.
6. **Detailed explanation**: reset moves branch history or the index/worktree depending on mode; revert creates a new commit undoing an existing commit and is safer for shared history. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “reset vs revert?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: reset moves branch history or the index/worktree depending on mode; revert creates a new commit undoing an existing commit and is safer for shared history.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 576. soft vs mixed vs hard reset?

1. **Question**: soft vs mixed vs hard reset?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: Soft reset moves HEAD only; mixed also resets the index; hard resets index and working tree and discards uncommitted changes.
6. **Detailed explanation**: Soft reset moves HEAD only; mixed also resets the index; hard resets index and working tree and discards uncommitted changes. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “soft vs mixed vs hard reset?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: Soft reset moves HEAD only; mixed also resets the index; hard resets index and working tree and discards uncommitted changes.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 577. What is HEAD?

1. **Question**: What is HEAD?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: HEAD identifies the current checkout, usually the current branch tip or commit.
6. **Detailed explanation**: HEAD identifies the current checkout, usually the current branch tip or commit. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “What is HEAD?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: HEAD identifies the current checkout, usually the current branch tip or commit.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 578. What is detached HEAD?

1. **Question**: What is detached HEAD?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: Detached HEAD means HEAD points directly to a commit rather than a branch; create a branch if you need to preserve new commits.
6. **Detailed explanation**: Detached HEAD means HEAD points directly to a commit rather than a branch; create a branch if you need to preserve new commits. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “What is detached HEAD?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: Detached HEAD means HEAD points directly to a commit rather than a branch; create a branch if you need to preserve new commits.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 579. How do you resolve merge conflicts?

1. **Question**: How do you resolve merge conflicts?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: Resolve conflicts by understanding both sides, editing markers, testing, staging resolved files, and continuing or completing the merge/rebase.
6. **Detailed explanation**: Resolve conflicts by understanding both sides, editing markers, testing, staging resolved files, and continuing or completing the merge/rebase. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “How do you resolve merge conflicts?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: Resolve conflicts by understanding both sides, editing markers, testing, staging resolved files, and continuing or completing the merge/rebase.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 580. What is squash?

1. **Question**: What is squash?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: Squash combines several commits into one logical commit to produce a cleaner review or release history.
6. **Detailed explanation**: Squash combines several commits into one logical commit to produce a cleaner review or release history. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “What is squash?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: Squash combines several commits into one logical commit to produce a cleaner review or release history.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 581. What is GitFlow?

1. **Question**: What is GitFlow?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: GitFlow uses long-lived main/develop branches plus feature, release, and hotfix branches; teams often prefer simpler trunk-based variants.
6. **Detailed explanation**: GitFlow uses long-lived main/develop branches plus feature, release, and hotfix branches; teams often prefer simpler trunk-based variants. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “What is GitFlow?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: GitFlow uses long-lived main/develop branches plus feature, release, and hotfix branches; teams often prefer simpler trunk-based variants.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 582. What branching strategy have you used?

1. **Question**: What branching strategy have you used?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: Choose a strategy based on release cadence, team size, CI maturity, and rollback needs; keep branches short-lived and integrate frequently.
6. **Detailed explanation**: Choose a strategy based on release cadence, team size, CI maturity, and rollback needs; keep branches short-lived and integrate frequently. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “What branching strategy have you used?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: Choose a strategy based on release cadence, team size, CI maturity, and rollback needs; keep branches short-lived and integrate frequently.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 583. How do you undo a pushed commit safely?

1. **Question**: How do you undo a pushed commit safely?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: Revert a pushed commit with a new commit; coordinate force-pushes only on protected, private branches with explicit agreement.
6. **Detailed explanation**: Revert a pushed commit with a new commit; coordinate force-pushes only on protected, private branches with explicit agreement. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “How do you undo a pushed commit safely?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: Revert a pushed commit with a new commit; coordinate force-pushes only on protected, private branches with explicit agreement.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 584. How do you find which commit introduced a bug?

1. **Question**: How do you find which commit introduced a bug?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: Use git log -S/-G, blame, bisect, and targeted tests to find the introducing commit.
6. **Detailed explanation**: Use git log -S/-G, blame, bisect, and targeted tests to find the introducing commit. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “How do you find which commit introduced a bug?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: Use git log -S/-G, blame, bisect, and targeted tests to find the introducing commit.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 585. What is `git bisect`?

1. **Question**: What is `git bisect`?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: git bisect performs a binary search across commits using good/bad markers and a reproducible test.
6. **Detailed explanation**: git bisect performs a binary search across commits using good/bad markers and a reproducible test. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “What is `git bisect`?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: git bisect performs a binary search across commits using good/bad markers and a reproducible test.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---

## 586. How do you manage release and hotfix branches?

1. **Question**: How do you manage release and hotfix branches?
2. **Difficulty**: Advanced
3. **Topic**: Git
4. **What interviewer is testing**: Whether you can apply the platform or workflow safely in a real engineering environment.
5. **Short interview answer (30–60 seconds)**: Use protected main/release branches, reviewed changes, automated checks, tagged releases, and isolated hotfixes merged back into active lines.
6. **Detailed explanation**: Use protected main/release branches, reviewed changes, automated checks, tagged releases, and isolated hotfixes merged back into active lines. Security, reliability, compatibility, and operational trade-offs determine whether this choice is suitable.
7. **How it works internally**: The platform or tool reconciles declared configuration and executes the required control-plane, data-plane, or repository operations.
8. **Example**:

For “How do you manage release and hotfix branches?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```bash
git status
git log --oneline --decorate -10
git diff --check
```




10. **Time & space complexity**: The concrete operation cost includes network, storage, build, or repository effects where applicable.
11. **Real-world/project usage**: This governs deployment, identity, networking, collaboration, release management, and incident recovery.
12. **Common mistakes**: Broad permissions, unreviewed destructive changes, unbounded resources, missing backups, or unclear ownership and rollback.
13. **Advantages**: Automation, repeatability, managed capabilities, and improved collaboration when conventions are followed.
14. **Limitations**: Platform coupling, configuration complexity, hidden defaults, and failure modes that require operational expertise.
15. **Comparison with related concepts**: Compare the closest platform services or workflow commands by ownership, consistency, security, and use case.
16. **Production considerations**: Use least privilege, reviews, audit trails, monitoring, backups, compatibility checks, and documented recovery.
17. **Possible follow-up questions**: What happens on failure, retry, rollback, conflict, quota exhaustion, or credential loss?
18. **Senior-level follow-up questions**: How would you migrate, standardize, govern, and measure this across teams?
19. **Scenario-based question**: A deployment or change fails after release. Explain how you would inspect evidence, contain impact, roll back, and prevent recurrence.
20. **One-line revision note**: Use protected main/release branches, reviewed changes, automated checks, tagged releases, and isolated hotfixes merged back into active lines.
21. **Image visuals (if required)**: A platform topology or Git history diagram may clarify the answer.

---
