# 31. SQL Coding Questions

> Source range: questions 798–817
## 798. Write SQL to find the second-highest salary.

1. **Question**: Write SQL to find the second-highest salary.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use DENSE_RANK over salary descending or select MAX(salary) below the maximum; decide how ties should behave.
6. **Detailed explanation**: Use DENSE_RANK over salary descending or select MAX(salary) below the maximum; decide how ties should behave. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Write SQL to find the second-highest salary.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT MAX(salary) AS second_highest FROM employee WHERE salary < (SELECT MAX(salary) FROM employee);
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use DENSE_RANK over salary descending or select MAX(salary) below the maximum; decide how ties should behave.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 799. Write SQL to find the nth-highest salary.

1. **Question**: Write SQL to find the nth-highest salary.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use DENSE_RANK or a distinct ordered subquery and filter where the rank equals N, handling fewer than N distinct salaries.
6. **Detailed explanation**: Use DENSE_RANK or a distinct ordered subquery and filter where the rank equals N, handling fewer than N distinct salaries. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Write SQL to find the nth-highest salary.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
WITH ranked AS (SELECT salary, DENSE_RANK() OVER (ORDER BY salary DESC) AS rnk FROM employee) SELECT salary FROM ranked WHERE rnk = :n;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use DENSE_RANK or a distinct ordered subquery and filter where the rank equals N, handling fewer than N distinct salaries.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 800. Find duplicate records.

1. **Question**: Find duplicate records.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: GROUP BY the duplicate-defining columns and filter with HAVING COUNT(*) > 1.
6. **Detailed explanation**: GROUP BY the duplicate-defining columns and filter with HAVING COUNT(*) > 1. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Find duplicate records.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT email, COUNT(*) AS occurrences FROM customer GROUP BY email HAVING COUNT(*) > 1;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: GROUP BY the duplicate-defining columns and filter with HAVING COUNT(*) > 1.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 801. Delete duplicate records while keeping one.

1. **Question**: Delete duplicate records while keeping one.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use ROW_NUMBER partitioned by the duplicate key, delete rows with row_number > 1, and keep the canonical row in a transaction.
6. **Detailed explanation**: Use ROW_NUMBER partitioned by the duplicate key, delete rows with row_number > 1, and keep the canonical row in a transaction. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Delete duplicate records while keeping one.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
WITH ranked AS (SELECT id, ROW_NUMBER() OVER (PARTITION BY email ORDER BY id) AS rn FROM customer) DELETE FROM customer WHERE id IN (SELECT id FROM ranked WHERE rn > 1);
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use ROW_NUMBER partitioned by the duplicate key, delete rows with row_number > 1, and keep the canonical row in a transaction.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 802. Find employees earning more than their managers.

1. **Question**: Find employees earning more than their managers.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Join employees to managers and filter employee.salary > manager.salary, handling missing managers explicitly.
6. **Detailed explanation**: Join employees to managers and filter employee.salary > manager.salary, handling missing managers explicitly. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Find employees earning more than their managers.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT e.id, e.name FROM employee e JOIN employee m ON m.id = e.manager_id WHERE e.salary > m.salary;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Join employees to managers and filter employee.salary > manager.salary, handling missing managers explicitly.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 803. Find the highest-paid employee in each department.

1. **Question**: Find the highest-paid employee in each department.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use ROW_NUMBER or RANK partitioned by department ordered by salary descending and filter to rank one.
6. **Detailed explanation**: Use ROW_NUMBER or RANK partitioned by department ordered by salary descending and filter to rank one. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Find the highest-paid employee in each department.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT * FROM (SELECT e.*, DENSE_RANK() OVER (PARTITION BY department_id ORDER BY salary DESC) AS rnk FROM employee e) x WHERE rnk = 1;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use ROW_NUMBER or RANK partitioned by department ordered by salary descending and filter to rank one.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 804. Find the top three salaries in each department.

1. **Question**: Find the top three salaries in each department.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use DENSE_RANK partitioned by department and filter rank <= 3 when ties should be included.
6. **Detailed explanation**: Use DENSE_RANK partitioned by department and filter rank <= 3 when ties should be included. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Find the top three salaries in each department.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT * FROM (SELECT e.*, DENSE_RANK() OVER (PARTITION BY department_id ORDER BY salary DESC) AS rnk FROM employee e) x WHERE rnk <= 3;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use DENSE_RANK partitioned by department and filter rank <= 3 when ties should be included.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 805. Find customers with no orders.

1. **Question**: Find customers with no orders.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: LEFT JOIN customers to orders and filter where the order key is NULL, or use NOT EXISTS.
6. **Detailed explanation**: LEFT JOIN customers to orders and filter where the order key is NULL, or use NOT EXISTS. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Find customers with no orders.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT c.id FROM customer c WHERE NOT EXISTS (SELECT 1 FROM orders o WHERE o.customer_id = c.id);
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: LEFT JOIN customers to orders and filter where the order key is NULL, or use NOT EXISTS.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 806. Find records existing in one table but not another.

