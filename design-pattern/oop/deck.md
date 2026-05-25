---
id: 3c9b7d2f-4a8e-4f1d-9c3b-5e6f7a8b9c00
name: OOP Design Patterns Interview Prep
description: 20 essential design pattern questions for software engineering interviews, focusing on intent, applicability, and trade-offs.
author: Gemini
tags:
  - oop
  - design-patterns
  - software-engineering
---

## 1. What is the fundamental difference between the Strategy and State patterns?
Strategy is used to define a family of algorithms that the client can swap; State allows an object to change its behavior when its internal state changes.

## 2. How does the Decorator pattern differ from simple inheritance?
Decorator adds behavior to individual objects dynamically at runtime, whereas inheritance adds behavior to an entire class hierarchy at compile-time.

## 3. When should you use the Singleton pattern and what are the common concerns?
Use it for shared resources (like DB connections). Concerns include difficulty in unit testing, hidden dependencies, and issues with multi-threaded initialization.

## 4. Explain the "Dependency Inversion Principle" in the context of the Factory pattern.
The Factory pattern allows code to depend on abstractions (interfaces) rather than concrete implementations, adhering to the principle that high-level modules should not depend on low-level ones.

## 5. What is the intent of the Adapter pattern?
To allow two incompatible interfaces to work together by acting as a bridge (wrapper) between them.

## 6. How does the Proxy pattern differ from the Decorator pattern?
Decorator adds responsibilities to an object; Proxy controls access to an object (e.g., lazy loading, access control).

## 7. What is the "Observer" pattern and how is it used in reactive systems?
It defines a one-to-many dependency so that when one object changes state, all its dependents are notified. It is the backbone of event-driven/reactive programming.

## 8. Why would you prefer the Builder pattern over a constructor with many parameters?
It avoids "telescoping constructors," improves readability, and allows the construction process to be staged or conditional.

## 9. What is the Command pattern and why is it useful for undo/redo functionality?
It encapsulates a request as an object, allowing you to parameterize objects with operations and maintain a history of actions for undo/redo.

## 10. Explain the Template Method pattern.
It defines the skeleton of an algorithm in a base class, letting subclasses override specific steps without changing the overall structure.

## 11. When should you use the Facade pattern?
To provide a simplified, unified interface to a complex subsystem, reducing the coupling between the client and the subsystem.

## 12. What is the difference between the Abstract Factory and the Factory Method?
Factory Method uses inheritance to let subclasses decide which object to create; Abstract Factory uses object composition to create families of related objects.

## 13. How does the Composite pattern handle leaf nodes and container nodes uniformly?
By defining a common interface for both individual objects and compositions, allowing the client to treat them identically.

## 14. What is the Flyweight pattern and when is it applicable?
It minimizes memory usage by sharing as much data as possible with similar objects—useful when creating a massive number of objects with shared state.

## 15. How do you implement a "Chain of Responsibility" pattern?
Pass a request along a chain of handlers; each handler decides whether to process the request or pass it to the next handler in the chain.

## 16. What is the Memento pattern?
It allows an object to capture and externalize its internal state so that it can be restored to this state later, without violating encapsulation.

## 17. What is the intent of the Bridge pattern?
To decouple an abstraction from its implementation so that the two can vary independently.

## 18. Why is the Prototype pattern useful?
It allows you to create new objects by copying an existing instance (the prototype) rather than using the `new` keyword, which is useful for complex object creation.

## 19. What is the Visitor pattern and what is its main drawback?
It lets you add new operations to existing object structures without modifying the structures. The drawback is that it violates encapsulation and is hard to maintain when classes change.

## 20. How does the Mediator pattern promote decoupling?
It restricts direct communications between objects and forces them to collaborate only via a mediator object, reducing the "spaghetti" of object-to-object dependencies.
