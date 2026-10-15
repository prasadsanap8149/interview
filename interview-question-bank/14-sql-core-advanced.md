# 14. SQL — Core & Advanced

> Source range: questions 349–392
## 349. DDL vs DML vs DCL vs TCL?

1. **Question**: DDL vs DML vs DCL vs TCL?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: DDL defines schema, DML changes data, DCL controls privileges, and TCL controls transactions.
6. **Detailed explanation**: DDL defines schema, DML changes data, DCL controls privileges, and TCL controls transactions. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “DDL vs DML vs DCL vs TCL?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: DDL defines schema, DML changes data, DCL controls privileges, and TCL controls transactions.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 350. DELETE vs TRUNCATE vs DROP?

1. **Question**: DELETE vs TRUNCATE vs DROP?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: DELETE removes selected rows and is transactional in typical databases. TRUNCATE removes all rows efficiently with database-specific logging and rollback semantics. DROP removes the object itself.
6. **Detailed explanation**: DELETE removes selected rows and is transactional in typical databases. TRUNCATE removes all rows efficiently with database-specific logging and rollback semantics. DROP removes the object itself. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “DELETE vs TRUNCATE vs DROP?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: DELETE removes selected rows and is transactional in typical databases. TRUNCATE removes all rows efficiently with database-specific logging and rollback semantics. DROP removes the object itself.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 351. WHERE vs HAVING?

1. **Question**: WHERE vs HAVING?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: WHERE filters rows before grouping; HAVING filters groups after aggregation.
6. **Detailed explanation**: WHERE filters rows before grouping; HAVING filters groups after aggregation. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “WHERE vs HAVING?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: WHERE filters rows before grouping; HAVING filters groups after aggregation.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 352. GROUP BY?

1. **Question**: GROUP BY?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: GROUP BY forms groups so aggregate functions such as COUNT, SUM, and MAX can be calculated per group.
6. **Detailed explanation**: GROUP BY forms groups so aggregate functions such as COUNT, SUM, and MAX can be calculated per group. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “GROUP BY?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: GROUP BY forms groups so aggregate functions such as COUNT, SUM, and MAX can be calculated per group.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 353. UNION vs UNION ALL?

1. **Question**: UNION vs UNION ALL?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: UNION removes duplicates between result sets; UNION ALL concatenates them without duplicate elimination and is usually faster.
6. **Detailed explanation**: UNION removes duplicates between result sets; UNION ALL concatenates them without duplicate elimination and is usually faster. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “UNION vs UNION ALL?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: UNION removes duplicates between result sets; UNION ALL concatenates them without duplicate elimination and is usually faster.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 354. INNER JOIN vs LEFT JOIN vs RIGHT JOIN vs FULL JOIN?

1. **Question**: INNER JOIN vs LEFT JOIN vs RIGHT JOIN vs FULL JOIN?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: INNER JOIN returns matches; LEFT JOIN keeps all left rows; RIGHT JOIN keeps all right rows; FULL JOIN keeps unmatched rows from both sides where supported.
6. **Detailed explanation**: INNER JOIN returns matches; LEFT JOIN keeps all left rows; RIGHT JOIN keeps all right rows; FULL JOIN keeps unmatched rows from both sides where supported. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “INNER JOIN vs LEFT JOIN vs RIGHT JOIN vs FULL JOIN?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: INNER JOIN returns matches; LEFT JOIN keeps all left rows; RIGHT JOIN keeps all right rows; FULL JOIN keeps unmatched rows from both sides where supported.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 355. Subquery vs JOIN?

1. **Question**: Subquery vs JOIN?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A JOIN combines related rows and is often easier for the optimizer; a subquery expresses a nested condition or calculation. Choose based on clarity and plan quality.
6. **Detailed explanation**: A JOIN combines related rows and is often easier for the optimizer; a subquery expresses a nested condition or calculation. Choose based on clarity and plan quality. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “Subquery vs JOIN?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A JOIN combines related rows and is often easier for the optimizer; a subquery expresses a nested condition or calculation. Choose based on clarity and plan quality.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 356. EXISTS vs IN?

1. **Question**: EXISTS vs IN?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: EXISTS tests whether a matching row exists and can short-circuit; IN compares against a set and has null-related semantics to understand.
6. **Detailed explanation**: EXISTS tests whether a matching row exists and can short-circuit; IN compares against a set and has null-related semantics to understand. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “EXISTS vs IN?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: EXISTS tests whether a matching row exists and can short-circuit; IN compares against a set and has null-related semantics to understand.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 357. What is a correlated subquery?

