# 📚 Help AG Interview — Answer Bank

Detailed, interview-ready answers to the question bank in [questions.md](questions.md).

> **Progress: 20 / 175 questions answered.** Track the remaining ones in [answer-progress.md](answer-progress.md).

## 📑 Table of Contents

**Java Fundamentals (Q1–Q10)**

1. [Explain the equals() and hashCode() contract. What breaks if it’s violated?](#explain-the-equals-and-hashcode-contract-what-breaks-if-its-violated)
2. [How does Java memory management work (Heap, Stack, Metaspace)?](#how-does-java-memory-management-work-heap-stack-metaspace)
3. [Difference between volatile, synchronized, and Atomic classes.](#difference-between-volatile-synchronized-and-atomic-classes)
4. [How does garbage collection work in G1 vs ZGC?](#how-does-garbage-collection-work-in-g1-vs-zgc)
5. [What happens if an exception is thrown inside a finally block?](#what-happens-if-an-exception-is-thrown-inside-a-finally-block)
6. [How do you design immutable objects in Java?](#how-do-you-design-immutable-objects-in-java)
7. [Explain class loading in Java. How do custom class loaders work?](#explain-class-loading-in-java-how-do-custom-class-loaders-work)
8. [What are memory leaks in Java? Give real examples from production.](#what-are-memory-leaks-in-java-give-real-examples-from-production)
9. [How do you debug OutOfMemoryError in a running JVM?](#how-do-you-debug-outofmemoryerror-in-a-running-jvm)
10. [Difference between checked and unchecked exceptions—real-world use cases.](#difference-between-checked-and-unchecked-exceptionsreal-world-use-cases)

**Spring Boot & Spring Ecosystem (Q11–Q20)**

11. [How does Spring Boot auto-configuration work internally?](#how-does-spring-boot-auto-configuration-work-internally)
12. [What is the difference between @Component, @Service, and @Repository?](#what-is-the-difference-between-component-service-and-repository)
13. [How does Spring manage dependency injection lifecycle?](#how-does-spring-manage-dependency-injection-lifecycle)
14. [What is @Transactional? How does propagation work?](#what-is-transactional-how-does-propagation-work)
15. [When does @Transactional NOT work?](#when-does-transactional-not-work)
16. [Explain lazy vs eager loading in Spring Data JPA.](#explain-lazy-vs-eager-loading-in-spring-data-jpa)
17. [How do you handle N+1 query issues?](#how-do-you-handle-n1-query-issues)
18. [Difference between JpaRepository and CrudRepository.](#difference-between-jparepository-and-crudrepository)
19. [How do you implement pagination and sorting efficiently?](#how-do-you-implement-pagination-and-sorting-efficiently)
20. [How do you secure Spring Boot applications?](#how-do-you-secure-spring-boot-applications)

---

### Explain the equals() and hashCode() contract. What breaks if it’s violated?

---

## 1️⃣ What is the `equals()` and `hashCode()` Contract?

In Java, **`equals()` and `hashCode()` must work together**, especially for **hash-based collections** like:

* `HashMap`
* `HashSet`
* `ConcurrentHashMap`

### 📜 The Contract (Official Rules)

### equals() contract

For any non-null objects `a`, `b`, `c`:

1. **Reflexive** → `a.equals(a)` is `true`
2. **Symmetric** → `a.equals(b)` == `b.equals(a)`
3. **Transitive** → if `a.equals(b)` and `b.equals(c)` → `a.equals(c)`
4. **Consistent** → multiple calls return same result if data unchanged
5. **Non-null** → `a.equals(null)` is `false`

---

### hashCode() contract

1. If `a.equals(b) == true` → **`a.hashCode() == b.hashCode()` MUST be true**
2. If `a.hashCode() == b.hashCode()` → `a.equals(b)` **may or may not be true**
3. hashCode must be **consistent** during object lifetime (unless fields change)

👉 **equals stronger than hashCode**

---

## 2️⃣ Why This Contract Exists

Hash-based collections work in **two steps**:

1. Use `hashCode()` → find **bucket**
2. Use `equals()` → find **exact object**

If the contract breaks → collections behave incorrectly.

---

## 3️⃣ What Breaks If the Contract Is Violated?

### ❌ Case 1: equals() overridden, hashCode() NOT overridden

```java
class User {
    int id;

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (!(o instanceof User)) return false;
        User user = (User) o;
        return id == user.id;
    }
}
```

```java
User u1 = new User(1);
User u2 = new User(1);

Set<User> set = new HashSet<>();
set.add(u1);

System.out.println(set.contains(u2)); // ❌ false (BUG)
```

📌 **Why?**

* `equals()` → true
* `hashCode()` → different (Object’s default)
* HashSet looks in **wrong bucket**

🔥 **Result:**

* `contains()` fails
* duplicates appear
* memory leaks in maps

---

### ❌ Case 2: hashCode changes after insertion

```java
class User {
    int id;

    @Override
    public int hashCode() {
        return Objects.hash(id);
    }
}
```

```java
User user = new User(1);
HashSet<User> set = new HashSet<>();

set.add(user);
user.id = 2;

System.out.println(set.contains(user)); // ❌ false
```

📌 **Why?**

* Bucket calculated using old hashCode
* Object moved logically, not physically

🔥 **Result:** object becomes **unreachable**

---

### ❌ Case 3: equals() not symmetric

```java
class A {
    int id;
    public boolean equals(Object o) {
        return o instanceof B && id == ((B) o).id;
    }
}
class B extends A {}
```

```java
A a = new A(1);
B b = new B(1);

a.equals(b); // true
b.equals(a); // false ❌
```

🔥 **Result:** unpredictable collection behavior

---

## 4️⃣ Correct & Production-Ready Implementation

### ✅ Best Practice Example (FULL, USABLE)

```java
import java.util.Objects;

public final class User {

    private final Long id;
    private final String email;

    public User(Long id, String email) {
        this.id = id;
        this.email = email;
    }

    public Long getId() {
        return id;
    }

    public String getEmail() {
        return email;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        User user = (User) o;
        return Objects.equals(id, user.id) &&
               Objects.equals(email, user.email);
    }

    @Override
    public int hashCode() {
        return Objects.hash(id, email);
    }
}
```

### Why this is correct

* Uses **immutable fields**
* Uses `getClass()` (strict equality)
* Uses `Objects.hash()` (safe & readable)
* Safe for HashMap / HashSet / caching

---

## 5️⃣ JPA / Hibernate Special Case (VERY IMPORTANT)

### ⚠️ Entity equals/hashCode Rule

❌ Don’t use database-generated IDs directly if they’re assigned **after persist**

```java
@Id
@GeneratedValue
private Long id;
```

### ✅ Recommended pattern

```java
@Override
public boolean equals(Object o) {
    if (this == o) return true;
    if (!(o instanceof User)) return false;
    User other = (User) o;
    return id != null && id.equals(other.id);
}

@Override
public int hashCode() {
    return getClass().hashCode();
}
```

📌 Prevents:

* HashSet corruption
* Hibernate proxy issues

---

## 6️⃣ Interview Follow-Up Questions (Expect These)

* Why hash collisions are allowed?
* Can two unequal objects have same hashCode?
* Why immutable fields are preferred?
* Why use `getClass()` instead of `instanceof`?
* What happens in `ConcurrentHashMap`?
* How does HashMap internally work?

---

## 7️⃣ One-Line Interview Answer (If Time Is Short)

> If two objects are equal, they must have the same hashCode. Violating this breaks hash-based collections like HashMap and HashSet, causing lost entries, duplicates, and incorrect lookups.

---

If you want, next I can:

* 🔥 Deep dive into **HashMap internals**
* 🔥 equals/hashCode **with Hibernate proxies**
* 🔥 **ConcurrentHashMap behavior**
* 🔥 Real **production bug scenarios**

Ask the **next question** 🚀

---

### How does Java memory management work (Heap, Stack, Metaspace)?

Excellent choice — this is **JVM internals + performance + debugging + interview gold**.

I’ll keep it **brief but complete**, then give a **fully usable example**, and finally the **failure scenarios** interviewers care about.

---

## 1️⃣ Java Memory Management – High Level

Java memory is managed by the **JVM**, not the OS directly.
The main runtime memory areas are:

```
┌───────────────┐
│   Stack       │  → Method calls, local variables
├───────────────┤
│   Heap        │  → Objects, arrays
├───────────────┤
│ Metaspace     │  → Class metadata
├───────────────┤
│ Code Cache    │  → JIT compiled code
└───────────────┘
```

---

## 2️⃣ Stack Memory

### What lives in Stack?

* Method call frames
* Local variables
* References to heap objects
* Primitive values

### Characteristics

* **Thread-specific** (each thread has its own stack)
* Very fast (LIFO)
* Automatically freed when method exits
* Fixed size per thread

### Example

```java
public class StackExample {

    public static void main(String[] args) {
        int x = 10;                 // stored in stack
        User user = new User(1L);   // reference in stack
    }
}

class User {
    Long id; // actual object in heap
    User(Long id) {
        this.id = id;
    }
}
```

📌 Stack stores `user` **reference**, not the object itself.

### Failure

```text
java.lang.StackOverflowError
```

Caused by:

* Infinite recursion
* Deep call stacks

---

## 3️⃣ Heap Memory (Most Important)

### What lives in Heap?

* Objects (`new`)
* Arrays
* Class instances
* Static variables

### Shared across all threads

### Managed by **Garbage Collector (GC)**

---

### Heap Structure (Generational Model)

```
Heap
 ├── Young Generation
 │    ├── Eden
 │    ├── Survivor S0
 │    └── Survivor S1
 └── Old Generation
```

### Object Lifecycle

1. New object → **Eden**
2. Minor GC → moves to Survivor
3. Survives multiple GCs → **Old Gen**
4. Old Gen GC → Major / Full GC

---

### Example

```java
public class HeapExample {

    public static void main(String[] args) {
        for (int i = 0; i < 1_000_000; i++) {
            new User(i); // heap allocation
        }
    }
}
```

### Failure

```text
java.lang.OutOfMemoryError: Java heap space
```

### Common Causes

* Memory leaks (references not released)
* Large collections
* Caches without eviction

---

## 4️⃣ Metaspace (Java 8+)

### What is Metaspace?

* Stores **class metadata**
* Replaced **PermGen** (Java 7 and earlier)
* Stored in **native memory** (outside heap)

### Stores

* Class names
* Method metadata
* Field metadata
* Annotations
* Constant pool

---

### Example (Dynamic Class Loading)

```java
import net.bytebuddy.ByteBuddy;

public class MetaspaceExample {
    public static void main(String[] args) {
        while (true) {
            new ByteBuddy()
                .subclass(Object.class)
                .make()
                .load(MetaspaceExample.class.getClassLoader());
        }
    }
}
```

### Failure

```text
java.lang.OutOfMemoryError: Metaspace
```

### Causes

* Excessive class loading
* ClassLoader leaks
* Dynamic proxies

---

## 5️⃣ Static Variables – Where Do They Go?

```java
class Config {
    static String APP_NAME = "HelpAG";
}
```

| Part         | Stored Where |
| ------------ | ------------ |
| Reference    | Metaspace    |
| Object value | Heap         |

---

## 6️⃣ Garbage Collection Overview

### What GC Does

* Finds unreachable objects
* Frees heap memory
* Compacts memory

### Common GC Algorithms

* **G1 GC** (default)
* ZGC (low latency)
* Shenandoah

### GC Does NOT

* Free stack memory
* Free Metaspace automatically if classloaders alive

---

## 7️⃣ Interview Gold: What Breaks Where?

| Issue                        | Area             |
| ---------------------------- | ---------------- |
| StackOverflowError           | Stack            |
| OutOfMemoryError: heap space | Heap             |
| OutOfMemoryError: Metaspace  | Metaspace        |
| Memory leak                  | Heap / Metaspace |
| Slow app                     | Excess GC        |

---

## 8️⃣ JVM Tuning Parameters (Must Know)

```bash
-Xms512m           # Initial heap
-Xmx2g             # Max heap
-XX:MaxMetaspaceSize=256m
-XX:+UseG1GC
```

---

## 9️⃣ Production-Ready Demo (Runnable)

```java
import java.util.ArrayList;
import java.util.List;

public class MemoryDemo {

    static List<Object> cache = new ArrayList<>();

    public static void main(String[] args) {
        while (true) {
            cache.add(new byte[1024 * 1024]); // 1MB
        }
    }
}
```

👉 Will throw:

```text
OutOfMemoryError: Java heap space
```

---

## 🔥 One-Line Interview Answer

> Stack stores method execution and local variables per thread, Heap stores objects shared across threads and managed by GC, and Metaspace stores class metadata in native memory. Memory issues arise when these areas overflow due to recursion, leaks, or excessive class loading.

---

## Follow-up Questions You WILL Get

* Why stack is thread-safe?
* Why Metaspace replaced PermGen?
* How GC identifies unreachable objects?
* How to detect memory leaks?
* How to tune JVM memory?

Ask the **next question** — we’re in full interview mode 🚀

---

### Difference between volatile, synchronized, and Atomic classes.

Excellent — this is **concurrency fundamentals + JVM memory model + real bugs**. Interviewers *love* this.

I’ll keep it **brief but deep**, then give **full, runnable examples**, and finally **what breaks if you misuse them**.

---

## 1️⃣ High-Level Difference (Quick Table)

| Feature          | `volatile`  | `synchronized`    | Atomic classes    |
| ---------------- | ----------- | ----------------- | ----------------- |
| Visibility       | ✅ Yes       | ✅ Yes             | ✅ Yes             |
| Atomicity        | ❌ No        | ✅ Yes             | ✅ Yes             |
| Mutual exclusion | ❌ No        | ✅ Yes             | ❌ (lock-free)     |
| Blocking         | ❌ No        | ✅ Yes             | ❌ No              |
| Performance      | 🔥 Fast     | 🐢 Slower         | ⚡ Fast            |
| Use case         | State flags | Critical sections | Counters, CAS ops |

---

## 2️⃣ `volatile`

### What it does

* Guarantees **visibility** of variable across threads
* Reads/writes go **directly to main memory**
* Prevents instruction reordering

### What it does NOT do

❌ Does **not** guarantee atomicity

---

### Example (Correct Use)

```java
public class VolatileExample {

    private static volatile boolean running = true;

    public static void main(String[] args) throws InterruptedException {

        Thread worker = new Thread(() -> {
            while (running) {
                // do work
            }
            System.out.println("Stopped");
        });

        worker.start();
        Thread.sleep(1000);

        running = false; // visible to worker
    }
}
```

### ❌ Broken Example

```java
private volatile int count = 0;

count++; // NOT atomic
```

🔥 Race condition occurs

---

## 3️⃣ `synchronized`

### What it does

* Ensures **mutual exclusion**
* Ensures **visibility**
* Locks on **monitor (object or class)**

### Guarantees

* Only one thread executes critical section
* Lock acquisition creates **happens-before** relation

---

### Example (Thread-Safe Counter)

```java
public class SynchronizedCounter {

    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public synchronized int get() {
        return count;
    }
}
```

### Internals

* Uses JVM monitor lock
* Can cause:

  * Blocking
  * Context switching
  * Deadlocks (if misused)

---

### ❌ Deadlock Example

```java
synchronized (obj1) {
    synchronized (obj2) {
        // thread 1
    }
}

synchronized (obj2) {
    synchronized (obj1) {
        // thread 2
    }
}
```

🔥 App hangs forever

---

## 4️⃣ Atomic Classes (`java.util.concurrent.atomic`)

### What they are

* Lock-free, thread-safe
* Use **CAS (Compare-And-Swap)** internally
* Backed by CPU-level instructions

### Common Classes

* `AtomicInteger`
* `AtomicLong`
* `AtomicBoolean`
* `AtomicReference`

---

### Example (Best Counter)

```java
import java.util.concurrent.atomic.AtomicInteger;

public class AtomicCounter {

    private AtomicInteger count = new AtomicInteger(0);

    public void increment() {
        count.incrementAndGet();
    }

    public int get() {
        return count.get();
    }
}
```

### Why Atomic is Faster

* No blocking
* No context switching
* Retries instead of waiting

---

## 5️⃣ Compare Same Problem – All 3

### ❌ Volatile (Broken)

```java
private volatile int count = 0;

public void increment() {
    count++; // race condition
}
```

---

### ✅ synchronized (Correct but slower)

```java
public synchronized void increment() {
    count++;
}
```

---

### ✅ Atomic (Correct & best)

```java
private AtomicInteger count = new AtomicInteger();

public void increment() {
    count.incrementAndGet();
}
```

---

## 6️⃣ Memory Visibility Rule (Interview Gold)

| Action                     | Guarantees Visibility |
| -------------------------- | --------------------- |
| volatile write → read      | ✅                     |
| synchronized unlock → lock | ✅                     |
| Atomic CAS                 | ✅                     |

---

## 7️⃣ When to Use What (Real Projects)

### Use `volatile` when:

* Simple state flags
* Stop/start signals
* No compound operations

### Use `synchronized` when:

* Multiple variables
* Complex invariants
* Need mutual exclusion

### Use Atomic when:

* Counters
* Statistics
* Sequence generators
* Performance-critical paths

---

## 8️⃣ What Breaks If Misused?

| Misuse                   | Result                  |
| ------------------------ | ----------------------- |
| volatile for counters    | Wrong values            |
| synchronized too much    | Performance degradation |
| Atomic for complex logic | Inconsistent state      |

---

## 9️⃣ One-Line Interview Answer

> `volatile` ensures visibility only, `synchronized` ensures both visibility and mutual exclusion via locks, and Atomic classes provide lock-free, thread-safe operations using CAS.

---

## Follow-up Questions Interviewers Ask

* Why volatile doesn’t guarantee atomicity?
* How CAS works internally?
* Atomic vs LongAdder?
* When synchronized is unavoidable?
* Happens-before principle?

Ask the **next question** 🚀


### How does garbage collection work in G1 vs ZGC?

Excellent — this is **JVM internals + performance tuning + senior-level interview** territory.

I’ll keep it **brief but complete**, then give **usable JVM configs + demo code**, and finally **what breaks / when to choose which**.

---

## 1️⃣ Big Picture

Both **G1 GC** and **ZGC** are **low-pause, concurrent garbage collectors**, but they solve **different problems**.

| Aspect            | G1 GC                           | ZGC                   |
| ----------------- | ------------------------------- | --------------------- |
| Goal              | Balanced throughput + low pause | Ultra-low pause       |
| Pause time        | ~10–200 ms                      | **< 10 ms**           |
| Heap size         | Medium–Large                    | Very large (TBs)      |
| Compaction        | Stop-the-world (partial)        | **Concurrent**        |
| Pointer technique | Region-based                    | **Colored pointers**  |
| Java version      | Java 8+ (default)               | Java 11+ (prod-ready) |

---

## 2️⃣ G1 GC (Garbage First)

### How G1 Works

G1 divides the heap into **equal-sized regions** (1–32 MB):

```
Heap
 ├── Region (Eden)
 ├── Region (Survivor)
 ├── Region (Old)
 └── Region (Humongous)
```

### Collection Strategy

1. **Young GC** (STW, fast)
2. **Concurrent marking** identifies garbage in Old Gen
3. **Mixed GC** collects both Young + selected Old regions
4. Prioritizes regions with **most garbage first**

👉 “Garbage First”

---

### Key Features

* Predictable pause times
* Region-based evacuation
* Compacts memory to reduce fragmentation

---

### G1 JVM Configuration

```bash
-XX:+UseG1GC
-XX:MaxGCPauseMillis=100
-Xms4g
-Xmx4g
```

---

### G1 Failure Modes

* Pause spikes if heap too small
* Stop-the-world during evacuation
* Fragmentation with humongous objects

---

## 3️⃣ ZGC (Z Garbage Collector)

### How ZGC Works

ZGC uses **colored pointers + load barriers** to do **almost everything concurrently**.

```
Object Reference
 ├── Marked
 ├── Remapped
 └── Relocated
```

### Core Idea

* GC runs **concurrently with application**
* No long stop-the-world pauses
* Objects moved while app threads running

---

### ZGC Phases

1. Concurrent marking
2. Concurrent relocation
3. Concurrent remapping
4. Very short STW pauses (<10ms)

🔥 Pause time independent of heap size

---

### ZGC JVM Configuration

```bash
-XX:+UseZGC
-Xms16g
-Xmx16g
```

(No pause target needed)

---

### ZGC Strengths

* Sub-10 ms pauses
* Handles huge heaps
* No heap fragmentation
* Ideal for latency-sensitive systems

---

### ZGC Tradeoffs

* Slightly lower throughput
* More CPU usage
* Requires modern JVM

---

## 4️⃣ Side-by-Side Summary

| Feature         | G1                   | ZGC                        |
| --------------- | -------------------- | -------------------------- |
| Heap division   | Regions              | Regions + pointer coloring |
| STW pauses      | Yes                  | Minimal                    |
| Heap compaction | Partially STW        | Fully concurrent           |
| Fragmentation   | Possible             | Almost none                |
| Best for        | General backend apps | Low-latency systems        |

---

## 5️⃣ Practical Demo (Same Code, Different GC)

### Memory Pressure Code (Runnable)

```java
import java.util.ArrayList;
import java.util.List;

public class GcDemo {

    static List<byte[]> cache = new ArrayList<>();

    public static void main(String[] args) throws InterruptedException {
        while (true) {
            cache.add(new byte[1024 * 1024]); // 1MB
            Thread.sleep(10);
        }
    }
}
```

### Run with G1

```bash
java -XX:+UseG1GC -Xmx2g GcDemo
```

### Run with ZGC

```bash
java -XX:+UseZGC -Xmx2g GcDemo
```

🔍 Observe:

* G1 → noticeable pauses
* ZGC → smooth execution

---

## 6️⃣ What Breaks If You Choose Wrong?

| Scenario          | Wrong GC Impact |
| ----------------- | --------------- |
| Low-latency APIs  | G1 pause spikes |
| Huge heap (50GB+) | G1 long pauses  |
| CPU constrained   | ZGC overhead    |
| Legacy Java 8     | ZGC unavailable |

---

## 7️⃣ When to Choose What (Interview Answer)

### Choose **G1** if:

* General backend services
* Balanced throughput
* Java 8–17 apps

### Choose **ZGC** if:

* Latency-sensitive systems
* Large heaps
* Trading, payments, streaming

---

## 8️⃣ One-Line Interview Answer

> G1 uses region-based, partially stop-the-world collection with predictable pauses, while ZGC performs almost all GC work concurrently using colored pointers, achieving sub-10ms pauses regardless of heap size.

---

## Follow-up Questions You WILL Get

* What are humongous objects in G1?
* How colored pointers work?
* Why pause time is independent of heap size in ZGC?
* G1 vs Shenandoah?
* How to debug GC pauses?

Ask the **next question** 🚀



### What happens if an exception is thrown inside a finally block?

This is a **tricky but very important Java interview question**. It tests **exception handling semantics, debugging skills, and production awareness**.

I’ll keep it **brief, precise, and complete**, with **full runnable examples**.

---

## 1️⃣ Short Answer (Core Rule)

> **If an exception is thrown inside a `finally` block, it OVERRIDES any exception thrown in the `try` or `catch` block.**

🔥 The original exception is **lost** unless explicitly preserved.

---

## 2️⃣ Normal Flow Refresher

```java
try {
    // risky code
} catch (Exception e) {
    // handle
} finally {
    // cleanup (always runs)
}
```

* `finally` executes **always** (except JVM crash / `System.exit`)
* Intended for cleanup (closing resources)

---

## 3️⃣ Example: Exception in `try`, Exception in `finally`

### ❌ Problematic Code (Runnable)

```java
public class FinallyExceptionDemo {

    public static void main(String[] args) {
        try {
            throw new RuntimeException("Exception from try");
        } finally {
            throw new IllegalStateException("Exception from finally");
        }
    }
}
```

### Output

```text
Exception in thread "main" java.lang.IllegalStateException: Exception from finally
```

📌 **What happened?**

* `RuntimeException` from `try` is **discarded**
* `IllegalStateException` from `finally` wins

🔥 **Original root cause is lost**

---

## 4️⃣ Exception in `catch` + `finally`

```java
public class FinallyCatchDemo {

    public static void main(String[] args) {
        try {
            int x = 10 / 0;
        } catch (ArithmeticException e) {
            throw new RuntimeException("From catch");
        } finally {
            throw new IllegalStateException("From finally");
        }
    }
}
```

### Result

```text
IllegalStateException: From finally
```

Again → **catch exception lost**

---

## 5️⃣ Exception in `finally` WITHOUT try exception

```java
public class FinallyOnlyDemo {

    public static void main(String[] args) {
        try {
            System.out.println("No exception here");
        } finally {
            throw new RuntimeException("Finally exception");
        }
    }
}
```

✅ `finally` exception is thrown normally.

---

## 6️⃣ Why This Is Dangerous (Production Impact)

* Root cause disappears
* Logs become misleading
* Debugging becomes extremely hard
* Seen often in **resource cleanup code**

---

## 7️⃣ Correct Way: Preserve Original Exception

### ✅ Suppressed Exceptions (Java 7+)

```java
public class FinallySafeDemo {

    public static void main(String[] args) {
        Exception primary = null;

        try {
            throw new RuntimeException("Primary exception");
        } catch (Exception e) {
            primary = e;
            throw e;
        } finally {
            try {
                throw new IllegalStateException("Cleanup failed");
            } catch (Exception cleanup) {
                if (primary != null) {
                    primary.addSuppressed(cleanup);
                }
            }
        }
    }
}
```

### Output

```text
RuntimeException: Primary exception
Suppressed: IllegalStateException: Cleanup failed
```

---

## 8️⃣ Best Practice: Try-With-Resources (RECOMMENDED)

### ✅ Clean & Safe

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class TryWithResourcesDemo {

    public static void main(String[] args) throws IOException {
        try (BufferedReader br = new BufferedReader(new FileReader("file.txt"))) {
            System.out.println(br.readLine());
        }
    }
}
```

### Why better?

* JVM automatically handles cleanup
* Suppressed exceptions handled internally
* No exception masking

---

## 9️⃣ Special Case: `return` in `finally` (VERY BAD)

```java
public static int test() {
    try {
        return 1;
    } finally {
        return 2;
    }
}
```

### Output

```text
2
```

🔥 `finally` **overrides return value**

---

## 10️⃣ What Interviewers Expect You to Say

> * Finally always executes
> * Exception in finally overrides try/catch exception
> * This causes exception masking
> * Use try-with-resources or suppressed exceptions

---

## 11️⃣ One-Line Interview Answer

> If an exception is thrown in a finally block, it suppresses and replaces any exception thrown in the try or catch block, potentially hiding the real root cause.

---

## Follow-up Questions You’ll Likely Get

* Does finally always execute?
* What if `System.exit()` is called?
* How try-with-resources handles exceptions?
* What are suppressed exceptions?
* Why returning from finally is dangerous?

Ask the **next question** 🚀

---

### How do you design immutable objects in Java?

Excellent — this is **core Java design + thread-safety + security + interview favorite**.

I’ll keep it **brief but complete**, then give a **full, production-ready immutable class**, and finally **what breaks if you do it wrong**.

---

## 1️⃣ What Is an Immutable Object?

> An immutable object is an object whose **state cannot change after it is created**.

Examples:

* `String`
* `Integer`
* `LocalDate`

---

## 2️⃣ Why Immutability Matters (Interview Angle)

* Thread-safe by default
* No synchronization needed
* Safe for caching
* Secure (state cannot be altered)
* Easier to reason about

---

## 3️⃣ Rules to Design Immutable Objects

### ✅ Mandatory Rules

1. **Make class `final`**

   * Prevents subclassing
2. **Make all fields `private final`**
3. **No setters**
4. **Initialize all fields via constructor**
5. **Defensive copy of mutable inputs**
6. **Return defensive copies for mutable fields**

---

## 4️⃣ WRONG Example (Looks Immutable but Isn’t)

```java
import java.util.Date;

public class User {

    private final String name;
    private final Date dob;

    public User(String name, Date dob) {
        this.name = name;
        this.dob = dob; // ❌ reference leak
    }

    public Date getDob() {
        return dob; // ❌ mutable exposed
    }
}
```

### ❌ Why it breaks

```java
Date date = new Date();
User u = new User("Prasad", date);

date.setTime(0); // modifies internal state!
```

---

## 5️⃣ CORRECT, Production-Ready Immutable Class (FULL CODE)

```java
import java.util.Date;

public final class ImmutableUser {

    private final String name;
    private final Date dateOfBirth;

    public ImmutableUser(String name, Date dateOfBirth) {
        this.name = name;
        // defensive copy
        this.dateOfBirth = new Date(dateOfBirth.getTime());
    }

    public String getName() {
        return name;
    }

    public Date getDateOfBirth() {
        // defensive copy
        return new Date(dateOfBirth.getTime());
    }
}
```

✅ Fully immutable
✅ Thread-safe
✅ Secure

---

## 6️⃣ Best Practice: Prefer Immutable Types

Instead of `Date`, use `java.time` API:

```java
import java.time.LocalDate;

public final class BetterImmutableUser {

    private final String name;
    private final LocalDate dob;

    public BetterImmutableUser(String name, LocalDate dob) {
        this.name = name;
        this.dob = dob; // LocalDate is immutable
    }

    public String getName() {
        return name;
    }

    public LocalDate getDob() {
        return dob;
    }
}
```

🔥 No defensive copy needed

---

## 7️⃣ Immutable + Collections (VERY IMPORTANT)

### ❌ Wrong

```java
private final List<String> roles;
```

### ✅ Correct

```java
import java.util.Collections;
import java.util.List;

public final class ImmutableRoleUser {

    private final List<String> roles;

    public ImmutableRoleUser(List<String> roles) {
        this.roles = List.copyOf(roles); // Java 10+
    }

    public List<String> getRoles() {
        return roles;
    }
}
```

---

## 8️⃣ Immutability vs `final` (Trick Question)

```java
final List<String> list = new ArrayList<>();
list.add("ADMIN"); // allowed
```

📌 `final` means reference can’t change, **object can**

---

## 9️⃣ What Breaks If You Design It Wrong?

| Mistake           | Impact            |
| ----------------- | ----------------- |
| Mutable fields    | State corruption  |
| Reference leaks   | Security bugs     |
| No defensive copy | Thread issues     |
| Not final class   | Subclass mutation |

---

## 🔥 One-Line Interview Answer

> To design an immutable object, make the class final, fields private and final, initialize via constructor, avoid setters, and use defensive copies for mutable fields.

---

## Follow-up Questions Interviewers Ask

* Why String is immutable?
* Is immutability always good?
* Performance impact of immutability?
* Immutable vs thread-safe?
* How to make immutable objects serializable?

Ask the **next question** 🚀


---

### Explain class loading in Java. How do custom class loaders work?
Great question — this is **JVM internals + security + architecture**, and interviewers love it.

I’ll explain it **clearly**, then show **exact flow**, then a **working custom ClassLoader example**, and finally **real-world use cases & pitfalls**.

---

## 1️⃣ What Is Class Loading in Java?

> **Class loading** is the process by which the JVM **loads `.class` files into memory**, verifies them, and makes them executable.

It’s handled by the **ClassLoader subsystem** of the JVM.

---

## 2️⃣ When Is a Class Loaded?

A class is loaded when it’s **first actively used**, for example:

* Creating an object (`new`)
* Calling a static method
* Accessing a static field
* Using reflection
* Class.forName()

📌 Java uses **lazy loading**.

---

## 3️⃣ Class Loading Phases

### 🔹 1. Loading

* Reads `.class` bytecode
* Creates `Class<?>` object
* Loads into **Metaspace**

### 🔹 2. Linking

**a) Verification**

* Bytecode verification (security)

**b) Preparation**

* Allocates memory for static fields
* Sets default values

**c) Resolution**

* Symbolic references → direct references

### 🔹 3. Initialization

* Executes static blocks
* Assigns actual static values

```java
static {
    System.out.println("Class initialized");
}
```

---

## 4️⃣ Java ClassLoader Hierarchy

```
Bootstrap ClassLoader
   ↓
Platform ClassLoader
   ↓
Application ClassLoader
   ↓
Custom ClassLoader
```

### 🔹 Bootstrap ClassLoader

* Loads core Java classes (`java.lang.*`)
* Written in native code

### 🔹 Platform ClassLoader

* Loads Java SE platform modules

### 🔹 Application ClassLoader

* Loads classes from classpath

---

## 5️⃣ Parent Delegation Model (VERY IMPORTANT)

> **A class loader first delegates to its parent before loading the class itself**

### Flow:

```
loadClass()
   ↓
Parent.loadClass()
   ↓
If not found → try locally
```

### Why?

* Security
* Prevents overriding core Java classes (`java.lang.String`)

---

## 6️⃣ Example: Verify ClassLoader

```java
public class ClassLoaderDemo {

    public static void main(String[] args) {
        System.out.println(String.class.getClassLoader()); // null (Bootstrap)
        System.out.println(ClassLoaderDemo.class.getClassLoader());
    }
}
```

### Output

```text
null
jdk.internal.loader.ClassLoaders$AppClassLoader
```

---

## 7️⃣ How Custom ClassLoaders Work

You create a custom class loader by:

* Extending `ClassLoader`
* Overriding `findClass()`

⚠️ **DO NOT override `loadClass()` unless you know what you’re doing**

---

## 8️⃣ FULL WORKING Custom ClassLoader Example

### 🔹 Custom ClassLoader

```java
import java.nio.file.Files;
import java.nio.file.Path;

public class MyClassLoader extends ClassLoader {

    private final Path classDir;

    public MyClassLoader(Path classDir) {
        this.classDir = classDir;
    }

    @Override
    protected Class<?> findClass(String className) throws ClassNotFoundException {
        try {
            String fileName = className.replace('.', '/') + ".class";
            Path classFile = classDir.resolve(fileName);

            byte[] classBytes = Files.readAllBytes(classFile);

            return defineClass(className, classBytes, 0, classBytes.length);
        } catch (Exception e) {
            throw new ClassNotFoundException(className, e);
        }
    }
}
```

---

### 🔹 Using the Custom ClassLoader

```java
import java.nio.file.Path;

public class CustomLoaderTest {

    public static void main(String[] args) throws Exception {
        Path path = Path.of("/tmp/classes");

        MyClassLoader loader = new MyClassLoader(path);

        Class<?> clazz = loader.loadClass("com.example.Hello");

        Object obj = clazz.getDeclaredConstructor().newInstance();
        clazz.getMethod("sayHello").invoke(obj);
    }
}
```

---

## 9️⃣ Breaking Parent Delegation (Advanced)

Some frameworks **intentionally break delegation**:

* Web containers (Tomcat)
* OSGi
* Application servers

Why?

* Multiple versions of same library
* Plugin systems

⚠️ Dangerous if misused

---

## 🔥 Real-World Uses of Custom ClassLoaders

| Use Case       | Example           |
| -------------- | ----------------- |
| Plugin systems | IDEs              |
| App servers    | Tomcat            |
| Hot reloading  | Spring DevTools   |
| Isolation      | Multi-tenant apps |
| Sandboxing     | Security tools    |

---

## 10️⃣ ClassLoader + Security (Interview Favorite)

* Same class name + different classloader = **different classes**
* Prevents malicious code replacing core classes
* Enables module isolation

---

## 11️⃣ Common Pitfalls

| Issue                | Cause                                  |
| -------------------- | -------------------------------------- |
| ClassCastException   | Same class loaded by different loaders |
| Memory leaks         | ClassLoader not GC’d                   |
| NoClassDefFoundError | Class missing at runtime               |

---

## 🔥 One-Line Interview Answer

> Java class loading uses a parent delegation model with Bootstrap, Platform, and Application class loaders; custom class loaders extend ClassLoader and override findClass to load classes dynamically.

---

## Follow-up Questions You’ll Get

* Difference between `ClassNotFoundException` and `NoClassDefFoundError`
* Why String class loader is null?
* How class loaders cause memory leaks?
* How Spring Boot uses class loaders?

Ask the **next one** 🚀
---
### What are memory leaks in Java? Give real examples from production.
Alright, this one is **very important for real-world Java + interviews**. Let’s go clean, crisp, and practical.

---

## What is a Memory Leak in Java?

A **memory leak** happens when **objects that are no longer needed are still strongly referenced**, so the **Garbage Collector cannot reclaim them**, causing **heap usage to grow over time** → eventually **OutOfMemoryError**.

> Java has GC, but GC **cannot free objects that are still reachable**.

---

## Why Memory Leaks Happen (Root Cause)

**Unintentional object retention** due to:

* Long-lived references
* Static fields
* Caches without eviction
* Listeners not removed
* ThreadLocal misuse

---

## Common Production Memory Leak Scenarios (REAL)

---

### 1. Static Collections (Most Common 🔥)

#### ❌ Problem

```java
public class UserCache {
    private static final Map<String, User> CACHE = new HashMap<>();

    public static void addUser(User user) {
        CACHE.put(user.getId(), user);
    }
}
```

* `CACHE` lives for the **entire JVM lifetime**
* Users are **never removed**
* Heap keeps growing

#### ✅ Fix

* Use eviction
* Use Weak references
* Limit size

```java
private static final Map<String, User> CACHE =
        new LinkedHashMap<>(100, 0.75f, true) {
            protected boolean removeEldestEntry(Map.Entry eldest) {
                return size() > 1000;
            }
        };
```

---

### 2. Listener / Callback Leaks (Very Common in Spring & UI)

#### ❌ Problem

```java
eventSource.registerListener(this);
```

* Listener holds reference to the object
* Object never GC’ed if listener is not removed

#### ✅ Fix

```java
eventSource.unregisterListener(this);
```

Or use **WeakReference listeners**.

---

### 3. ThreadLocal Memory Leak (Classic Interview Favorite)

#### ❌ Problem

```java
private static final ThreadLocal<UserContext> context =
        new ThreadLocal<>();

public void process() {
    context.set(new UserContext());
}
```

* In **thread pools**, threads are reused
* ThreadLocal value **never cleared**
* Leaks accumulate

#### ✅ Fix (MANDATORY)

```java
try {
    context.set(new UserContext());
    // business logic
} finally {
    context.remove();
}
```

---

### 4. Improper Cache Usage (Production Killer)

#### ❌ Problem

```java
Map<String, Object> cache = new HashMap<>();

cache.put(requestId, heavyObject);
```

* No TTL
* No eviction
* Used in high-traffic services

#### ✅ Fix

Use proper cache libraries:

```java
Cache<String, Object> cache = Caffeine.newBuilder()
        .maximumSize(10_000)
        .expireAfterWrite(10, TimeUnit.MINUTES)
        .build();
```

---

### 5. ClassLoader Leaks (App Server / Microservices)

#### ❌ Problem

* Static references to classes loaded by **custom class loaders**
* Happens during:

  * Hot redeploy
  * App reload (Tomcat, WebLogic)

#### Result

* Old classloader **never GC’ed**
* Metaspace leak

#### ✅ Fix

* Avoid static references to:

  * JDBC drivers
  * ThreadLocals
  * Singletons
* Clean up in `@PreDestroy`

---

### 6. Unclosed Resources (Silent but Deadly)

#### ❌ Problem

```java
InputStream in = new FileInputStream("data.txt");
// no close()
```

* Native memory leak
* File descriptors leak

#### ✅ Fix

```java
try (InputStream in = new FileInputStream("data.txt")) {
    // use stream
}
```

---

## How Memory Leaks Show Up in Production

* Gradual heap growth
* Frequent Full GC
* GC pauses increase
* Eventually:

```text
java.lang.OutOfMemoryError: Java heap space
```

or

```text
OutOfMemoryError: Metaspace
```

---

## How to Detect Memory Leaks (Real Tools)

* **Heap Dump**

  * `jmap -dump:live,format=b,file=heap.hprof <pid>`
* **Analyzers**

  * Eclipse MAT
  * VisualVM
  * JProfiler
* Look for:

  * Dominator Tree
  * Retained Heap
  * GC Roots

---

## Interview One-Liners (Very Useful)

* “Memory leaks in Java occur due to **unintended object retention**, not lack of GC.”
* “Static references and ThreadLocals are the most common causes.”
* “GC can only collect unreachable objects.”

---

## Key Takeaways

* Java memory leaks = **logical leaks**
* GC ≠ automatic safety
* Always:

  * Remove listeners
  * Clear ThreadLocals
  * Bound caches
  * Close resources

---

If you want next:

* **Heap dump analysis walkthrough**
* **ThreadLocal internals**
* **Metaspace vs Heap leaks**
* **Spring Boot real leak scenarios**

👉 Ask the next question.
---
### How do you debug OutOfMemoryError in a running JVM?
This is a **real production-grade question**. I’ll cover **what actually works on a live JVM**, step by step.

---

## What is OutOfMemoryError (OOM)?

`OutOfMemoryError` occurs when the JVM **cannot allocate memory** in:

* Heap
* Metaspace
* Native memory (direct buffers, threads)

GC is running, but **nothing eligible to free**.

---

## Step-by-Step: Debug OOM in a Running JVM

---

## 1️⃣ Identify the OOM Type (CRITICAL FIRST STEP)

Check logs / error message:

```text
java.lang.OutOfMemoryError: Java heap space
java.lang.OutOfMemoryError: Metaspace
java.lang.OutOfMemoryError: GC overhead limit exceeded
java.lang.OutOfMemoryError: Direct buffer memory
```

Each means **different root causes**.

---

## 2️⃣ Enable JVM Diagnostics (Before Crash)

### Mandatory JVM Flags (Production Safe)

```bash
-XX:+HeapDumpOnOutOfMemoryError
-XX:HeapDumpPath=/var/log/heapdump.hprof
-XX:+ExitOnOutOfMemoryError
```

👉 Ensures **heap dump is captured automatically**.

---

## 3️⃣ Observe Memory in Real Time (Live JVM)

### Check heap usage

```bash
jstat -gc <pid> 5s
```

Look for:

* Old Gen constantly growing
* Full GC not reducing usage

---

### Check JVM memory

```bash
jcmd <pid> GC.heap_info
```

---

## 4️⃣ Capture Heap Dump from Running JVM

### Safe in production (brief pause)

```bash
jmap -dump:live,format=b,file=heap.hprof <pid>
```

* `live` = only reachable objects
* Pause depends on heap size

---

## 5️⃣ Analyze Heap Dump (Most Important)

### Use Tools

* Eclipse MAT (best)
* VisualVM
* JProfiler

### What to Look For

* **Top Consumers**
* **Dominator Tree**
* **Retained Heap**
* **GC Roots**

👉 Find **who is holding references**

---

## 6️⃣ Identify Common Leak Patterns

| Symptom            | Root Cause              |
| ------------------ | ----------------------- |
| `HashMap` huge     | Unbounded cache         |
| `ThreadLocalMap`   | ThreadLocal not cleared |
| `ClassLoader`      | Redeploy leak           |
| `byte[]` large     | File/stream buffering   |
| `DirectByteBuffer` | Netty / NIO leak        |

---

## 7️⃣ Debug Without Heap Dump (Emergency)

### Thread dump

```bash
jstack <pid>
```

Helps detect:

* Thread explosion
* Blocked threads
* ThreadLocal misuse

---

### Native memory tracking

```bash
jcmd <pid> VM.native_memory summary
```

Useful for:

* Direct buffers
* Off-heap leaks

---

## 8️⃣ Fix Based on OOM Type

---

### 🧠 Java Heap Space

**Cause**

* Memory leak
* Large collections

**Fix**

* Bound caches
* Fix retention
* Tune heap

```bash
-Xms4g -Xmx4g
```

---

### 🧠 Metaspace OOM

**Cause**

* Classloader leak
* Dynamic proxy explosion

**Fix**

```bash
-XX:MaxMetaspaceSize=512m
```

* Fix static references

---

### 🧠 GC Overhead Limit

**Cause**

* GC spending >98% time, <2% reclaimed

**Fix**

* Reduce allocations
* Fix leaks
* Increase heap

---

### 🧠 Direct Buffer Memory

**Cause**

* NIO / Netty buffers

**Fix**

```bash
-XX:MaxDirectMemorySize=1g
```

---

## 9️⃣ Production Code Example: ThreadLocal OOM Fix

### ❌ Leak

```java
private static final ThreadLocal<byte[]> buffer =
        new ThreadLocal<>();

public void process() {
    buffer.set(new byte[10_000_000]);
}
```

### ✅ Fix

```java
public void process() {
    try {
        buffer.set(new byte[10_000_000]);
    } finally {
        buffer.remove();
    }
}
```

---

## 10️⃣ Prevent OOM (Best Practices)

* Always:

  * Bound caches
  * Remove listeners
  * Close resources
* Monitor:

  * Heap usage
  * GC pauses
* Load test with:

  * Production data size

---

## Interview Gold Statements

* “OOM is usually caused by **object retention**, not GC failure.”
* “Heap dump + dominator tree tells the truth.”
* “ThreadLocal leaks are common in thread pools.”

---

## Debug Flow (One Line)

**Logs → Identify OOM type → Heap dump → Dominator Tree → Fix root reference**

---

If you want next:

* **Heap dump analysis demo**
* **ZGC vs G1 OOM behavior**
* **Spring Boot OOM case study**
* **Netty direct memory leaks**

👉 Ask the next question.

---
### Difference between checked and unchecked exceptions—real-world use cases.

Classic Java interview question — but I’ll explain it **from real production + design perspective**, not textbook.

---

## 1️⃣ What Are Checked vs Unchecked Exceptions?

| Type                   | Checked Exception                               | Unchecked Exception              |
| ---------------------- | ----------------------------------------------- | -------------------------------- |
| Package                | `java.lang.Exception` (except RuntimeException) | `RuntimeException`               |
| Compile-time check     | ✅ Mandatory                                     | ❌ Not required                   |
| Must handle or declare | Yes                                             | No                               |
| Indicates              | Recoverable conditions                          | Programming bugs / invalid state |

---

## 2️⃣ Checked Exceptions (WHEN & WHY)

### 📌 Definition

Exceptions that **must be caught or declared** using `throws`.

### Common Examples

* `IOException`
* `SQLException`
* `FileNotFoundException`

---

### ✅ Real-World Use Cases (Checked)

#### 1. File System Operations

```java
public String readFile(String path) throws IOException {
    return Files.readString(Path.of(path));
}
```

📌 Why checked?

* Disk may fail
* File may not exist
* Caller may retry or choose fallback

---

#### 2. External System Calls (DB, Network)

```java
public void save(User user) throws SQLException {
    // DB might be down
}
```

📌 Caller can:

* Retry
* Use backup DB
* Send error response

---

### ❗ Best Practice

Checked exceptions **cross system boundaries**:

* IO
* DB
* Network
* External APIs

---

## 3️⃣ Unchecked Exceptions (WHEN & WHY)

### 📌 Definition

Exceptions that extend `RuntimeException`.

### Common Examples

* `NullPointerException`
* `IllegalArgumentException`
* `IllegalStateException`

---

### ✅ Real-World Use Cases (Unchecked)

#### 1. Programming Errors

```java
public int divide(int a, int b) {
    if (b == 0) {
        throw new IllegalArgumentException("b cannot be zero");
    }
    return a / b;
}
```

📌 Why unchecked?

* Caller should not recover
* Indicates bug or invalid input

---

#### 2. Invalid Application State

```java
if (order.getStatus() != PAID) {
    throw new IllegalStateException("Order not paid");
}
```

---

#### 3. Framework & Spring Boot

Spring converts checked exceptions into unchecked ones:

```java
throw new DataAccessException("DB error") { };
```

📌 Prevents cluttered `throws` everywhere.

---

## 4️⃣ Controller-Level Handling (REAL WORLD)

### ❌ Bad (Leaking Checked Exception)

```java
@GetMapping("/user")
public User getUser() throws SQLException {
    ...
}
```

### ✅ Good (Translate to Unchecked / Business Exception)

```java
@GetMapping("/user")
public User getUser() {
    try {
        return service.getUser();
    } catch (SQLException ex) {
        throw new ServiceException("Unable to fetch user", ex);
    }
}
```

---

## 5️⃣ Custom Exception Design (BEST PRACTICE)

### Business Exception (Unchecked)

```java
public class BusinessException extends RuntimeException {
    public BusinessException(String message) {
        super(message);
    }
}
```

Used for:

* Validation failures
* Business rule violations

---

### System Exception (Checked)

```java
public class ExternalServiceException extends Exception {
    public ExternalServiceException(String message, Throwable cause) {
        super(message, cause);
    }
}
```

Used for:

* External dependencies

---

## 6️⃣ Rule of Thumb (Interview Gold)

| Scenario                 | Use       |
| ------------------------ | --------- |
| Can caller recover?      | Checked   |
| Programming mistake?     | Unchecked |
| Business rule violated?  | Unchecked |
| External system failure? | Checked   |
| Framework internal error | Unchecked |

---

## 7️⃣ Why Checked Exceptions Are Avoided in Modern Java?

* Pollutes method signatures
* Hard to refactor
* Poor for lambdas & streams
* Spring, Hibernate prefer unchecked

📌 That’s why **Spring wraps checked into runtime exceptions**

---

## 8️⃣ FULL Spring Boot Example (Production-Ready)

### Repository

```java
public User findById(Long id) {
    return userRepository.findById(id)
        .orElseThrow(() -> new BusinessException("User not found"));
}
```

---

### Global Exception Handler

```java
@RestControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(BusinessException.class)
    public ResponseEntity<String> handleBusiness(BusinessException ex) {
        return ResponseEntity.badRequest().body(ex.getMessage());
    }
}
```

---

## 9️⃣ What Happens If You Abuse Checked Exceptions?

* Too many `throws`
* Tight coupling
* Hard-to-read APIs
* Developers catch & ignore (`catch(Exception e){}` ❌)

---

## 🔥 One-Line Interview Answer

> Checked exceptions represent recoverable conditions like IO or DB failures, while unchecked exceptions indicate programming or business logic errors that should not be silently handled.

---

## Follow-up Questions They Ask

* Why RuntimeException preferred in Spring?
* Can we create checked business exceptions?
* Should controllers throw checked exceptions?
* How exception handling works in microservices?

---
### How does Spring Boot auto-configuration work internally?

This is **one of the most important Spring Boot internals questions**. I’ll keep it **clear, layered, and practical**, with **real internal flow + usable code**.

---

## 1️⃣ What Is Spring Boot Auto-Configuration?

> Auto-configuration automatically **creates and configures Spring beans** based on:

* Classpath dependencies
* Existing beans
* Application properties

📌 Goal: **Convention over configuration**

---

## 2️⃣ High-Level Flow (Interview View)

```
@SpringBootApplication
        ↓
@EnableAutoConfiguration
        ↓
spring.factories / AutoConfiguration.imports
        ↓
Auto-Configuration Classes
        ↓
@Conditional checks
        ↓
Beans created
```

---

## 3️⃣ What Happens at Startup (Step-by-Step)

### Step 1: `@SpringBootApplication`

```java
@SpringBootApplication
public class App { }
```

This includes:

```java
@EnableAutoConfiguration
@ComponentScan
@Configuration
```

---

### Step 2: Enable Auto-Configuration

```java
@EnableAutoConfiguration
```

Internally imports:

```java
AutoConfigurationImportSelector
```

This selector **decides which auto-config classes to load**.

---

## 4️⃣ How Spring Finds Auto-Config Classes

### Spring Boot ≤ 2.x

```
META-INF/spring.factories
```

```properties
org.springframework.boot.autoconfigure.EnableAutoConfiguration=\
org.springframework.boot.autoconfigure.jdbc.DataSourceAutoConfiguration,\
org.springframework.boot.autoconfigure.web.servlet.WebMvcAutoConfiguration
```

---

### Spring Boot 3.x (IMPORTANT)

```
META-INF/spring/org.springframework.boot.autoconfigure.AutoConfiguration.imports
```

📌 Faster startup, cleaner metadata.

---

## 5️⃣ How Conditions Control Auto-Config

Auto-configuration classes are full of **@Conditional annotations**.

### Common Conditions

| Condition                      | Meaning                   |
| ------------------------------ | ------------------------- |
| `@ConditionalOnClass`          | Class exists on classpath |
| `@ConditionalOnMissingBean`    | Bean not defined by user  |
| `@ConditionalOnProperty`       | Property enabled          |
| `@ConditionalOnWebApplication` | Web environment           |

---

### Example: DataSource Auto-Config (Simplified)

```java
@Configuration
@ConditionalOnClass(DataSource.class)
@ConditionalOnMissingBean(DataSource.class)
public class DataSourceAutoConfiguration {

    @Bean
    public DataSource dataSource() {
        return new HikariDataSource();
    }
}
```

📌 If **you define your own DataSource**, Boot backs off.

---

## 6️⃣ Property-Driven Configuration

```properties
spring.datasource.url=jdbc:postgresql://localhost/db
spring.datasource.username=admin
spring.datasource.password=secret
```

Spring Boot:

* Binds properties
* Applies them automatically
* No explicit bean needed

---

## 7️⃣ How Spring Boot “Backs Off”

### User Overrides Auto-Config

```java
@Bean
public DataSource customDataSource() {
    return new CustomDataSource();
}
```

Auto-config stops because:

```java
@ConditionalOnMissingBean(DataSource.class)
```

🔥 **User config always wins**

---

## 8️⃣ Debugging Auto-Configuration (VERY IMPORTANT)

### Enable Report

```properties
debug=true
```

Or:

```bash
--debug
```

### Output Shows

* Positive matches
* Negative matches
* Why config was applied or skipped

---

## 9️⃣ Write Your Own Auto-Configuration (FULL EXAMPLE)

### 1️⃣ Create Auto-Config Class

```java
@Configuration
@ConditionalOnClass(MyService.class)
@ConditionalOnMissingBean(MyService.class)
public class MyServiceAutoConfiguration {

    @Bean
    public MyService myService() {
        return new MyService();
    }
}
```

---

### 2️⃣ Register It (Spring Boot 3.x)

```
META-INF/spring/org.springframework.boot.autoconfigure.AutoConfiguration.imports
```

```text
com.example.autoconfig.MyServiceAutoConfiguration
```

---

### 3️⃣ Consumer App

```java
@Autowired
MyService myService; // auto-created
```

---

## 10️⃣ How Auto-Config Helps DevSecOps & Microservices

* Standardized configs
* Secure defaults
* Property-based overrides
* Easy cloud portability
* Faster CI/CD

---

## 11️⃣ Common Interview Traps

❓ **Is auto-configuration magic?**
👉 No, it’s conditional bean registration.

❓ **Does Spring Boot override user beans?**
👉 Never.

❓ **When is auto-config evaluated?**
👉 During application context refresh.

---

## 🔥 One-Line Interview Answer

> Spring Boot auto-configuration works by conditionally registering configuration classes discovered from metadata files, creating beans only when required dependencies and conditions are satisfied, while backing off when user-defined beans exist.

---

## Follow-Up Questions Interviewers Ask

* Difference between auto-config and component scan?
* How to exclude auto-config?
* How does Spring Boot 3 improve startup?
* How conditional annotations work internally?




---
### If i want to add multiple database in single java spring boot project how to do this?Give the code example of more than 3 different database connection and save user data?

Great question—this *does* come up in real projects (multi-tenant apps, legacy migrations, reporting DBs, etc.).
Let’s walk through a **clean, production-style way** to connect **more than 3 databases** in **one Spring Boot app**, and **save user data** into each.

I’ll show:

1. **Architecture**
2. **application.yml**
3. **4 Database configurations**
4. **Entities & Repositories**
5. **Saving user data**
6. **Common mistakes & tips**

---

## 1️⃣ Architecture (High Level)

Each database needs **its own**:

* DataSource
* EntityManagerFactory
* TransactionManager
* Repository package

Example databases:

* **DB1** → MySQL
* **DB2** → PostgreSQL
* **DB3** → Oracle
* **DB4** → MongoDB *(NoSQL – optional but common)*

> Spring Boot **does NOT auto-configure multiple DBs** — you must define them explicitly.

---

## 2️⃣ application.yml

```yaml
spring:
  jpa:
    show-sql: true
    hibernate:
      ddl-auto: update

db1:
  datasource:
    url: jdbc:mysql://localhost:3306/user_db1
    username: root
    password: root
    driver-class-name: com.mysql.cj.jdbc.Driver

db2:
  datasource:
    url: jdbc:postgresql://localhost:5432/user_db2
    username: postgres
    password: postgres
    driver-class-name: org.postgresql.Driver

db3:
  datasource:
    url: jdbc:oracle:thin:@localhost:1521:xe
    username: system
    password: oracle
    driver-class-name: oracle.jdbc.OracleDriver

spring:
  data:
    mongodb:
      uri: mongodb://localhost:27017/user_db4
```

---

## 3️⃣ Database Configurations

---

### 🔹 DB1 – MySQL (Primary DB)

```java
@Configuration
@EnableJpaRepositories(
        basePackages = "com.example.db1.repo",
        entityManagerFactoryRef = "db1EntityManager",
        transactionManagerRef = "db1TransactionManager"
)
public class DB1Config {

    @Primary
    @Bean
    @ConfigurationProperties(prefix = "db1.datasource")
    public DataSource db1DataSource() {
        return DataSourceBuilder.create().build();
    }

    @Primary
    @Bean
    public LocalContainerEntityManagerFactoryBean db1EntityManager(
            EntityManagerFactoryBuilder builder) {

        return builder
                .dataSource(db1DataSource())
                .packages("com.example.db1.entity")
                .persistenceUnit("db1PU")
                .build();
    }

    @Primary
    @Bean
    public PlatformTransactionManager db1TransactionManager(
            @Qualifier("db1EntityManager") EntityManagerFactory emf) {
        return new JpaTransactionManager(emf);
    }
}
```

---

### 🔹 DB2 – PostgreSQL

```java
@Configuration
@EnableJpaRepositories(
        basePackages = "com.example.db2.repo",
        entityManagerFactoryRef = "db2EntityManager",
        transactionManagerRef = "db2TransactionManager"
)
public class DB2Config {

    @Bean
    @ConfigurationProperties(prefix = "db2.datasource")
    public DataSource db2DataSource() {
        return DataSourceBuilder.create().build();
    }

    @Bean
    public LocalContainerEntityManagerFactoryBean db2EntityManager(
            EntityManagerFactoryBuilder builder) {

        return builder
                .dataSource(db2DataSource())
                .packages("com.example.db2.entity")
                .persistenceUnit("db2PU")
                .build();
    }

    @Bean
    public PlatformTransactionManager db2TransactionManager(
            @Qualifier("db2EntityManager") EntityManagerFactory emf) {
        return new JpaTransactionManager(emf);
    }
}
```

---

### 🔹 DB3 – Oracle

```java
@Configuration
@EnableJpaRepositories(
        basePackages = "com.example.db3.repo",
        entityManagerFactoryRef = "db3EntityManager",
        transactionManagerRef = "db3TransactionManager"
)
public class DB3Config {

    @Bean
    @ConfigurationProperties(prefix = "db3.datasource")
    public DataSource db3DataSource() {
        return DataSourceBuilder.create().build();
    }

    @Bean
    public LocalContainerEntityManagerFactoryBean db3EntityManager(
            EntityManagerFactoryBuilder builder) {

        return builder
                .dataSource(db3DataSource())
                .packages("com.example.db3.entity")
                .persistenceUnit("db3PU")
                .build();
    }

    @Bean
    public PlatformTransactionManager db3TransactionManager(
            @Qualifier("db3EntityManager") EntityManagerFactory emf) {
        return new JpaTransactionManager(emf);
    }
}
```

---

### 🔹 DB4 – MongoDB (NoSQL)

```java
@Document(collection = "users")
public class UserMongo {

    @Id
    private String id;
    private String name;
    private String email;
}
```

```java
public interface UserMongoRepository extends MongoRepository<UserMongo, String> {
}
```

---

## 4️⃣ Entities

### MySQL User

```java
@Entity
@Table(name = "users")
public class UserMySQL {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private String email;
}
```

### PostgreSQL User

```java
@Entity
@Table(name = "users_pg")
public class UserPostgres {

    @Id
    @GeneratedValue
    private Long id;
    private String name;
    private String email;
}
```

### Oracle User

```java
@Entity
@Table(name = "users_oracle")
public class UserOracle {

    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE)
    private Long id;
    private String name;
    private String email;
}
```

---

## 5️⃣ Repositories

```java
public interface UserMySQLRepo extends JpaRepository<UserMySQL, Long> {}
public interface UserPostgresRepo extends JpaRepository<UserPostgres, Long> {}
public interface UserOracleRepo extends JpaRepository<UserOracle, Long> {}
```

---

## 6️⃣ Service – Save User into ALL Databases

```java
@Service
public class UserService {

    @Autowired
    private UserMySQLRepo mysqlRepo;

    @Autowired
    private UserPostgresRepo postgresRepo;

    @Autowired
    private UserOracleRepo oracleRepo;

    @Autowired
    private UserMongoRepository mongoRepo;

    public void saveUserEverywhere(String name, String email) {

        mysqlRepo.save(new UserMySQL(null, name, email));
        postgresRepo.save(new UserPostgres(null, name, email));
        oracleRepo.save(new UserOracle(null, name, email));

        mongoRepo.save(new UserMongo(null, name, email));
    }
}
```

---

## 7️⃣ Important Interview & Production Notes 🔥

### ❗ Transactions across DBs?

* `@Transactional` **does NOT work across multiple DBs**
* You need:

  * **Saga Pattern**
  * **2-Phase Commit (XA)** *(rare & heavy)*

---

### ❗ Common Mistakes

❌ Same entity package for multiple DBs
❌ Forgetting `@Primary`
❌ Mixing repositories
❌ Expecting rollback across DBs automatically

---

## 8️⃣ When Should You Use This?

✅ Multi-tenant apps
✅ Gradual DB migration
✅ Read/write split
✅ Reporting DB
❌ Small apps (overkill)

---

If you want, I can also:

* Show **dynamic DB routing**
* Implement **Saga pattern**
* Add **read/write separation**
* Convert this to **Spring Boot 3 + Jakarta**
* Draw **architecture diagram**

Just tell me 👍

---

### What is the difference between @Component, @Service, and @Repository?

This looks simple, but interviewers use it to test **Spring internals + clean architecture + exception handling**. Let’s do it properly.

---

## 1️⃣ High-Level Difference (Truth First)

> **Functionally, all three create Spring beans.**
> The difference is **semantic meaning + behavior**, not DI.

| Annotation    | Purpose                     | Extra Behavior        |
| ------------- | --------------------------- | --------------------- |
| `@Component`  | Generic Spring-managed bean | None                  |
| `@Service`    | Business logic layer        | Semantic clarity      |
| `@Repository` | Data access layer           | Exception translation |

---

## 2️⃣ @Component (Generic)

### When to Use

* Utility classes
* Helpers
* Infrastructure beans

### Example

```java
@Component
public class JwtUtil {

    public String generateToken(String user) {
        return "token";
    }
}
```

📌 No special behavior
📌 Just registers a bean

---

## 3️⃣ @Service (Business Logic Layer)

### When to Use

* Business rules
* Orchestration
* Transactions

### Example

```java
@Service
public class OrderService {

    public void placeOrder() {
        // business logic
    }
}
```

📌 Improves readability
📌 Helps AOP (transactions, security)

---

## 4️⃣ @Repository (Data Access Layer)

### 🔥 SPECIAL BEHAVIOR (IMPORTANT)

`@Repository` enables **exception translation**.

### What That Means

Low-level exceptions:

```java
SQLException
```

Are converted into:

```java
DataAccessException (Runtime)
```

---

### Example

```java
@Repository
public class UserRepository {

    public User findById(Long id) {
        throw new SQLException("DB error"); // simulated
    }
}
```

Spring converts it to:

```java
DataAccessException
```

🔥 This avoids checked exceptions leaking to service layer.

---

## 5️⃣ Why Exception Translation Matters (REAL WORLD)

### ❌ Without @Repository

```java
throws SQLException
```

Every layer must handle it.

### ✅ With @Repository

```java
throw new DataAccessException(...)
```

Handled globally.

---

## 6️⃣ Under the Hood (Internal Detail)

All three are meta-annotations of `@Component`:

```java
@Component
public @interface Service { }
```

```java
@Component
public @interface Repository { }
```

📌 Spring distinguishes them **via stereotypes**, not DI.

---

## 7️⃣ Full Layered Example (PRODUCTION-READY)

### Repository

```java
@Repository
public class UserRepository {

    public User findUser(Long id) {
        if (id == 0) {
            throw new RuntimeException("DB error");
        }
        return new User(id, "Prasad");
    }
}
```

---

### Service

```java
@Service
public class UserService {

    private final UserRepository repo;

    public UserService(UserRepository repo) {
        this.repo = repo;
    }

    public User getUser(Long id) {
        return repo.findUser(id);
    }
}
```

---

### Controller

```java
@RestController
public class UserController {

    private final UserService service;

    public UserController(UserService service) {
        this.service = service;
    }

    @GetMapping("/user/{id}")
    public User get(@PathVariable Long id) {
        return service.getUser(id);
    }
}
```

---

## 8️⃣ When Should NOT Use @Component?

| Case           | Use Instead                       |
| -------------- | --------------------------------- |
| Business logic | `@Service`                        |
| DB access      | `@Repository`                     |
| Controllers    | `@Controller` / `@RestController` |

---

## 9️⃣ Interview Trick Questions

❓ *Can I replace @Service with @Component?*
👉 Yes, but **don’t** (loses semantic meaning).

❓ *Does @Service add transactions automatically?*
👉 No. But it’s commonly used with `@Transactional`.

❓ *Does @Repository work without DB?*
👉 Yes, but exception translation is DB-specific.

---

## 🔥 One-Line Interview Answer

> @Component is a generic Spring bean, @Service represents business logic, and @Repository represents data access with automatic exception translation.

---

## Follow-Up Questions They Ask

* How exception translation works internally?
* Difference between @Controller and @RestController?
* Where should @Transactional be placed?
* What happens if we annotate DAO with @Component?

---
### How does Spring manage dependency injection lifecycle?

This is a **core Spring internals + lifecycle + DI question**. Interviewers want to know **what happens behind the scenes**, not just `@Autowired`.

I’ll explain it **step-by-step**, then give a **full usable lifecycle demo**.

---

## 1️⃣ What Is Dependency Injection Lifecycle in Spring?

> Spring manages the **creation, wiring, initialization, usage, and destruction** of beans inside the **IoC container**.

Lifecycle phases:

```
Bean Definition
→ Bean Instantiation
→ Dependency Injection
→ Aware callbacks
→ BeanPostProcessors (before init)
→ Initialization
→ BeanPostProcessors (after init)
→ Bean Ready for use
→ Destruction
```

---

## 2️⃣ Step-by-Step Bean Lifecycle (Internals)

---

### 🔹 1. Bean Definition Loading

Spring reads metadata from:

* `@Component`, `@Service`, `@Bean`
* XML / Java Config

```java
@Component
class PaymentService {}
```

Spring creates a **BeanDefinition**, not the object yet.

---

### 🔹 2. Bean Instantiation

Spring creates object using:

* Constructor (preferred)
* Reflection

```java
public PaymentService() {}
```

📌 Object created, **dependencies NOT injected yet**

---

### 🔹 3. Dependency Injection (DI)

Spring injects dependencies via:

* Constructor injection (BEST)
* Setter injection
* Field injection

```java
@Service
public class OrderService {

    private final PaymentService paymentService;

    public OrderService(PaymentService paymentService) {
        this.paymentService = paymentService;
    }
}
```

📌 Happens **after instantiation**

---

### 🔹 4. Aware Interfaces (Optional)

If bean implements:

* `BeanNameAware`
* `ApplicationContextAware`

Spring injects container info.

```java
@Component
public class MyBean implements BeanNameAware {

    @Override
    public void setBeanName(String name) {
        System.out.println("Bean name: " + name);
    }
}
```

---

### 🔹 5. BeanPostProcessor (Before Init)

Framework hooks run here:

* `@Autowired` processing
* `@Value`
* AOP proxies

```java
postProcessBeforeInitialization()
```

---

### 🔹 6. Initialization

Called via:

* `@PostConstruct`
* `InitializingBean.afterPropertiesSet()`
* `initMethod`

```java
@PostConstruct
public void init() {
    System.out.println("Bean initialized");
}
```

📌 Bean is now fully ready

---

### 🔹 7. BeanPostProcessor (After Init)

Used for:

* AOP proxies
* Transactions
* Security

```java
postProcessAfterInitialization()
```

---

### 🔹 8. Bean Ready for Use

Bean is injected and used by application.

---

### 🔹 9. Destruction Phase

Triggered when:

* App shuts down
* Context closes

```java
@PreDestroy
public void cleanup() {
    System.out.println("Bean destroyed");
}
```

---

## 3️⃣ FULL LIFECYCLE DEMO (PRODUCTION-READY)

```java
@Component
public class LifecycleBean
        implements BeanNameAware, InitializingBean, DisposableBean {

    public LifecycleBean() {
        System.out.println("1. Constructor");
    }

    @Override
    public void setBeanName(String name) {
        System.out.println("2. BeanNameAware: " + name);
    }

    @PostConstruct
    public void postConstruct() {
        System.out.println("3. @PostConstruct");
    }

    @Override
    public void afterPropertiesSet() {
        System.out.println("4. InitializingBean");
    }

    @PreDestroy
    public void preDestroy() {
        System.out.println("5. @PreDestroy");
    }

    @Override
    public void destroy() {
        System.out.println("6. DisposableBean");
    }
}
```

---

## 4️⃣ Bean Scopes & Lifecycle Impact

| Scope     | Lifecycle                                        |
| --------- | ------------------------------------------------ |
| Singleton | One per container                                |
| Prototype | New instance every request (no destroy callback) |
| Request   | HTTP request                                     |
| Session   | HTTP session                                     |

📌 **Prototype beans are NOT destroyed by Spring**

---

## 5️⃣ Constructor vs Field Injection (Interview Trap)

### ✅ Constructor Injection (Best)

* Immutable
* Testable
* Fail-fast

### ❌ Field Injection

* Reflection-based
* Hard to test
* Not recommended

---

## 6️⃣ How Spring Resolves Dependencies

1. By **type**
2. By **@Qualifier**
3. By **@Primary**

```java
@Autowired
@Qualifier("paypal")
PaymentService paymentService;
```

---

## 7️⃣ Circular Dependency Handling

* Allowed with **setter injection**
* ❌ Not allowed with constructor injection

```java
A → B → A  // fails with constructor injection
```

---

## 8️⃣ DI Lifecycle in Spring Boot vs Spring

Spring Boot:

* Same lifecycle
* Adds auto-configuration
* Registers many BeanPostProcessors

---

## 🔥 One-Line Interview Answer

> Spring manages dependency injection by creating bean definitions, instantiating beans, injecting dependencies, applying lifecycle callbacks and post-processors, and finally managing destruction when the context shuts down.

---

## Follow-Up Questions Interviewers Ask

* Why constructor injection is preferred?
* What is BeanPostProcessor?
* How AOP works in lifecycle?
* How Spring handles circular dependencies?
* Difference between prototype and singleton lifecycle?

---

### What is @Transactional? How does propagation work?

This is a **must-know Spring + real production question**. I’ll explain **what actually happens**, then **propagation types with real use cases**, and finish with **working code + traps**.

---

## 1️⃣ What Is `@Transactional`?

> `@Transactional` tells Spring to **start, manage, and complete a database transaction** around a method.

Spring ensures:

* **BEGIN** transaction
* **COMMIT** on success
* **ROLLBACK** on failure

It works using **AOP proxies**.

---

## 2️⃣ How `@Transactional` Works Internally

1. Spring creates a **proxy** for the bean
2. Method call goes through proxy
3. TransactionManager:

   * Opens transaction
   * Executes method
   * Commits or rolls back
4. Proxy returns result

📌 **Internal method calls are NOT intercepted**

---

## 3️⃣ Basic Example (FULL, USABLE)

```java
@Service
public class OrderService {

    @Transactional
    public void placeOrder() {
        orderRepository.save(new Order());
        paymentRepository.save(new Payment());
    }
}
```

If payment fails → **entire transaction rolls back**

---

## 4️⃣ Rollback Rules (VERY IMPORTANT)

### Default Behavior

| Exception          | Rollback? |
| ------------------ | --------- |
| `RuntimeException` | ✅ Yes     |
| `Error`            | ✅ Yes     |
| Checked Exception  | ❌ No      |

### Force Rollback for Checked

```java
@Transactional(rollbackFor = Exception.class)
```

---

## 5️⃣ What Is Propagation?

> Propagation defines **how transactions behave when a transactional method is called inside another transactional method**.

---

## 6️⃣ Propagation Types (REAL-WORLD MEANING)

---

### 1️⃣ REQUIRED (DEFAULT)

```java
@Transactional(propagation = Propagation.REQUIRED)
```

📌 Uses existing transaction or creates a new one.

✅ Most common
❌ All failures rollback everything

---

### Example

```java
@Transactional
public void parent() {
    child(); // joins same transaction
}
```

---

### 2️⃣ REQUIRES_NEW

```java
@Transactional(propagation = Propagation.REQUIRES_NEW)
```

📌 Suspends parent transaction, starts a new one.

✅ Independent commit
❌ Expensive

---

### Example (Audit Logging)

```java
@Transactional
public void placeOrder() {
    orderRepo.save(order);
    auditService.log(); // separate transaction
}
```

```java
@Transactional(propagation = Propagation.REQUIRES_NEW)
public void log() {
    auditRepo.save(new Audit());
}
```

📌 Audit commits even if order fails

---

### 3️⃣ SUPPORTS

```java
@Transactional(propagation = Propagation.SUPPORTS)
```

📌 Runs in transaction if exists, else non-transactional.

Use for:

* Read-only methods

---

### 4️⃣ NOT_SUPPORTED

```java
@Transactional(propagation = Propagation.NOT_SUPPORTED)
```

📌 Suspends existing transaction.

Use for:

* External API calls
* Long operations

---

### 5️⃣ NEVER

```java
@Transactional(propagation = Propagation.NEVER)
```

📌 Throws exception if transaction exists.

Use for:

* Critical non-transactional logic

---

### 6️⃣ MANDATORY

```java
@Transactional(propagation = Propagation.MANDATORY)
```

📌 Fails if no transaction exists.

Use for:

* Internal core operations

---

### 7️⃣ NESTED (Advanced)

```java
@Transactional(propagation = Propagation.NESTED)
```

📌 Creates savepoint inside parent transaction.

⚠️ Works only with JDBC, not all DBs.

---

## 7️⃣ Propagation Summary Table

| Propagation   | Uses Existing TX | Creates New TX |
| ------------- | ---------------- | -------------- |
| REQUIRED      | ✅                | If none        |
| REQUIRES_NEW  | ❌                | ✅              |
| SUPPORTS      | Optional         | ❌              |
| NOT_SUPPORTED | ❌                | ❌              |
| NEVER         | ❌                | ❌              |
| MANDATORY     | ✅                | ❌              |
| NESTED        | ✅                | Savepoint      |

---

## 8️⃣ Common Production Bugs (INTERVIEW GOLD)

---

### ❌ Internal Method Call (Proxy Bypass)

```java
@Transactional
public void parent() {
    child(); // @Transactional ignored
}
```

📌 Solution: call via another bean

---

### ❌ Wrong Exception Type

```java
throw new Exception(); // no rollback
```

📌 Fix:

```java
@Transactional(rollbackFor = Exception.class)
```

---

### ❌ Using on private methods

```java
@Transactional
private void save() {} // ignored
```

---

## 9️⃣ Read-Only Optimization

```java
@Transactional(readOnly = true)
public List<User> findAll() {}
```

📌 Improves performance (especially Hibernate)

---

## 🔥 One-Line Interview Answer

> `@Transactional` manages database transactions using AOP proxies, and propagation defines how transactional methods behave when invoked within existing transactions.

---

## Follow-Up Questions Interviewers Ask

* Why internal calls don’t trigger @Transactional?
* Difference between REQUIRED vs REQUIRES_NEW?
* How rollback rules work?
* Distributed transactions in microservices?

---
### When does @Transactional NOT work?

This is a **high-value Spring interview question**. Interviewers ask it to check if you *actually used transactions in production* 😄

I’ll give you **clear cases where `@Transactional` silently fails**, **why it fails**, and **working fixes with code**.

---

## 1️⃣ Internal Method Calls (MOST COMMON)

### ❌ Problem

```java
@Service
public class OrderService {

    @Transactional
    public void placeOrder() {
        saveOrder(); // ❌ @Transactional IGNORED
    }

    @Transactional
    public void saveOrder() {
        orderRepository.save(new Order());
    }
}
```

### Why?

* Spring uses **proxy-based AOP**
* Internal calls **bypass the proxy**

### ✅ Fix

Split into separate beans:

```java
@Service
public class OrderService {

    private final OrderTxService txService;

    public OrderService(OrderTxService txService) {
        this.txService = txService;
    }

    public void placeOrder() {
        txService.saveOrder();
    }
}

@Service
public class OrderTxService {

    @Transactional
    public void saveOrder() {
        // transactional
    }
}
```

---

## 2️⃣ Private / Final Methods

### ❌ Problem

```java
@Transactional
private void save() { }
```

### Why?

* Spring cannot proxy private methods

### ✅ Fix

* Use **public** methods
* Avoid `final`

---

## 3️⃣ Checked Exceptions (Silent No Rollback)

### ❌ Problem

```java
@Transactional
public void save() throws Exception {
    throw new Exception("fail"); // ❌ commits
}
```

### Why?

* Default rollback only for `RuntimeException`

### ✅ Fix

```java
@Transactional(rollbackFor = Exception.class)
```

---

## 4️⃣ Wrong Bean Type (No Proxy)

### ❌ Problem

```java
new OrderService().placeOrder();
```

### Why?

* Spring does not manage manually created objects

### ✅ Fix

Always inject beans:

```java
@Autowired
OrderService service;
```

---

## 5️⃣ Calling @Transactional from @PostConstruct

### ❌ Problem

```java
@PostConstruct
@Transactional
public void init() {
    saveData(); // ❌ no transaction
}
```

### Why?

* Bean proxy not ready yet

### ✅ Fix

Use `ApplicationRunner` or `@EventListener`

---

## 6️⃣ Wrong Transaction Manager (Multiple DBs)

### ❌ Problem

```java
@Transactional
public void save() { }
```

But app has **multiple DataSources**.

### Why?

* Spring picks default transaction manager

### ✅ Fix

```java
@Transactional(transactionManager = "orderTxManager")
```

---

## 7️⃣ No PlatformTransactionManager

### ❌ Problem

* Missing DB dependency
* No `DataSource`

📌 Spring logs:

```
No qualifying bean of type 'PlatformTransactionManager'
```

---

## 8️⃣ Async Methods (@Async)

### ❌ Problem

```java
@Async
@Transactional
public void saveAsync() { }
```

### Why?

* Runs in different thread
* Transaction context not propagated

### ✅ Fix

Use messaging or manual TX handling

---

## 9️⃣ Non-Transactional Databases

### ❌ Problem

* MyISAM (MySQL)
* NoSQL (MongoDB without transactions)

### Why?

* DB does not support transactions

---

## 🔥 10️⃣ Read-Only Transaction Writing Data

```java
@Transactional(readOnly = true)
public void save() {
    repo.save(entity); // ❌ ignored / exception
}
```

---

## 11️⃣ Summary Table (INTERVIEW GOLD)

| Scenario               | Works?     |
| ---------------------- | ---------- |
| Internal method call   | ❌          |
| Private / final method | ❌          |
| Checked exception      | ❌ rollback |
| Manual object creation | ❌          |
| @PostConstruct         | ❌          |
| Wrong TX manager       | ❌          |
| @Async                 | ❌          |
| Read-only TX write     | ❌          |

---

## 🔥 One-Line Interview Answer

> `@Transactional` does not work on internal method calls, private methods, checked exceptions without rollback rules, manually created objects, async methods, or before the Spring proxy is fully initialized.

---

## Follow-Up Questions Interviewers Ask

* How Spring AOP proxies work?
* Difference between JDK proxy and CGLIB?
* How to make @Transactional work across beans?
* Distributed transactions in microservices?

---

### Explain lazy vs eager loading in Spring Data JPA.
This is a **very common Spring Data JPA + Hibernate + production-bug question**. Interviewers usually want **real behavior + pitfalls**, not definitions.

I’ll explain **clearly**, then give **real code**, **SQL behavior**, and **production fixes**.

---

## 1️⃣ What Is Lazy vs Eager Loading?

> It defines **when related entities are fetched from the database**.

| Type  | When Data Is Loaded     |
| ----- | ----------------------- |
| Lazy  | Only when accessed      |
| Eager | Immediately with parent |

---

## 2️⃣ Default Fetch Types (INTERVIEW FAVORITE)

| Relationship  | Default |
| ------------- | ------- |
| `@ManyToOne`  | EAGER   |
| `@OneToOne`   | EAGER   |
| `@OneToMany`  | LAZY    |
| `@ManyToMany` | LAZY    |

📌 Always remember this table.

---

## 3️⃣ Lazy Loading (How It Works)

Hibernate uses **proxies**.

### Entity Example

```java
@Entity
public class Order {

    @Id
    private Long id;

    @OneToMany(fetch = FetchType.LAZY)
    private List<OrderItem> items;
}
```

### What Happens

```java
Order order = orderRepo.findById(1L).get();
order.getItems(); // SQL fired HERE
```

* First query loads `Order`
* Second query loads `OrderItem`

---

## 4️⃣ Lazy Loading Failure (🔥 LazyInitializationException)

### ❌ Problem

```java
Order order = orderRepo.findById(1L).get();
session.close();
order.getItems(); // 💥 exception
```

### Exception

```text
LazyInitializationException: could not initialize proxy
```

### Why?

* Hibernate session closed
* Proxy cannot fetch data

---

## 5️⃣ Eager Loading (How It Works)

```java
@Entity
public class Order {

    @ManyToOne(fetch = FetchType.EAGER)
    private Customer customer;
}
```

### SQL Behavior

```sql
SELECT o.*, c.*
FROM order o
LEFT JOIN customer c ON o.customer_id = c.id;
```

📌 Loaded immediately.

---

## 6️⃣ Eager Loading Problems (PRODUCTION PAIN)

❌ Loads unnecessary data
❌ Heavy joins
❌ Cartesian explosion
❌ Slower queries

📌 **Never use EAGER blindly**

---

## 7️⃣ N+1 Query Problem (MOST IMPORTANT)

### ❌ Problem

```java
List<Order> orders = orderRepo.findAll();

for (Order o : orders) {
    o.getItems().size(); // N+1 queries
}
```

### SQL

* 1 query for orders
* N queries for items

🔥 Performance killer.

---

## 8️⃣ Fix N+1 Problem (REAL SOLUTIONS)

---

### ✅ 1️⃣ Fetch Join (BEST)

```java
@Query("""
    SELECT o FROM Order o
    JOIN FETCH o.items
""")
List<Order> findAllWithItems();
```

✔ One SQL query
✔ Controlled eager loading

---

### ✅ 2️⃣ EntityGraph

```java
@EntityGraph(attributePaths = "items")
List<Order> findAll();
```

---

### ✅ 3️⃣ DTO Projection (Best for APIs)

```java
@Query("""
    SELECT new com.example.OrderDTO(o.id, i.name)
    FROM Order o JOIN o.items i
""")
List<OrderDTO> fetchOrderDTOs();
```

---

## 9️⃣ Transaction Scope Matters (REAL WORLD)

### Service Layer

```java
@Transactional
public Order getOrder(Long id) {
    return orderRepo.findById(id).get();
}
```

Lazy loading works **inside transaction**.

---

## 🔥 10️⃣ Best Practices (INTERVIEW GOLD)

* Prefer **LAZY** by default
* Use **fetch join** when needed
* Avoid EAGER in entities
* Use DTOs for REST APIs
* Keep transaction in service layer

---

## 11️⃣ Full Production Example

### Entity

```java
@Entity
class User {

    @OneToMany(fetch = FetchType.LAZY)
    List<Role> roles;
}
```

### Repository

```java
@Query("SELECT u FROM User u JOIN FETCH u.roles WHERE u.id = :id")
User findWithRoles(Long id);
```

---

## 🔥 One-Line Interview Answer

> Lazy loading fetches related entities on demand using proxies, while eager loading fetches them immediately, and improper use can cause performance issues like N+1 queries or LazyInitializationException.

---

## Follow-Up Questions Interviewers Ask

* What is N+1 problem?
* How Hibernate proxies work?
* Difference between fetch join and EntityGraph?
* Why EAGER is dangerous?


---

### How do you handle N+1 query issues?

This is a **real production performance problem** and a favorite Hibernate interview topic.

---

## 1️⃣ What Is the N+1 Query Problem?

> When Hibernate executes **1 query for parent + N queries for children**, causing massive DB load.

---

### Example Scenario

```java
List<Order> orders = orderRepository.findAll();

for (Order order : orders) {
    System.out.println(order.getItems().size());
}
```

---

### SQL Generated ❌

```sql
-- 1 query
SELECT * FROM orders;

-- N queries (for each order)
SELECT * FROM order_items WHERE order_id = 1;
SELECT * FROM order_items WHERE order_id = 2;
SELECT * FROM order_items WHERE order_id = 3;
...
```

If 1000 orders → **1001 queries**

🔥 This kills performance in production.

---

## 2️⃣ Why It Happens?

Because of **LAZY loading + iteration outside optimized fetch**.

Hibernate loads associations **one-by-one**.

---

## 3️⃣ How to Detect N+1 (Important)

Enable SQL logs:

```properties
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
```

Or use:

* Hibernate statistics
* APM tools (NewRelic, Dynatrace)
* Query count assertions in tests

---

## 4️⃣ Solutions to Fix N+1 (Production Techniques)

---

## ✅ Solution 1: Fetch Join (BEST & MOST USED)

Use JPQL fetch join to load in one query.

```java
@Query("""
    SELECT o FROM Order o
    JOIN FETCH o.items
""")
List<Order> findAllWithItems();
```

### SQL Generated ✔

```sql
SELECT o.*, i.*
FROM orders o
JOIN order_items i ON o.id = i.order_id;
```

✔ Single query
✔ No lazy loading

---

## ✅ Solution 2: Use `@EntityGraph` (Cleaner Alternative)

```java
@EntityGraph(attributePaths = {"items"})
List<Order> findAll();
```

Spring tells Hibernate:

> Load association eagerly **for this query only**.

✔ No entity-level EAGER needed.

---

## ✅ Solution 3: DTO Projection (Best for APIs)

Instead of loading entities, fetch only needed data.

```java
@Query("""
SELECT new com.app.dto.OrderDTO(o.id, i.name)
FROM Order o
JOIN o.items i
""")
List<OrderDTO> fetchOrders();
```

✔ No persistence context overhead
✔ Fastest for read APIs.

---

## ✅ Solution 4: Batch Fetching

Hibernate loads associations in batches instead of one-by-one.

### Enable Batch Size

```properties
spring.jpa.properties.hibernate.default_batch_fetch_size=50
```

Or:

```java
@OneToMany
@BatchSize(size = 50)
private List<OrderItem> items;
```

Now Hibernate runs:

```sql
SELECT * FROM order_items WHERE order_id IN (1,2,3,...50);
```

✔ Reduces N+1 to **N/50**

---

## ✅ Solution 5: Avoid Open Session in View (OSIV Trap)

OSIV hides N+1 by delaying loading to controller layer.

Disable it:

```properties
spring.jpa.open-in-view=false
```

Forces proper fetching in service layer.

---

## 5️⃣ What NOT To Do ❌

| Anti-Pattern             | Why Bad                           |
| ------------------------ | --------------------------------- |
| Set `FetchType.EAGER`    | Creates bigger performance issues |
| Use OSIV                 | Hides N+1 instead of fixing       |
| Call lazy inside loop    | Classic trigger                   |
| Load entire entity graph | Memory explosion                  |

---

## 6️⃣ Real Production Strategy (Recommended)

✔ Keep associations **LAZY**
✔ Use **fetch join per use-case**
✔ Use DTOs for APIs
✔ Enable batch fetching globally

---

## 7️⃣ Full Example (Production Ready)

### Entity

```java
@Entity
class Order {

    @OneToMany(mappedBy = "order", fetch = FetchType.LAZY)
    private List<OrderItem> items;
}
```

---

### Repository

```java
@Repository
public interface OrderRepository extends JpaRepository<Order, Long> {

    @Query("""
        SELECT DISTINCT o FROM Order o
        JOIN FETCH o.items
    """)
    List<Order> findOrdersWithItems();
}
```

---

### Service

```java
@Service
public class OrderService {

    private final OrderRepository repo;

    public OrderService(OrderRepository repo) {
        this.repo = repo;
    }

    @Transactional(readOnly = true)
    public List<Order> getOrders() {
        return repo.findOrdersWithItems();
    }
}
```

---

## 🔥 One-Line Interview Answer

> N+1 occurs when Hibernate lazily loads associations in separate queries; it is solved using fetch joins, EntityGraphs, DTO projections, or batch fetching rather than switching to EAGER loading.

---

## Follow-Up Questions Interviewers Ask

* Difference between fetch join and EntityGraph?
* Why DISTINCT needed in fetch join?
* How batch fetching works internally?
* Why OSIV is dangerous?


---

### Difference between JpaRepository and CrudRepository.

This is a **Spring Data JPA basics + design-choice question**. Interviewers want to see if you know **when to use which** and what extra power `JpaRepository` gives.

---

## 1️⃣ Relationship Between Them

```
Repository
   ↑
CrudRepository
   ↑
PagingAndSortingRepository
   ↑
JpaRepository
```

👉 `JpaRepository` **extends** `CrudRepository` (and adds more features).

---

## 2️⃣ CrudRepository (Basic CRUD Only)

> Provides **minimal operations** for generic persistence.

### Key Methods

```java
save()
findById()
findAll()
delete()
count()
existsById()
```

### Example

```java
public interface UserRepository extends CrudRepository<User, Long> {
}
```

📌 Works with any Spring Data store (not JPA-specific).

---

## 3️⃣ JpaRepository (JPA-Specific + Advanced Features)

> Adds JPA + Hibernate-specific functionality and batch operations.

Extends:

* `CrudRepository`
* `PagingAndSortingRepository`

---

### Extra Methods Available

| Feature           | Method                       |
| ----------------- | ---------------------------- |
| Pagination        | `findAll(Pageable pageable)` |
| Sorting           | `findAll(Sort sort)`         |
| Batch Insert      | `saveAll()`                  |
| Batch Delete      | `deleteAllInBatch()`         |
| Flush Persistence | `flush()`                    |
| Lazy Reference    | `getReferenceById()`         |

---

### Example

```java
public interface UserRepository extends JpaRepository<User, Long> {
}
```

---

## 4️⃣ Key Functional Differences

| Feature                   | CrudRepository | JpaRepository |
| ------------------------- | -------------- | ------------- |
| Basic CRUD                | ✅              | ✅             |
| Pagination                | ❌              | ✅             |
| Sorting                   | ❌              | ✅             |
| Batch operations          | ❌              | ✅             |
| Flush control             | ❌              | ✅             |
| JPA-specific optimization | ❌              | ✅             |
| getReference (lazy proxy) | ❌              | ✅             |

---

## 5️⃣ Real Production Example Difference

### Using CrudRepository ❌ (Limited)

```java
Iterable<User> users = userRepo.findAll();
```

You must manually handle pagination.

---

### Using JpaRepository ✅

```java
Page<User> page = userRepo.findAll(PageRequest.of(0, 10));
```

✔ Database-level pagination
✔ Efficient queries

---

## 6️⃣ Why JpaRepository Is Preferred in Real Projects

Because it supports:

* Pagination APIs
* Batch processing
* Persistence context control
* Better performance tools
* Hibernate integration

👉 Almost **all Spring Boot JPA apps use JpaRepository**.

---

## 7️⃣ Flush Example (Important)

```java
userRepository.save(user);
userRepository.flush(); // forces SQL execution immediately
```

Useful for:

* Stored procedures
* Validation before commit
* Bulk processing

---

## 8️⃣ Batch Delete Example

```java
userRepository.deleteAllInBatch();
```

Runs:

```sql
DELETE FROM users;
```

Instead of deleting row-by-row.

---

## 9️⃣ When Would You Use CrudRepository?

Rare cases:

* Non-JPA datastore (Mongo, Redis)
* Extremely simple service
* Want strict abstraction

---

## 🔥 One-Line Interview Answer

> `CrudRepository` provides basic CRUD operations, while `JpaRepository` extends it with JPA-specific features like pagination, sorting, batch operations, and persistence context control, making it the preferred choice for JPA-based applications.

---

## Follow-Up Questions Interviewers Ask

* Difference between `getById()` and `findById()`?
* What is flush in Hibernate?
* How pagination works internally?
* Why batch operations are faster?

---
### How do you implement pagination and sorting efficiently?
Efficient pagination & sorting is **critical for performance** (especially in APIs returning large datasets). The goal is to **push work to the database**, avoid loading unnecessary rows, and prevent memory/CPU overhead in the JVM.

---

## 1️⃣ Use Database-Level Pagination (NEVER In-Memory)

> Always paginate using SQL `LIMIT/OFFSET` (or keyset pagination), not Java streams.

### ❌ Bad (Loads everything into memory)

```java
List<User> users = userRepository.findAll();
return users.stream().skip(1000).limit(20).toList();
```

➡ Loads entire table → OOM risk.

---

### ✅ Correct Way (Spring Data Pageable)

```java
Page<User> page = userRepository.findAll(
        PageRequest.of(0, 20, Sort.by("createdAt").descending())
);
```

Spring generates:

```sql
SELECT * FROM users
ORDER BY created_at DESC
LIMIT 20 OFFSET 0;
```

✔ Efficient
✔ Uses DB index
✔ Returns only needed rows.

---

## 2️⃣ Repository Implementation

```java
@Repository
public interface UserRepository extends JpaRepository<User, Long> {

    Page<User> findByStatus(String status, Pageable pageable);
}
```

---

## 3️⃣ Service Layer (Best Practice)

```java
@Service
public class UserService {

    private final UserRepository repo;

    public UserService(UserRepository repo) {
        this.repo = repo;
    }

    @Transactional(readOnly = true)
    public Page<User> getActiveUsers(int page, int size) {

        Pageable pageable = PageRequest.of(
                page,
                size,
                Sort.by(Sort.Direction.DESC, "createdAt")
        );

        return repo.findByStatus("ACTIVE", pageable);
    }
}
```

---

## 4️⃣ Controller Example (Production Style API)

```java
@RestController
@RequestMapping("/users")
public class UserController {

    private final UserService service;

    public UserController(UserService service) {
        this.service = service;
    }

    @GetMapping
    public Page<User> list(
            @RequestParam int page,
            @RequestParam int size) {

        return service.getActiveUsers(page, size);
    }
}
```

---

## 5️⃣ Important Performance Optimizations

---

### ✅ Add Database Index (MANDATORY)

Sorting without index = full table scan.

```sql
CREATE INDEX idx_users_created_at ON users(created_at DESC);
```

---

### ✅ Use DTO Projection (Avoid Loading Full Entity)

If entity has relationships, pagination may trigger N+1.

```java
@Query("""
SELECT new com.app.dto.UserDTO(u.id, u.name, u.createdAt)
FROM User u
WHERE u.status = :status
""")
Page<UserDTO> findUsers(String status, Pageable pageable);
```

✔ Fetches only required columns
✔ Much faster.

---

### ✅ Avoid `fetch join` with pagination (Common Mistake)

```java
-- ❌ This breaks pagination in Hibernate
JOIN FETCH u.roles
```

Because it creates duplicate rows → wrong page count.

---

### ✔ Instead Use Two-Step Query Pattern

1️⃣ Fetch IDs with pagination
2️⃣ Fetch associations separately

---

### ✅ Use Slice Instead of Page When Count Is Expensive

`Page` runs an extra query:

```sql
SELECT COUNT(*)
```

If total count not needed → use `Slice`.

```java
Slice<User> slice = repo.findByStatus("ACTIVE", pageable);
```

✔ No count query
✔ Faster for large datasets.

---

## 6️⃣ Keyset Pagination (For Very Large Tables 🚀)

OFFSET becomes slow after millions of rows.

### Instead of:

```sql
LIMIT 20 OFFSET 1000000
```

Use:

```sql
WHERE id < lastSeenId
ORDER BY id DESC
LIMIT 20
```

---

### Spring Implementation

```java
@Query("""
SELECT u FROM User u
WHERE u.id < :lastId
ORDER BY u.id DESC
""")
List<User> findNextPage(Long lastId, Pageable pageable);
```

✔ Scales to billions of rows
✔ Used in real systems like feeds/logs.

---

## 7️⃣ Common Pagination Mistakes (Interview Favorites)

| Mistake                    | Impact               |
| -------------------------- | -------------------- |
| In-memory pagination       | OOM + slow           |
| Sorting without index      | Table scan           |
| Using `Page` unnecessarily | Extra count query    |
| Fetch join with paging     | Wrong results        |
| Large OFFSET               | Performance collapse |

---

## 8️⃣ Best-Practice Strategy (Real Projects)

✔ Use `Pageable` for normal pagination
✔ Use DTO projections
✔ Index all sortable columns
✔ Use `Slice` if count not needed
✔ Use keyset pagination for large datasets
✔ Never paginate in Java memory

---

## 🔥 One-Line Interview Answer

> Efficient pagination in Spring Data JPA is implemented using `Pageable` to delegate LIMIT/OFFSET to the database, combined with indexed sorting, DTO projections, and keyset pagination for large datasets to avoid performance bottlenecks.

---

## Follow-Up Questions Interviewers Ask

* Difference between `Page` and `Slice`?
* Why fetch join breaks pagination?
* How keyset pagination improves performance?
* How to paginate with joins safely?

---
### How do you secure Spring Boot applications?

Securing a Spring Boot application means protecting **authentication, authorization, data, APIs, and infrastructure** using layered security (App + Transport + DB + DevSecOps).

---

# 1️⃣ Add Spring Security (Foundation)

Include dependency:

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-security</artifactId>
</dependency>
```

Spring Boot automatically:

* Enables authentication
* Protects all endpoints
* Adds CSRF protection
* Uses secure password hashing

---

# 2️⃣ Configure Authentication (JWT / OAuth2 Recommended)

## ✅ Modern Approach → Stateless JWT Security

---

### Security Configuration

```java
@Configuration
@EnableWebSecurity
public class SecurityConfig {

    @Bean
    public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {

        http
            .csrf(csrf -> csrf.disable())
            .sessionManagement(sm -> sm.sessionCreationPolicy(SessionCreationPolicy.STATELESS))
            .authorizeHttpRequests(auth -> auth
                    .requestMatchers("/auth/**").permitAll()
                    .requestMatchers("/admin/**").hasRole("ADMIN")
                    .anyRequest().authenticated()
            )
            .addFilterBefore(jwtFilter(), UsernamePasswordAuthenticationFilter.class);

        return http.build();
    }

    @Bean
    public JwtAuthenticationFilter jwtFilter() {
        return new JwtAuthenticationFilter();
    }
}
```

---

# 3️⃣ JWT Authentication Filter

```java
public class JwtAuthenticationFilter extends OncePerRequestFilter {

    @Override
    protected void doFilterInternal(HttpServletRequest request,
                                    HttpServletResponse response,
                                    FilterChain chain)
                                    throws ServletException, IOException {

        String header = request.getHeader("Authorization");

        if (header != null && header.startsWith("Bearer ")) {

            String token = header.substring(7);
            String username = JwtUtil.validateToken(token);

            UsernamePasswordAuthenticationToken auth =
                    new UsernamePasswordAuthenticationToken(username, null, List.of());

            SecurityContextHolder.getContext().setAuthentication(auth);
        }

        chain.doFilter(request, response);
    }
}
```

---

# 4️⃣ Password Security (Never Store Plain Passwords)

Use BCrypt hashing:

```java
@Bean
public PasswordEncoder passwordEncoder() {
    return new BCryptPasswordEncoder();
}
```

Saving user:

```java
user.setPassword(passwordEncoder.encode(rawPassword));
```

---

# 5️⃣ Authorization (Role-Based Access Control)

```java
@PreAuthorize("hasRole('ADMIN')")
@GetMapping("/admin/data")
public String secureEndpoint() {
    return "Only admin";
}
```

Enable method security:

```java
@EnableMethodSecurity
```

---

# 6️⃣ Protect Against Common Attacks

| Attack         | Protection                     |
| -------------- | ------------------------------ |
| SQL Injection  | Use JPA / PreparedStatements   |
| XSS            | Validate input + encode output |
| CSRF           | Enable for web apps            |
| Brute Force    | Rate limiting                  |
| Session Hijack | Use HTTPS                      |
| Password Theft | BCrypt hashing                 |

---

# 7️⃣ Secure Configuration (Never Hardcode Secrets)

❌ Bad:

```properties
spring.datasource.password=root123
```

✅ Use Environment Variables:

```properties
spring.datasource.password=${DB_PASSWORD}
```

Or Secret Manager (Azure Key Vault / OCI Vault).

---

# 8️⃣ Enable HTTPS (Transport Security)

Configure SSL:

```properties
server.port=8443
server.ssl.key-store=classpath:keystore.p12
server.ssl.key-store-password=changeit
server.ssl.keyStoreType=PKCS12
```

---

# 9️⃣ API Validation (Prevent Malicious Input)

```java
@PostMapping("/users")
public ResponseEntity<?> createUser(@Valid @RequestBody UserRequest req) {
}
```

DTO:

```java
public class UserRequest {

    @NotBlank
    private String username;

    @Email
    private String email;
}
```

---

# 🔟 Secure Headers (Important for Web Security)

```java
http.headers(headers -> headers
        .contentSecurityPolicy("default-src 'self'")
        .frameOptions().deny()
);
```

Adds:

* X-Frame-Options
* CSP
* HSTS

---

# 11️⃣ Logging & Monitoring (Security Visibility)

Log authentication failures:

```java
log.warn("Unauthorized access attempt: {}", username);
```

Use:

* SIEM integration
* Audit logs
* Alerting

---

# 12️⃣ DevSecOps Practices (Interview Must Mention)

✔ Use dependency scanning (OWASP Dependency Check)
✔ Container scanning
✔ Secret scanning
✔ SAST / DAST tools
✔ Rotate keys regularly
✔ Zero-trust architecture

---

# 13️⃣ Production Security Architecture

```
Client → API Gateway → Spring Boot (JWT Validation)
                     ↓
               RBAC + Validation
                     ↓
             Database (Encrypted)
                     ↓
            Secrets from Vault
```

---

# 🔥 One-Line Interview Answer

> Spring Boot applications are secured using Spring Security with JWT/OAuth2 authentication, role-based authorization, encrypted passwords, HTTPS, input validation, secure headers, and DevSecOps practices like secret management and vulnerability scanning.

---

# Follow-Up Questions Interviewers Ask

* Difference between OAuth2 and JWT?
* How to secure microservices?
* How to implement refresh tokens?
* How to integrate Azure AD / B2C?

---
