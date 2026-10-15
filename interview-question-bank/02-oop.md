# 2. OOP

> Source range: questions 21–40
## 21. What are the four pillars of OOP?

1. **Question**: What are the four pillars of OOP?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: The four pillars are encapsulation, abstraction, inheritance, and polymorphism. Together they hide implementation details, model shared behavior, and allow one interface to support multiple implementations.
6. **Detailed explanation**: The four pillars are encapsulation, abstraction, inheritance, and polymorphism. Together they hide implementation details, model shared behavior, and allow one interface to support multiple implementations. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “What are the four pillars of OOP?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Payment { void pay(long cents); }
final class CardPayment implements Payment {
    public void pay(long cents) { System.out.println("paid " + cents); }
}
```




10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: The four pillars are encapsulation, abstraction, inheritance, and polymorphism. Together they hide implementation details, model shared behavior, and allow one interface to support multiple implementations.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 22. Explain encapsulation with a practical example.

1. **Question**: Explain encapsulation with a practical example.
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Encapsulation keeps state private and exposes controlled operations. For example, a BankAccount keeps balance private and allows deposit only after validating that the amount is positive.
6. **Detailed explanation**: Encapsulation keeps state private and exposes controlled operations. For example, a BankAccount keeps balance private and allows deposit only after validating that the amount is positive. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “Explain encapsulation with a practical example.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
final class BankAccount { private long balance; void deposit(long cents) { if (cents <= 0) throw new IllegalArgumentException(); balance += cents; } }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Encapsulation keeps state private and exposes controlled operations. For example, a BankAccount keeps balance private and allows deposit only after validating that the amount is positive.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 23. Explain abstraction with a practical example.

1. **Question**: Explain abstraction with a practical example.
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Abstraction exposes what an object does while hiding how it does it. A PaymentService interface can expose pay(), while card and UPI implementations hide provider-specific details.
6. **Detailed explanation**: Abstraction exposes what an object does while hiding how it does it. A PaymentService interface can expose pay(), while card and UPI implementations hide provider-specific details. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “Explain abstraction with a practical example.”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Payment { void pay(long cents); }
final class CardPayment implements Payment {
    public void pay(long cents) { System.out.println("paid " + cents); }
}
```




10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Abstraction exposes what an object does while hiding how it does it. A PaymentService interface can expose pay(), while card and UPI implementations hide provider-specific details.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 24. What is inheritance?

1. **Question**: What is inheritance?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Inheritance lets a subclass reuse and specialize accessible state and behavior from a superclass. Java supports single class inheritance and avoids multiple class inheritance ambiguity.
6. **Detailed explanation**: Inheritance lets a subclass reuse and specialize accessible state and behavior from a superclass. Java supports single class inheritance and avoids multiple class inheritance ambiguity. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “What is inheritance?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
class Animal { void speak() {} } class Dog extends Animal { @Override void speak() {} }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Inheritance lets a subclass reuse and specialize accessible state and behavior from a superclass. Java supports single class inheritance and avoids multiple class inheritance ambiguity.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 25. What is polymorphism?

1. **Question**: What is polymorphism?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Polymorphism means the same operation can behave differently for different objects. An overridden method is selected at runtime based on the actual object type.
6. **Detailed explanation**: Polymorphism means the same operation can behave differently for different objects. An overridden method is selected at runtime based on the actual object type. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “What is polymorphism?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
Animal animal = new Dog(); animal.speak();
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Polymorphism means the same operation can behave differently for different objects. An overridden method is selected at runtime based on the actual object type.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 26. Compile-time vs runtime polymorphism?

1. **Question**: Compile-time vs runtime polymorphism?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Compile-time polymorphism is method overloading resolved by the compiler. Runtime polymorphism is method overriding resolved by dynamic dispatch when the program runs.
6. **Detailed explanation**: Compile-time polymorphism is method overloading resolved by the compiler. Runtime polymorphism is method overriding resolved by dynamic dispatch when the program runs. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “Compile-time vs runtime polymorphism?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
int sum(int a,int b){return a+b;} double sum(double a,double b){return a+b;}
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Compile-time polymorphism is method overloading resolved by the compiler. Runtime polymorphism is method overriding resolved by dynamic dispatch when the program runs.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 27. Method overloading vs method overriding?

1. **Question**: Method overloading vs method overriding?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Overloading uses the same method name with different parameter lists in one class. Overriding supplies a compatible implementation in a subclass; it requires the same signature and cannot reduce visibility.
6. **Detailed explanation**: Overloading uses the same method name with different parameter lists in one class. Overriding supplies a compatible implementation in a subclass; it requires the same signature and cannot reduce visibility. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “Method overloading vs method overriding?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
class Base { void run(){} } class Child extends Base { @Override void run(){} }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Overloading uses the same method name with different parameter lists in one class. Overriding supplies a compatible implementation in a subclass; it requires the same signature and cannot reduce visibility.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 28. Can static methods be overridden?