1. **Question**: What is a correlated subquery?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A correlated subquery references columns from the outer query and may execute conceptually per outer row, though optimizers can rewrite it.
6. **Detailed explanation**: A correlated subquery references columns from the outer query and may execute conceptually per outer row, though optimizers can rewrite it. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What is a correlated subquery?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A correlated subquery references columns from the outer query and may execute conceptually per outer row, though optimizers can rewrite it.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 358. What is a CTE?

1. **Question**: What is a CTE?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A CTE names a subquery for readability, reuse, or recursive processing within one statement.
6. **Detailed explanation**: A CTE names a subquery for readability, reuse, or recursive processing within one statement. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What is a CTE?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A CTE names a subquery for readability, reuse, or recursive processing within one statement.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 359. What is a recursive CTE?

1. **Question**: What is a recursive CTE?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A recursive CTE contains an anchor query and recursive member to walk hierarchies or graphs until no more rows are produced.
6. **Detailed explanation**: A recursive CTE contains an anchor query and recursive member to walk hierarchies or graphs until no more rows are produced. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What is a recursive CTE?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A recursive CTE contains an anchor query and recursive member to walk hierarchies or graphs until no more rows are produced.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 360. What are window functions?

1. **Question**: What are window functions?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Window functions calculate across related rows without collapsing them, using OVER with partitioning and ordering.
6. **Detailed explanation**: Window functions calculate across related rows without collapsing them, using OVER with partitioning and ordering. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What are window functions?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Window functions calculate across related rows without collapsing them, using OVER with partitioning and ordering.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 361. ROW_NUMBER vs RANK vs DENSE_RANK?

1. **Question**: ROW_NUMBER vs RANK vs DENSE_RANK?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: ROW_NUMBER assigns unique sequence numbers; RANK leaves gaps after ties; DENSE_RANK does not leave gaps.
6. **Detailed explanation**: ROW_NUMBER assigns unique sequence numbers; RANK leaves gaps after ties; DENSE_RANK does not leave gaps. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “ROW_NUMBER vs RANK vs DENSE_RANK?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: ROW_NUMBER assigns unique sequence numbers; RANK leaves gaps after ties; DENSE_RANK does not leave gaps.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 362. What is PARTITION BY?

1. **Question**: What is PARTITION BY?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: PARTITION BY divides rows into independent windows for aggregation or ranking without grouping them into one output row.
6. **Detailed explanation**: PARTITION BY divides rows into independent windows for aggregation or ranking without grouping them into one output row. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What is PARTITION BY?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: PARTITION BY divides rows into independent windows for aggregation or ranking without grouping them into one output row.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 363. What is an index?

1. **Question**: What is an index?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: An index is an auxiliary data structure that helps locate rows without scanning the whole table.
6. **Detailed explanation**: An index is an auxiliary data structure that helps locate rows without scanning the whole table. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What is an index?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: An index is an auxiliary data structure that helps locate rows without scanning the whole table.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 364. How does an index work?

1. **Question**: How does an index work?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: The database traverses the index structure to find key ranges or values, then fetches matching rows or satisfies the query from the index itself.
6. **Detailed explanation**: The database traverses the index structure to find key ranges or values, then fetches matching rows or satisfies the query from the index itself. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “How does an index work?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: The database traverses the index structure to find key ranges or values, then fetches matching rows or satisfies the query from the index itself.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 365. Clustered vs non-clustered indexes?

1. **Question**: Clustered vs non-clustered indexes?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A clustered index determines table row order or storage organization; a non-clustered index is a separate lookup structure. Exact behavior is database-specific.
6. **Detailed explanation**: A clustered index determines table row order or storage organization; a non-clustered index is a separate lookup structure. Exact behavior is database-specific. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “Clustered vs non-clustered indexes?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A clustered index determines table row order or storage organization; a non-clustered index is a separate lookup structure. Exact behavior is database-specific.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 366. Composite index?

1. **Question**: Composite index?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A composite index contains multiple columns in a defined order and can support predicates and ordering that follow that order.
6. **Detailed explanation**: A composite index contains multiple columns in a defined order and can support predicates and ordering that follow that order. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “Composite index?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A composite index contains multiple columns in a defined order and can support predicates and ordering that follow that order.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 367. What is the leftmost-prefix rule?

