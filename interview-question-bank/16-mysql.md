# 16. MySQL

> Source range: questions 421–437
## 421. MySQL vs PostgreSQL?

1. **Question**: MySQL vs PostgreSQL?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: PostgreSQL offers broader advanced SQL and extensibility; MySQL is widely adopted and can be simpler to operate. Compare engine, workload, tooling, and team needs.
6. **Detailed explanation**: PostgreSQL offers broader advanced SQL and extensibility; MySQL is widely adopted and can be simpler to operate. Compare engine, workload, tooling, and team needs. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “MySQL vs PostgreSQL?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: PostgreSQL offers broader advanced SQL and extensibility; MySQL is widely adopted and can be simpler to operate. Compare engine, workload, tooling, and team needs.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 422. What is InnoDB?

1. **Question**: What is InnoDB?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: InnoDB is MySQL’s default transactional storage engine with clustered primary keys, row-level locks, MVCC, redo/undo logging, and foreign keys.
6. **Detailed explanation**: InnoDB is MySQL’s default transactional storage engine with clustered primary keys, row-level locks, MVCC, redo/undo logging, and foreign keys. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “What is InnoDB?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: InnoDB is MySQL’s default transactional storage engine with clustered primary keys, row-level locks, MVCC, redo/undo logging, and foreign keys.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 423. InnoDB vs MyISAM?

1. **Question**: InnoDB vs MyISAM?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: InnoDB supports transactions, row locks, and crash recovery. MyISAM is non-transactional with table-level locking and is legacy for most applications.
6. **Detailed explanation**: InnoDB supports transactions, row locks, and crash recovery. MyISAM is non-transactional with table-level locking and is legacy for most applications. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “InnoDB vs MyISAM?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: InnoDB supports transactions, row locks, and crash recovery. MyISAM is non-transactional with table-level locking and is legacy for most applications.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 424. How does MySQL indexing work?

1. **Question**: How does MySQL indexing work?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: MySQL indexes, primarily B-trees, organize key values so the engine can locate rows or satisfy covering queries without full scans.
6. **Detailed explanation**: MySQL indexes, primarily B-trees, organize key values so the engine can locate rows or satisfy covering queries without full scans. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “How does MySQL indexing work?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: MySQL indexes, primarily B-trees, organize key values so the engine can locate rows or satisfy covering queries without full scans.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 425. What is a covering index?

1. **Question**: What is a covering index?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: A covering index contains all columns needed by a query, allowing the engine to answer it from the index without table lookups.
6. **Detailed explanation**: A covering index contains all columns needed by a query, allowing the engine to answer it from the index without table lookups. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “What is a covering index?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: A covering index contains all columns needed by a query, allowing the engine to answer it from the index without table lookups.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 426. What is a composite index?

1. **Question**: What is a composite index?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: A composite index orders multiple columns; design the leading columns around equality, range, join, and ordering predicates.
6. **Detailed explanation**: A composite index orders multiple columns; design the leading columns around equality, range, join, and ordering predicates. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “What is a composite index?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: A composite index orders multiple columns; design the leading columns around equality, range, join, and ordering predicates.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 427. How does `EXPLAIN` help?

1. **Question**: How does `EXPLAIN` help?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: EXPLAIN shows access type, chosen indexes, row estimates, join order, and filtering so you can diagnose scans and poor plans.
6. **Detailed explanation**: EXPLAIN shows access type, chosen indexes, row estimates, join order, and filtering so you can diagnose scans and poor plans. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “How does `EXPLAIN` help?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: EXPLAIN shows access type, chosen indexes, row estimates, join order, and filtering so you can diagnose scans and poor plans.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 428. What is MVCC in MySQL?

1. **Question**: What is MVCC in MySQL?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: InnoDB MVCC lets transactions read consistent snapshots while writers create new versions and undo records.
6. **Detailed explanation**: InnoDB MVCC lets transactions read consistent snapshots while writers create new versions and undo records. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “What is MVCC in MySQL?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: InnoDB MVCC lets transactions read consistent snapshots while writers create new versions and undo records.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 429. How does InnoDB implement transactions?

1. **Question**: How does InnoDB implement transactions?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: InnoDB uses redo logs, undo logs, a buffer pool, locks, and two-phase commit coordination to provide transactional durability and recovery.
6. **Detailed explanation**: InnoDB uses redo logs, undo logs, a buffer pool, locks, and two-phase commit coordination to provide transactional durability and recovery. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “How does InnoDB implement transactions?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: InnoDB uses redo logs, undo logs, a buffer pool, locks, and two-phase commit coordination to provide transactional durability and recovery.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 430. What are database locks?

1. **Question**: What are database locks?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: Database locks protect rows, gaps, or tables from conflicting operations according to isolation and statement behavior.
6. **Detailed explanation**: Database locks protect rows, gaps, or tables from conflicting operations according to isolation and statement behavior. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “What are database locks?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: Database locks protect rows, gaps, or tables from conflicting operations according to isolation and statement behavior.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 431. Row-level vs table-level locking?