1. **Question**: Can static methods be overridden?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Static methods are hidden, not overridden. A call through a class or reference is resolved from the declared type, so static dispatch is compile-time based.
6. **Detailed explanation**: Static methods are hidden, not overridden. A call through a class or reference is resolved from the declared type, so static dispatch is compile-time based. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “Can static methods be overridden?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
class Parent { static void ping(){} } class Child extends Parent { static void ping(){} }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Static methods are hidden, not overridden. A call through a class or reference is resolved from the declared type, so static dispatch is compile-time based.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 29. Can private methods be overridden?

1. **Question**: Can private methods be overridden?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Private methods are not inherited and therefore cannot be overridden. A subclass method with the same signature is a separate method.
6. **Detailed explanation**: Private methods are not inherited and therefore cannot be overridden. A subclass method with the same signature is a separate method. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “Can private methods be overridden?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
class Parent { private void audit(){} } class Child extends Parent { void audit(){} }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Private methods are not inherited and therefore cannot be overridden. A subclass method with the same signature is a separate method.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 30. Can final methods be overridden?

1. **Question**: Can final methods be overridden?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: A final instance method cannot be overridden because its implementation is fixed by the declaring class. It can still be overloaded with a different parameter list.
6. **Detailed explanation**: A final instance method cannot be overridden because its implementation is fixed by the declaring class. It can still be overloaded with a different parameter list. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “Can final methods be overridden?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
class Parent { final void id(){} } // id cannot be overridden
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: A final instance method cannot be overridden because its implementation is fixed by the declaring class. It can still be overloaded with a different parameter list.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 31. Abstract class vs interface?

1. **Question**: Abstract class vs interface?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: An abstract class can hold state, constructors, and implemented methods, while an interface defines a contract and supports multiple inheritance of type. Use an abstract class for shared base behavior and an interface for a capability.
6. **Detailed explanation**: An abstract class can hold state, constructors, and implemented methods, while an interface defines a contract and supports multiple inheritance of type. Use an abstract class for shared base behavior and an interface for a capability. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “Abstract class vs interface?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
abstract class Report { abstract byte[] render(); } interface Auditable { void audit(); }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: An abstract class can hold state, constructors, and implemented methods, while an interface defines a contract and supports multiple inheritance of type. Use an abstract class for shared base behavior and an interface for a capability.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 32. When would you choose an abstract class over an interface?

1. **Question**: When would you choose an abstract class over an interface?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Choose an abstract class when related classes share state or protected implementation. Choose an interface when unrelated classes need a common contract or when multiple capabilities are required.
6. **Detailed explanation**: Choose an abstract class when related classes share state or protected implementation. Choose an interface when unrelated classes need a common contract or when multiple capabilities are required. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “When would you choose an abstract class over an interface?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
abstract class Template { abstract void execute(); void run(){execute();} }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Choose an abstract class when related classes share state or protected implementation. Choose an interface when unrelated classes need a common contract or when multiple capabilities are required.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 33. Can an interface have methods with implementation?

1. **Question**: Can an interface have methods with implementation?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Yes. Interfaces can contain default and static methods with implementations, and since Java 9 they can also contain private helper methods. Implementing classes must still provide abstract methods.
6. **Detailed explanation**: Yes. Interfaces can contain default and static methods with implementations, and since Java 9 they can also contain private helper methods. Implementing classes must still provide abstract methods. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “Can an interface have methods with implementation?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Greeting { default String text(){return "hi";} }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Yes. Interfaces can contain default and static methods with implementations, and since Java 9 they can also contain private helper methods. Implementing classes must still provide abstract methods.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 34. What are default methods?

1. **Question**: What are default methods?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: A default method is an interface method with a body. It lets a library evolve an interface without forcing every existing implementation to add the method immediately.
6. **Detailed explanation**: A default method is an interface method with a body. It lets a library evolve an interface without forcing every existing implementation to add the method immediately. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “What are default methods?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface Clock { static int seconds(){return 60;} }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: A default method is an interface method with a body. It lets a library evolve an interface without forcing every existing implementation to add the method immediately.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 35. What are static interface methods?

1. **Question**: What are static interface methods?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: A static interface method belongs to the interface itself and is called with InterfaceName.method(). It is not inherited or overridden by implementing classes.
6. **Detailed explanation**: A static interface method belongs to the interface itself and is called with InterfaceName.method(). It is not inherited or overridden by implementing classes. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “What are static interface methods?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
interface A { default void run(){} } interface B { default void run(){} }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: A static interface method belongs to the interface itself and is called with InterfaceName.method(). It is not inherited or overridden by implementing classes.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 36. What is multiple inheritance, and how does Java handle it?