1. **Question**: What is the leftmost-prefix rule?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: The leftmost-prefix rule means a composite index is most useful when a query constrains the leading columns in index order.
6. **Detailed explanation**: The leftmost-prefix rule means a composite index is most useful when a query constrains the leading columns in index order. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What is the leftmost-prefix rule?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: The leftmost-prefix rule means a composite index is most useful when a query constrains the leading columns in index order.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 368. When can indexes hurt performance?

1. **Question**: When can indexes hurt performance?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Indexes consume storage, slow writes, and add maintenance; too many or low-selectivity indexes can hurt performance.
6. **Detailed explanation**: Indexes consume storage, slow writes, and add maintenance; too many or low-selectivity indexes can hurt performance. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “When can indexes hurt performance?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Indexes consume storage, slow writes, and add maintenance; too many or low-selectivity indexes can hurt performance.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 369. Why might a database ignore an index?

1. **Question**: Why might a database ignore an index?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: The optimizer may ignore an index when a scan is cheaper, statistics are stale, selectivity is low, a function prevents use, or implicit conversion changes the predicate.
6. **Detailed explanation**: The optimizer may ignore an index when a scan is cheaper, statistics are stale, selectivity is low, a function prevents use, or implicit conversion changes the predicate. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “Why might a database ignore an index?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: The optimizer may ignore an index when a scan is cheaper, statistics are stale, selectivity is low, a function prevents use, or implicit conversion changes the predicate.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 370. How do you analyze a slow SQL query?

1. **Question**: How do you analyze a slow SQL query?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Capture the actual query and parameters, inspect the execution plan, row estimates, indexes, waits, I/O, and cardinality; then change and measure one thing at a time.
6. **Detailed explanation**: Capture the actual query and parameters, inspect the execution plan, row estimates, indexes, waits, I/O, and cardinality; then change and measure one thing at a time. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “How do you analyze a slow SQL query?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Capture the actual query and parameters, inspect the execution plan, row estimates, indexes, waits, I/O, and cardinality; then change and measure one thing at a time.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 371. What is an execution plan?

1. **Question**: What is an execution plan?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: An execution plan shows operators, join order, access paths, estimates, and costs chosen for a query.
6. **Detailed explanation**: An execution plan shows operators, join order, access paths, estimates, and costs chosen for a query. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What is an execution plan?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: An execution plan shows operators, join order, access paths, estimates, and costs chosen for a query.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 372. What is query cost?

1. **Question**: What is query cost?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Query cost is the optimizer’s estimated resource work, not a direct time guarantee; validate with actual execution metrics.
6. **Detailed explanation**: Query cost is the optimizer’s estimated resource work, not a direct time guarantee; validate with actual execution metrics. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What is query cost?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Query cost is the optimizer’s estimated resource work, not a direct time guarantee; validate with actual execution metrics.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 373. What is normalization?

1. **Question**: What is normalization?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Normalization structures data to reduce duplication and update anomalies while preserving relationships.
6. **Detailed explanation**: Normalization structures data to reduce duplication and update anomalies while preserving relationships. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What is normalization?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Normalization structures data to reduce duplication and update anomalies while preserving relationships.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 374. 1NF, 2NF, 3NF, BCNF?

1. **Question**: 1NF, 2NF, 3NF, BCNF?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: 1NF requires atomic values, 2NF removes partial dependency on a composite key, 3NF removes transitive dependency, and BCNF requires every determinant to be a candidate key.
6. **Detailed explanation**: 1NF requires atomic values, 2NF removes partial dependency on a composite key, 3NF removes transitive dependency, and BCNF requires every determinant to be a candidate key. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “1NF, 2NF, 3NF, BCNF?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: 1NF requires atomic values, 2NF removes partial dependency on a composite key, 3NF removes transitive dependency, and BCNF requires every determinant to be a candidate key.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 375. What is denormalization?

1. **Question**: What is denormalization?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Denormalization deliberately duplicates or precomputes data to improve reads, trading storage and write complexity for performance.
6. **Detailed explanation**: Denormalization deliberately duplicates or precomputes data to improve reads, trading storage and write complexity for performance. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What is denormalization?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Denormalization deliberately duplicates or precomputes data to improve reads, trading storage and write complexity for performance.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 376. Primary key vs unique key?

1. **Question**: Primary key vs unique key?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A primary key uniquely identifies rows and is the table’s main identity. A unique key enforces uniqueness but is not necessarily the chosen primary identity.
6. **Detailed explanation**: A primary key uniquely identifies rows and is the table’s main identity. A unique key enforces uniqueness but is not necessarily the chosen primary identity. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “Primary key vs unique key?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A primary key uniquely identifies rows and is the table’s main identity. A unique key enforces uniqueness but is not necessarily the chosen primary identity.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 377. Primary key vs foreign key?