1. **Question**: Find records existing in one table but not another.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use NOT EXISTS or EXCEPT/MINUS with the correct key and NULL semantics.
6. **Detailed explanation**: Use NOT EXISTS or EXCEPT/MINUS with the correct key and NULL semantics. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Find records existing in one table but not another.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT a.id FROM table_a a WHERE NOT EXISTS (SELECT 1 FROM table_b b WHERE b.business_key = a.business_key);
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use NOT EXISTS or EXCEPT/MINUS with the correct key and NULL semantics.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 807. Calculate running totals.

1. **Question**: Calculate running totals.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use SUM(amount) OVER (PARTITION BY account ORDER BY date ROWS UNBOUNDED PRECEDING).
6. **Detailed explanation**: Use SUM(amount) OVER (PARTITION BY account ORDER BY date ROWS UNBOUNDED PRECEDING). The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Calculate running totals.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT account_id, posted_at, amount, SUM(amount) OVER (PARTITION BY account_id ORDER BY posted_at ROWS UNBOUNDED PRECEDING) AS running_total FROM ledger;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use SUM(amount) OVER (PARTITION BY account ORDER BY date ROWS UNBOUNDED PRECEDING).
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 808. Calculate month-over-month growth.

1. **Question**: Calculate month-over-month growth.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Aggregate by month, use LAG to get the prior month, and calculate the percentage or absolute change with zero handling.
6. **Detailed explanation**: Aggregate by month, use LAG to get the prior month, and calculate the percentage or absolute change with zero handling. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Calculate month-over-month growth.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
WITH monthly AS (SELECT date_trunc('month', ordered_at) month, SUM(total) total FROM orders GROUP BY 1) SELECT month, total, LAG(total) OVER (ORDER BY month) AS previous_total, total - LAG(total) OVER (ORDER BY month) AS growth FROM monthly;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Aggregate by month, use LAG to get the prior month, and calculate the percentage or absolute change with zero handling.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 809. Find consecutive dates.

1. **Question**: Find consecutive dates.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use LAG to compare dates, form groups when the gap is greater than one, and aggregate consecutive ranges.
6. **Detailed explanation**: Use LAG to compare dates, form groups when the gap is greater than one, and aggregate consecutive ranges. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Find consecutive dates.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
WITH marked AS (SELECT event_date, event_date - (ROW_NUMBER() OVER (ORDER BY event_date))::int AS grp FROM event) SELECT MIN(event_date), MAX(event_date), COUNT(*) FROM marked GROUP BY grp;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use LAG to compare dates, form groups when the gap is greater than one, and aggregate consecutive ranges.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 810. Find users who logged in for consecutive days.

1. **Question**: Find users who logged in for consecutive days.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Deduplicate login dates, use LAG or date-minus-row-number grouping, and find runs meeting the required length.
6. **Detailed explanation**: Deduplicate login dates, use LAG or date-minus-row-number grouping, and find runs meeting the required length. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Find users who logged in for consecutive days.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
WITH days AS (SELECT DISTINCT user_id, login_date::date day FROM login), grouped AS (SELECT *, day - (ROW_NUMBER() OVER (PARTITION BY user_id ORDER BY day))::int AS grp FROM days) SELECT user_id, MIN(day), MAX(day), COUNT(*) FROM grouped GROUP BY user_id, grp;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Deduplicate login dates, use LAG or date-minus-row-number grouping, and find runs meeting the required length.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 811. Find duplicate emails.

1. **Question**: Find duplicate emails.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: GROUP BY email and HAVING COUNT(*) > 1, with normalization rules defined for case and whitespace.
6. **Detailed explanation**: GROUP BY email and HAVING COUNT(*) > 1, with normalization rules defined for case and whitespace. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Find duplicate emails.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT email, COUNT(*) FROM users GROUP BY LOWER(TRIM(email)) HAVING COUNT(*) > 1;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: GROUP BY email and HAVING COUNT(*) > 1, with normalization rules defined for case and whitespace.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 812. Find the latest record for every customer.

1. **Question**: Find the latest record for every customer.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use ROW_NUMBER partitioned by customer ordered by timestamp descending and select row one.
6. **Detailed explanation**: Use ROW_NUMBER partitioned by customer ordered by timestamp descending and select row one. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Find the latest record for every customer.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT * FROM (SELECT c.*, ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY created_at DESC) rn FROM customer_event c) x WHERE rn = 1;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use ROW_NUMBER partitioned by customer ordered by timestamp descending and select row one.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 813. Find the first and last order for every customer.

