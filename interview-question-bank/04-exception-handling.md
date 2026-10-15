# 4. Exception Handling

> Source range: questions 71–85
## 71. What is exception handling?

1. **Question**: What is exception handling?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: Exception handling lets a program detect, propagate, and recover from abnormal conditions without mixing failure logic into every normal path.
6. **Detailed explanation**: Exception handling lets a program detect, propagate, and recover from abnormal conditions without mixing failure logic into every normal path. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “What is exception handling?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: Exception handling lets a program detect, propagate, and recover from abnormal conditions without mixing failure logic into every normal path.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 72. Checked vs unchecked exceptions?

1. **Question**: Checked vs unchecked exceptions?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: Checked exceptions must be caught or declared and represent conditions a caller may reasonably recover from. Unchecked exceptions extend RuntimeException and usually indicate programming errors or invalid state.
6. **Detailed explanation**: Checked exceptions must be caught or declared and represent conditions a caller may reasonably recover from. Unchecked exceptions extend RuntimeException and usually indicate programming errors or invalid state. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “Checked vs unchecked exceptions?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: Checked exceptions must be caught or declared and represent conditions a caller may reasonably recover from. Unchecked exceptions extend RuntimeException and usually indicate programming errors or invalid state.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 73. Error vs Exception?

1. **Question**: Error vs Exception?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: An Error represents serious JVM or environment failure and is generally not recovered from. An Exception represents conditions an application may handle or report.
6. **Detailed explanation**: An Error represents serious JVM or environment failure and is generally not recovered from. An Exception represents conditions an application may handle or report. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “Error vs Exception?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: An Error represents serious JVM or environment failure and is generally not recovered from. An Exception represents conditions an application may handle or report.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 74. throw vs throws?

1. **Question**: throw vs throws?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: throw explicitly raises one exception object. throws declares exceptions a method may propagate to its caller; it does not itself throw anything.
6. **Detailed explanation**: throw explicitly raises one exception object. throws declares exceptions a method may propagate to its caller; it does not itself throw anything. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “throw vs throws?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: throw explicitly raises one exception object. throws declares exceptions a method may propagate to its caller; it does not itself throw anything.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 75. Can you have try without catch?

1. **Question**: Can you have try without catch?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: Yes. A try must be followed by catch, finally, or both. try-with-resources is also valid and supplies implicit cleanup.
6. **Detailed explanation**: Yes. A try must be followed by catch, finally, or both. try-with-resources is also valid and supplies implicit cleanup. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “Can you have try without catch?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: Yes. A try must be followed by catch, finally, or both. try-with-resources is also valid and supplies implicit cleanup.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 76. How does try-catch-finally work?

1. **Question**: How does try-catch-finally work?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: try executes normal work, catch handles matching failures, and finally runs cleanup after either success or failure, except in termination cases such as JVM halt.
6. **Detailed explanation**: try executes normal work, catch handles matching failures, and finally runs cleanup after either success or failure, except in termination cases such as JVM halt. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “How does try-catch-finally work?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: try executes normal work, catch handles matching failures, and finally runs cleanup after either success or failure, except in termination cases such as JVM halt.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 77. When does finally not execute?

1. **Question**: When does finally not execute?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: finally may not execute if the JVM exits or halts, the process is killed, the machine fails, or control never leaves the try because of an infinite loop.
6. **Detailed explanation**: finally may not execute if the JVM exits or halts, the process is killed, the machine fails, or control never leaves the try because of an infinite loop. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “When does finally not execute?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: finally may not execute if the JVM exits or halts, the process is killed, the machine fails, or control never leaves the try because of an infinite loop.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 78. What is try-with-resources?

1. **Question**: What is try-with-resources?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: Try-with-resources automatically closes AutoCloseable resources in reverse declaration order, even when the body throws. Close failures are suppressed onto the primary exception.
6. **Detailed explanation**: Try-with-resources automatically closes AutoCloseable resources in reverse declaration order, even when the body throws. Close failures are suppressed onto the primary exception. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “What is try-with-resources?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try { throw new IllegalStateException("invalid state"); }
catch (IllegalStateException ex) { System.out.println(ex.getMessage()); }
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: Try-with-resources automatically closes AutoCloseable resources in reverse declaration order, even when the body throws. Close failures are suppressed onto the primary exception.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 79. What is AutoCloseable?

1. **Question**: What is AutoCloseable?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: AutoCloseable defines close() throws Exception, allowing a resource to participate in try-with-resources. Closeable is the narrower I/O interface that throws IOException.
6. **Detailed explanation**: AutoCloseable defines close() throws Exception, allowing a resource to participate in try-with-resources. Closeable is the narrower I/O interface that throws IOException. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “What is AutoCloseable?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: AutoCloseable defines close() throws Exception, allowing a resource to participate in try-with-resources. Closeable is the narrower I/O interface that throws IOException.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 80. How do you create a custom exception?