1. **Question**: Primary key vs foreign key?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A primary key identifies rows in its table. A foreign key references a key in another table and enforces referential integrity.
6. **Detailed explanation**: A primary key identifies rows in its table. A foreign key references a key in another table and enforces referential integrity. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “Primary key vs foreign key?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A primary key identifies rows in its table. A foreign key references a key in another table and enforces referential integrity.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 378. What are constraints?

1. **Question**: What are constraints?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Constraints enforce rules such as NOT NULL, UNIQUE, PRIMARY KEY, FOREIGN KEY, and CHECK at the database boundary.
6. **Detailed explanation**: Constraints enforce rules such as NOT NULL, UNIQUE, PRIMARY KEY, FOREIGN KEY, and CHECK at the database boundary. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What are constraints?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Constraints enforce rules such as NOT NULL, UNIQUE, PRIMARY KEY, FOREIGN KEY, and CHECK at the database boundary.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 379. What are database transactions?

1. **Question**: What are database transactions?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A transaction groups operations into one logical unit with commit or rollback semantics.
6. **Detailed explanation**: A transaction groups operations into one logical unit with commit or rollback semantics. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What are database transactions?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A transaction groups operations into one logical unit with commit or rollback semantics.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 380. Explain ACID.

1. **Question**: Explain ACID.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: ACID means atomicity, consistency, isolation, and durability.
6. **Detailed explanation**: ACID means atomicity, consistency, isolation, and durability. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “Explain ACID.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: ACID means atomicity, consistency, isolation, and durability.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 381. What are isolation levels?

1. **Question**: What are isolation levels?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Isolation levels define which concurrent changes a transaction can observe and trade consistency anomalies against concurrency.
6. **Detailed explanation**: Isolation levels define which concurrent changes a transaction can observe and trade consistency anomalies against concurrency. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What are isolation levels?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Isolation levels define which concurrent changes a transaction can observe and trade consistency anomalies against concurrency.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 382. What are dirty reads?

1. **Question**: What are dirty reads?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A dirty read observes another transaction’s uncommitted change.
6. **Detailed explanation**: A dirty read observes another transaction’s uncommitted change. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What are dirty reads?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A dirty read observes another transaction’s uncommitted change.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 383. Non-repeatable reads?

1. **Question**: Non-repeatable reads?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A non-repeatable read returns different committed values when the same row is read twice in one transaction.
6. **Detailed explanation**: A non-repeatable read returns different committed values when the same row is read twice in one transaction. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “Non-repeatable reads?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A non-repeatable read returns different committed values when the same row is read twice in one transaction.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 384. Phantom reads?

1. **Question**: Phantom reads?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A phantom read occurs when a repeated range query returns a different set of rows because another transaction inserted or removed matching rows.
6. **Detailed explanation**: A phantom read occurs when a repeated range query returns a different set of rows because another transaction inserted or removed matching rows. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “Phantom reads?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A phantom read occurs when a repeated range query returns a different set of rows because another transaction inserted or removed matching rows.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 385. What is deadlock in a database?

1. **Question**: What is deadlock in a database?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: A database deadlock is a cycle of transactions waiting for locks held by each other.
6. **Detailed explanation**: A database deadlock is a cycle of transactions waiting for locks held by each other. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “What is deadlock in a database?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: A database deadlock is a cycle of transactions waiting for locks held by each other.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 386. How do you resolve database deadlocks?

1. **Question**: How do you resolve database deadlocks?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Keep transactions short, access tables in consistent order, index locking predicates, use timeouts, retry safely, and inspect deadlock graphs.
6. **Detailed explanation**: Keep transactions short, access tables in consistent order, index locking predicates, use timeouts, retry safely, and inspect deadlock graphs. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “How do you resolve database deadlocks?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Keep transactions short, access tables in consistent order, index locking predicates, use timeouts, retry safely, and inspect deadlock graphs.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 387. Optimistic vs pessimistic locking?

1. **Question**: Optimistic vs pessimistic locking?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Optimistic locking detects conflicts at update time; pessimistic locking blocks conflicting access earlier with database locks.
6. **Detailed explanation**: Optimistic locking detects conflicts at update time; pessimistic locking blocks conflicting access earlier with database locks. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “Optimistic vs pessimistic locking?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Optimistic locking detects conflicts at update time; pessimistic locking blocks conflicting access earlier with database locks.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 388. How do you find duplicate records?