1. **Question**: Find the first and last order for every customer.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use ROW_NUMBER ascending and descending per customer, or aggregate min/max order timestamps and join back for details.
6. **Detailed explanation**: Use ROW_NUMBER ascending and descending per customer, or aggregate min/max order timestamps and join back for details. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Find the first and last order for every customer.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT customer_id, MIN(ordered_at) AS first_order, MAX(ordered_at) AS last_order FROM orders GROUP BY customer_id;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use ROW_NUMBER ascending and descending per customer, or aggregate min/max order timestamps and join back for details.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 814. Write pagination SQL.

1. **Question**: Write pagination SQL.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use LIMIT/OFFSET for simple pages or a keyset predicate based on the last stable sort key for large data.
6. **Detailed explanation**: Use LIMIT/OFFSET for simple pages or a keyset predicate based on the last stable sort key for large data. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Write pagination SQL.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT id, created_at FROM orders WHERE created_at < :cursor_created OR (created_at = :cursor_created AND id < :cursor_id) ORDER BY created_at DESC, id DESC LIMIT :page_size;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use LIMIT/OFFSET for simple pages or a keyset predicate based on the last stable sort key for large data.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 815. Write a query using ROW_NUMBER.

1. **Question**: Write a query using ROW_NUMBER.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use ROW_NUMBER() OVER (PARTITION BY group ORDER BY sort_key) and filter the outer query by row number.
6. **Detailed explanation**: Use ROW_NUMBER() OVER (PARTITION BY group ORDER BY sort_key) and filter the outer query by row number. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Write a query using ROW_NUMBER.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT *, ROW_NUMBER() OVER (PARTITION BY department_id ORDER BY salary DESC) AS rn FROM employee;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use ROW_NUMBER() OVER (PARTITION BY group ORDER BY sort_key) and filter the outer query by row number.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 816. Write a query using RANK and DENSE_RANK.

1. **Question**: Write a query using RANK and DENSE_RANK.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Use RANK when ties share rank with gaps and DENSE_RANK when ties share rank without gaps, then filter the desired rank.
6. **Detailed explanation**: Use RANK when ties share rank with gaps and DENSE_RANK when ties share rank without gaps, then filter the desired rank. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Write a query using RANK and DENSE_RANK.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
SELECT salary, RANK() OVER (ORDER BY salary DESC) AS rank, DENSE_RANK() OVER (ORDER BY salary DESC) AS dense_rank FROM employee;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Use RANK when ties share rank with gaps and DENSE_RANK when ties share rank without gaps, then filter the desired rank.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---

## 817. Optimize a query involving multiple joins on large tables.

1. **Question**: Optimize a query involving multiple joins on large tables.
2. **Difficulty**: Advanced
3. **Topic**: SQL → Coding
4. **What interviewer is testing**: Whether you can write correct, set-based SQL and reason about ties, nulls, plans, and large data.
5. **Short interview answer (30–60 seconds)**: Inspect the actual plan, join cardinalities, predicates, indexes, and intermediate rows; reduce data early and index join/filter keys.
6. **Detailed explanation**: Inspect the actual plan, join cardinalities, predicates, indexes, and intermediate rows; reduce data early and index join/filter keys. The query assumes the stated schema; tie and NULL behavior must be defined before relying on the result.
7. **How it works internally**: The database scans or seeks rows, partitions/sorts or hashes them, computes windows/aggregates, and filters the resulting relation.
8. **Example**:

For “Optimize a query involving multiple joins on large tables.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```sql
EXPLAIN (ANALYZE, BUFFERS) SELECT o.id, c.id FROM orders o JOIN customer c ON c.id = o.customer_id WHERE o.created_at >= :from_date;
```

10. **Time & space complexity**: Discuss scan, index, sort/window, join, and temporary-storage costs.
11. **Real-world/project usage**: This is used for reporting, reconciliation, dashboards, deduplication, and API data access.
12. **Common mistakes**: Incorrect tie semantics, NULL behavior, nondeterministic ordering, deleting without a transaction, and missing indexes.
13. **Advantages**: Set-based execution, composability, and optimizer support.
14. **Limitations**: Plan sensitivity, large sorts, locking, and database-specific syntax.
15. **Comparison with related concepts**: Compare window functions, aggregates, joins, EXISTS, OFFSET, and keyset pagination.
16. **Production considerations**: Test on realistic volume, inspect actual plans, bound result size, parameterize inputs, and protect destructive statements.
17. **Possible follow-up questions**: How do ties, NULLs, duplicates, concurrent writes, or missing indexes affect the result?
18. **Senior-level follow-up questions**: How would you make it fast on hundreds of millions of rows and deploy it safely?
19. **Scenario-based question**: The query is correct but too slow in production. Explain plan analysis, indexing, rewrite, and verification.
20. **One-line revision note**: Inspect the actual plan, join cardinalities, predicates, indexes, and intermediate rows; reduce data early and index join/filter keys.
21. **Image visuals (if required)**: A relational-algebra or execution-plan diagram may help.

---