1. **Question**: Row-level vs table-level locking?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: Row locks allow more concurrency but have overhead; table locks are coarse and can block unrelated rows.
6. **Detailed explanation**: Row locks allow more concurrency but have overhead; table locks are coarse and can block unrelated rows. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “Row-level vs table-level locking?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: Row locks allow more concurrency but have overhead; table locks are coarse and can block unrelated rows.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 432. How do you identify slow queries?

1. **Question**: How do you identify slow queries?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: Use performance_schema, slow query logs, statement digests, EXPLAIN, waits, and resource metrics to locate slow queries.
6. **Detailed explanation**: Use performance_schema, slow query logs, statement digests, EXPLAIN, waits, and resource metrics to locate slow queries. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “How do you identify slow queries?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: Use performance_schema, slow query logs, statement digests, EXPLAIN, waits, and resource metrics to locate slow queries.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 433. What is the slow query log?

1. **Question**: What is the slow query log?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: The slow query log records statements exceeding configured thresholds and is a key source for workload analysis.
6. **Detailed explanation**: The slow query log records statements exceeding configured thresholds and is a key source for workload analysis. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “What is the slow query log?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: The slow query log records statements exceeding configured thresholds and is a key source for workload analysis.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 434. How do you optimize MySQL queries?

1. **Question**: How do you optimize MySQL queries?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: Improve predicates and indexes, reduce rows and columns, avoid functions on indexed columns, update statistics, and validate with EXPLAIN and measurements.
6. **Detailed explanation**: Improve predicates and indexes, reduce rows and columns, avoid functions on indexed columns, update statistics, and validate with EXPLAIN and measurements. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “How do you optimize MySQL queries?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: Improve predicates and indexes, reduce rows and columns, avoid functions on indexed columns, update statistics, and validate with EXPLAIN and measurements.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 435. What is replication?

1. **Question**: What is replication?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: Replication copies changes from a source to replicas using binlog events; modes and guarantees vary by configuration.
6. **Detailed explanation**: Replication copies changes from a source to replicas using binlog events; modes and guarantees vary by configuration. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “What is replication?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: Replication copies changes from a source to replicas using binlog events; modes and guarantees vary by configuration.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 436. What is read replica?

1. **Question**: What is read replica?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: A read replica serves read traffic and can provide reporting or failover support, but it may lag and should not receive stale-sensitive reads blindly.
6. **Detailed explanation**: A read replica serves read traffic and can provide reporting or failover support, but it may lag and should not receive stale-sensitive reads blindly. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “What is read replica?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: A read replica serves read traffic and can provide reporting or failover support, but it may lag and should not receive stale-sensitive reads blindly.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---

## 437. How do you handle database failover?

1. **Question**: How do you handle database failover?
2. **Difficulty**: Advanced
3. **Topic**: MySQL
4. **What interviewer is testing**: Whether you understand database behavior, operational trade-offs, and evidence-based troubleshooting.
5. **Short interview answer (30–60 seconds)**: Use managed failover or an orchestrated promotion process, verify replication health and data loss, redirect traffic, and test the runbook regularly.
6. **Detailed explanation**: Use managed failover or an orchestrated promotion process, verify replication health and data loss, redirect traffic, and test the runbook regularly. Storage, planner, locking, and operational implications determine the production behavior.
7. **How it works internally**: The database engine applies MVCC or locks, chooses an execution plan, reads indexes/pages, and records WAL or redo information as required.
8. **Example**:

For “How do you handle database failover?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: Discuss scan/index, sort, join, WAL, vacuum, network, and storage costs for the concrete operation.
11. **Real-world/project usage**: This appears in schema design, APIs, migrations, reporting, backups, replication, and incident response.
12. **Common mistakes**: Tuning without plans, ignoring statistics or bloat, using unsafe migrations, and assuming replicas or backups provide zero data loss.
13. **Advantages**: Mature transactional semantics, indexing, observability, and operational tooling.
14. **Limitations**: Locking and bloat, storage and replication cost, version-specific behavior, and operational maintenance.
15. **Comparison with related concepts**: Compare index types, MVCC and locks, views and materialized views, pooling, and replication modes.
16. **Production considerations**: Monitor plans, locks, bloat, connections, replication lag, backups, restore tests, and capacity.
17. **Possible follow-up questions**: What happens under concurrent writes, stale statistics, failover, long transactions, or a full disk?
18. **Senior-level follow-up questions**: How would you change schema or topology online, prove recovery objectives, and roll back safely?
19. **Scenario-based question**: Database latency or CPU spikes in production. Explain how you would inspect activity, plans, locks, I/O, and recent changes before mitigating.
20. **One-line revision note**: Use managed failover or an orchestrated promotion process, verify replication health and data loss, redirect traffic, and test the runbook regularly.
21. **Image visuals (if required)**: An MVCC, index, replication, or connection-pool diagram can clarify the answer.

---