1. **Question**: How do you find duplicate records?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Group by the duplicate-defining columns and use HAVING COUNT(*) > 1, or use ROW_NUMBER to identify duplicates with row detail.
6. **Detailed explanation**: Group by the duplicate-defining columns and use HAVING COUNT(*) > 1, or use ROW_NUMBER to identify duplicates with row detail. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “How do you find duplicate records?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Group by the duplicate-defining columns and use HAVING COUNT(*) > 1, or use ROW_NUMBER to identify duplicates with row detail.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 389. How do you find the nth-highest salary?

1. **Question**: How do you find the nth-highest salary?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Use DENSE_RANK or a distinct ordered subquery and select the requested rank, depending on whether ties share a rank.
6. **Detailed explanation**: Use DENSE_RANK or a distinct ordered subquery and select the requested rank, depending on whether ties share a rank. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “How do you find the nth-highest salary?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Use DENSE_RANK or a distinct ordered subquery and select the requested rank, depending on whether ties share a rank.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 390. How do you delete duplicate rows?

1. **Question**: How do you delete duplicate rows?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Assign ROW_NUMBER over the duplicate key, delete rows with row_number > 1, and retain the chosen canonical row inside a transaction.
6. **Detailed explanation**: Assign ROW_NUMBER over the duplicate key, delete rows with row_number > 1, and retain the chosen canonical row inside a transaction. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “How do you delete duplicate rows?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Assign ROW_NUMBER over the duplicate key, delete rows with row_number > 1, and retain the chosen canonical row inside a transaction.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 391. How do you retrieve the top N records per group?

1. **Question**: How do you retrieve the top N records per group?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Use ROW_NUMBER or DENSE_RANK partitioned by the group and filter to the required rank.
6. **Detailed explanation**: Use ROW_NUMBER or DENSE_RANK partitioned by the group and filter to the required rank. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “How do you retrieve the top N records per group?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Use ROW_NUMBER or DENSE_RANK partitioned by the group and filter to the required rank.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---

## 392. How would you optimize a query on a table containing hundreds of millions of rows?

1. **Question**: How would you optimize a query on a table containing hundreds of millions of rows?
2. **Difficulty**: Advanced
3. **Topic**: SQL → Core & Advanced
4. **What interviewer is testing**: Whether you understand relational semantics, query plans, concurrency, and performance trade-offs.
5. **Short interview answer (30–60 seconds)**: Partition or archive data, add selective covering indexes, use keyset pagination, pre-aggregate where justified, inspect plans, and avoid scanning unnecessary rows.
6. **Detailed explanation**: Partition or archive data, add selective covering indexes, use keyset pagination, pre-aggregate where justified, inspect plans, and avoid scanning unnecessary rows. The query must define null, duplicate, ordering, and transaction behavior explicitly.
7. **How it works internally**: The optimizer rewrites the query, chooses access paths and join algorithms, executes operators, and coordinates locks and transaction visibility.
8. **Example**:

For “How would you optimize a query on a table containing hundreds of millions of rows?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, name
FROM employee
WHERE active = TRUE
ORDER BY id;
```




10. **Time & space complexity**: The cost depends on scan, index, sort, hash, join, and window operators, table cardinality, and selectivity.
11. **Real-world/project usage**: This supports reporting, transactional services, reconciliation, pagination, and data cleanup.
12. **Common mistakes**: Ignoring NULL semantics, accidental cross joins, missing indexes, unstable pagination, and changing data without a transaction or backup.
13. **Advantages**: Declarative access, strong integrity guarantees, optimizer support, and expressive analytics.
14. **Limitations**: Plan sensitivity, lock contention, schema coupling, and performance degradation as data volume grows.
15. **Comparison with related concepts**: Compare joins/subqueries, UNION variants, isolation levels, indexing strategies, and ranking functions.
16. **Production considerations**: Use parameterized SQL, review plans, monitor waits and locks, test migrations, and bound long-running queries.
17. **Possible follow-up questions**: What happens with NULLs, ties, duplicate rows, concurrent updates, or a stale plan?
18. **Senior-level follow-up questions**: How would you tune it at scale, prove correctness, and deploy the change without blocking traffic?
19. **Scenario-based question**: A query becomes slow after data growth. Explain how you would capture the plan, validate estimates, change indexes or SQL, and measure the result.
20. **One-line revision note**: Partition or archive data, add selective covering indexes, use keyset pagination, pre-aggregate where justified, inspect plans, and avoid scanning unnecessary rows.
21. **Image visuals (if required)**: An execution-plan or transaction-isolation diagram may clarify the answer.

---