1. **Question**: How do you create a custom exception?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: Create a class extending Exception for a checked exception or RuntimeException for an unchecked one, provide meaningful constructors, and preserve the cause.
6. **Detailed explanation**: Create a class extending Exception for a checked exception or RuntimeException for an unchecked one, provide meaningful constructors, and preserve the cause. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “How do you create a custom exception?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: Create a class extending Exception for a checked exception or RuntimeException for an unchecked one, provide meaningful constructors, and preserve the cause.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 81. What happens if both try and finally return values?

1. **Question**: What happens if both try and finally return values?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: If both try and finally return, finally wins and hides the try return or exception. Returning from finally is therefore strongly discouraged.
6. **Detailed explanation**: If both try and finally return, finally wins and hides the try return or exception. Returning from finally is therefore strongly discouraged. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “What happens if both try and finally return values?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: If both try and finally return, finally wins and hides the try return or exception. Returning from finally is therefore strongly discouraged.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 82. How should exceptions be handled in production applications?

1. **Question**: How should exceptions be handled in production applications?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: Handle exceptions at the layer that can recover, translate them at boundaries, preserve causes, log actionable context without secrets, and return stable error responses.
6. **Detailed explanation**: Handle exceptions at the layer that can recover, translate them at boundaries, preserve causes, log actionable context without secrets, and return stable error responses. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “How should exceptions be handled in production applications?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: Handle exceptions at the layer that can recover, translate them at boundaries, preserve causes, log actionable context without secrets, and return stable error responses.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 83. Why is catching `Exception` generally discouraged?

1. **Question**: Why is catching `Exception` generally discouraged?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: Catching Exception can hide programming defects and make recovery incorrect. Catch the narrowest type you can handle and let unexpected failures propagate.
6. **Detailed explanation**: Catching Exception can hide programming defects and make recovery incorrect. Catch the narrowest type you can handle and let unexpected failures propagate. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “Why is catching `Exception` generally discouraged?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: Catching Exception can hide programming defects and make recovery incorrect. Catch the narrowest type you can handle and let unexpected failures propagate.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 84. How do you design application-specific exceptions?

1. **Question**: How do you design application-specific exceptions?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: Application exceptions should represent stable business or infrastructure categories, carry safe error codes and context, preserve causes, and map consistently to transport responses.
6. **Detailed explanation**: Application exceptions should represent stable business or infrastructure categories, carry safe error codes and context, preserve causes, and map consistently to transport responses. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “How do you design application-specific exceptions?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: Application exceptions should represent stable business or infrastructure categories, carry safe error codes and context, preserve causes, and map consistently to transport responses.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---

## 85. How do you implement global exception handling in Spring Boot?

1. **Question**: How do you implement global exception handling in Spring Boot?
2. **Difficulty**: Intermediate
3. **Topic**: Java → Exception Handling
4. **What interviewer is testing**: Whether you understand the rule, failure behavior, and safe production use.
5. **Short interview answer (30–60 seconds)**: Use @RestControllerAdvice with @ExceptionHandler methods to map domain, validation, and unexpected exceptions to consistent status codes and response bodies.
6. **Detailed explanation**: Use @RestControllerAdvice with @ExceptionHandler methods to map domain, validation, and unexpected exceptions to consistent status codes and response bodies. The service handles the relevant edge cases before state changes or external calls.
7. **How it works internally**: The JVM or framework applies the rule during compilation, execution, resource handling, or request processing; failures propagate according to the defined contract.
8. **Example**:

For “How do you implement global exception handling in Spring Boot?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
try (var resource = new java.io.StringReader("data")) {
    System.out.println(resource.read());
} catch (java.io.IOException ex) {
    throw new IllegalStateException("read failed", ex);
}
```




10. **Time & space complexity**: Report the complexity of the concrete operation; exception handling and language rules themselves do not have one universal complexity.
11. **Real-world/project usage**: This appears at service boundaries, validation, persistence, integrations, scheduled jobs, and operational diagnostics.
12. **Common mistakes**: Catching too broadly, losing the original cause, exposing sensitive details, or treating exceptional control flow as normal logic.
13. **Advantages**: Clear failure contracts, safer cleanup, and better recovery when used at the correct boundary.
14. **Limitations**: Poor handling can hide defects, add latency, or produce inconsistent state.
15. **Comparison with related concepts**: Compare checked and unchecked failures, local and global handling, and synchronous and asynchronous propagation.
16. **Production considerations**: Log with correlation IDs, preserve causes, return safe client responses, clean up resources, monitor rates, and test failure paths.
17. **Possible follow-up questions**: What happens on null input, nested failures, retries, or partial completion?
18. **Senior-level follow-up questions**: How would you design an error taxonomy, observability, retry policy, and backward-compatible API contract?
19. **Scenario-based question**: A downstream failure causes repeated errors in production. Explain how you would classify it, contain it, expose a safe response, and prevent recurrence.
20. **One-line revision note**: Use @RestControllerAdvice with @ExceptionHandler methods to map domain, validation, and unexpected exceptions to consistent status codes and response bodies.
21. **Image visuals (if required)**: An exception propagation or resource-lifecycle diagram helps when control flow is complex.

---