1. **Question**: What is multiple inheritance, and how does Java handle it?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Java does not allow a class to extend multiple classes, which avoids state and method ambiguity. A class can implement multiple interfaces; conflicts between default methods must be resolved explicitly.
6. **Detailed explanation**: Java does not allow a class to extend multiple classes, which avoids state and method ambiguity. A class can implement multiple interfaces; conflicts between default methods must be resolved explicitly. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “What is multiple inheritance, and how does Java handle it?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
class Service implements A,B { public void run(){ A.super.run(); } }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Java does not allow a class to extend multiple classes, which avoids state and method ambiguity. A class can implement multiple interfaces; conflicts between default methods must be resolved explicitly.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 37. What is the diamond problem?

1. **Question**: What is the diamond problem?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: The diamond problem occurs when a class inherits the same method through two paths and the implementation is ambiguous. Java avoids it for classes and requires an override when interface defaults conflict.
6. **Detailed explanation**: The diamond problem occurs when a class inherits the same method through two paths and the implementation is ambiguous. Java avoids it for classes and requires an override when interface defaults conflict. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “What is the diamond problem?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
class C implements A,B { public void run(){ A.super.run(); } }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: The diamond problem occurs when a class inherits the same method through two paths and the implementation is ambiguous. Java avoids it for classes and requires an override when interface defaults conflict.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 38. Association vs aggregation vs composition?

1. **Question**: Association vs aggregation vs composition?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Association is a general relationship. Aggregation is a weak whole-part relationship where parts can exist independently. Composition is strong ownership: the part lifecycle is controlled by the whole.
6. **Detailed explanation**: Association is a general relationship. Aggregation is a weak whole-part relationship where parts can exist independently. Composition is strong ownership: the part lifecycle is controlled by the whole. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “Association vs aggregation vs composition?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
class Employee { private final Department department; Employee(Department d){department=d;} }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Association is a general relationship. Aggregation is a weak whole-part relationship where parts can exist independently. Composition is strong ownership: the part lifecycle is controlled by the whole.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 39. Composition vs inheritance—which would you choose and why?

1. **Question**: Composition vs inheritance—which would you choose and why?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: Prefer composition when behavior should vary or ownership is not a true is-a relationship. Inheritance is appropriate for a stable subtype relationship and safe substitutability under LSP.
6. **Detailed explanation**: Prefer composition when behavior should vary or ownership is not a true is-a relationship. Inheritance is appropriate for a stable subtype relationship and safe substitutability under LSP. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “Composition vs inheritance—which would you choose and why?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
final class Order { private final Payment payment; Order(Payment p){payment=p;} }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: Prefer composition when behavior should vary or ownership is not a true is-a relationship. Inheritance is appropriate for a stable subtype relationship and safe substitutability under LSP.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---

## 40. What are SOLID principles?

1. **Question**: What are SOLID principles?
2. **Difficulty**: Intermediate
3. **Topic**: OOP
4. **What interviewer is testing**: Whether you can explain the principle accurately and choose it in a real design.
5. **Short interview answer (30–60 seconds)**: SOLID means Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, and Dependency Inversion. These principles reduce coupling and make changes safer, but they should not be applied mechanically.
6. **Detailed explanation**: SOLID means Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, and Dependency Inversion. These principles reduce coupling and make changes safer, but they should not be applied mechanically. In a project, use a small example and mention the main trade-off.
7. **How it works internally**: The compiler checks declarations and access rules; runtime dispatch applies where the concept uses virtual instance methods.
8. **Example**:

For “What are SOLID principles?”, the normal case follows the rule in the short answer; verify the relevant boundary case before using it in production.

9. **Code example**:

```java
final class OrderService { private final Payment payment; OrderService(Payment p){payment=p;} }
```

10. **Time & space complexity**: The principle has no standalone complexity; the concrete algorithm in the example determines time and auxiliary space.
11. **Real-world/project usage**: Use this principle to structure Spring services, domain objects, adapters, and testable components.
12. **Common mistakes**: Using inheritance only for code reuse, exposing mutable state, violating substitutability, or creating unnecessary abstractions.
13. **Advantages**: Better reuse, separation of concerns, extensibility, and testability when applied to a clear model.
14. **Limitations**: Extra types and indirection can increase complexity; poor abstraction can make simple code harder to change.
15. **Comparison with related concepts**: Compare inheritance, composition, abstract classes, and interfaces by ownership, substitutability, reuse, and coupling.
16. **Production considerations**: Keep contracts backward compatible, test polymorphic behavior, document invariants, and avoid reflection or proxy surprises.
17. **Possible follow-up questions**: What happens with nulls, default methods, access modifiers, or multiple implementations?
18. **Senior-level follow-up questions**: How would you evolve the abstraction without breaking clients, and how would you measure whether it reduced coupling?
19. **Scenario-based question**: A shared abstraction is causing regressions across services. Explain how you would isolate the contract, migrate implementations, and add compatibility tests.
20. **One-line revision note**: SOLID means Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, and Dependency Inversion. These principles reduce coupling and make changes safer, but they should not be applied mechanically.
21. **Image visuals (if required)**: A UML inheritance/composition diagram can help when relationships are central.

---
