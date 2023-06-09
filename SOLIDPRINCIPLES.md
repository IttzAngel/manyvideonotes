# SOLID: Single responsibility principle, Open closed principle, Liskov substitution principle, Interface segregation principle, Dependency inversion principle
- Pyramid of clean code: Base is SOLID, then design patterns, then TDD, then top is Continuous refactoring
- Code fragillity is the tendency of the software to break in many places every time it is changed
- Code rigidity is the tendency for software to be difficult to change, even in simple ways. every change causes a cascade of subsequent changes in dependent modules
- fast delivery is the easiest fix/change, fast, but poorly written code
- code quality takes more time, adds a bit of complexity, but code is maintainable
- cost of change should be lower, keep technical debt low and manageable
- no matter how good a team is, technical debt will build up
- if technical debt is left uncontrolled, it will kill the project
- the key is to keep the technical debt under control
- to control technical debt: write code, pay debt(refactor), write more code, pay debt(refactor)
- SOLID helps keep technical debt under control
- top benefits of SOLID code: easy to understand and reason about, changes are faster and have a minimal risk level, highly maintainable over long periods of time, and cost effective
- Other ways to keep architecture clean: constant refactoring, design patterns, and TDD(unit testing)
- every function, class, or module should have one and only one reason to change
- always identify the reasons to change, and simplify to be a single one
- use SRP because it makes code easier to understand, fix and maintain, classes are less coupled and more resilient to change, and it is a more testable design
# SRP: single responsibility principle
- symptoms of not using SRP: code is more difficult to read, decreased quality, general side effects, and high coupling
# Open Closed Principle is classes functions, and modules should be closed for modification, but open for extension
- modifying existing code is a risk
- use OCP to add new features more easily and with minimal cost, and works with SRP
- progressively apply OCP, start small, then add more changes, then do many changes/dynamic decision
- an API is a contract/agreement between different software components on how they should work together
- a public framework or API is under your control, but clients might use it in ways that you arent aware of
- best practices for changing API's: do not change existing public contracts: data classes and signatures, expose abstractions to yuor customerts and let them add new features on top of your framework, and if a breaking change is inevitable, give your clients time to adapt
- changing requirements are inevitable
- OCP also applies to packages
- inheritance and design patterns are effective ways to add features without modifying existing components
- making a flexible design adds more complexity
- OCP is all about making changes easy to do and avoid the struggle
# Liskov Substitution Principle
- if S is a subtype of T, then objects of type T in a program may be replaced with objects of type S without modifying the functionality of the program
- Any object of a type must be substitutable by objects of a derived typed without altering the correctness of that program
- relationships: is-A and is-subsitutable-by
- Square is a kind of rectangle, an ostrich is a bird
- Is the class rectangle fully substitutable by the class square?
- incorrect relationships between types cause unexpected bugs or side effects
- eliminate incorrect relations between objects, use tell dont ask principle to eliminate type checking and casting
- make sure that a derived type can substitute its base type completely, keep bases classes small and focused, and keep interfaces lean
- dont think relationships in terms of "is-A"
- empty methods, type checking and hardened preconditions are signs that you are violating the LSP
- LSP also applies for interfaces, not just for class inheritance
- most times you fix an incorrect type hierarchy by breaking it
- "if it looks like a duck, quacks like a duck, but needs batteries - you probably have the wrong abstraction"
# Interface Segregation Principle
- clients should not be forced to depend on methods that they do not use
- the interface word in the principle name does not strictly mean a java interface
- by keeping interfaces small, the classes that implement them have a higher chance to fully substitute the interface
- classes that implement small interfaces are more focused and tend to have a single purpose
- lean interfaces minimize dependencies on unused members and reduce code coupling
- code becomes more cohesive and focused
- it reinforces the use of SRP and LSP
- symptoms of interface pollution: interfaces with lots of methods, interfaces with low cohesion, client throws exception instead of implementing method, client provides empty implementation, and client forces implementation and becomes highly coupled
- fixing interface pollution: your own code - breaking interfaces is pretty easy and safe due to the possibility to implement as many interfaces as we want, external legacy doe - you cant control the interfaces in the external code, so you use design patterns like "adapter"
- dont confuse the word "interface" in the name with a java interface
- break large interfaces into many focused ones for code that you own -"use "adapter pattern" for external code
- pay attention to the symptoms of large interfaces and take action
- the ISP and linked with LSP and SRP
- many conflicts specific interfaces are better than one general purpose interface
# Dependency Inversion Principle
- dependency injection (DI)
- inversion of control (IoC)
- high level modules should not depend on low level modules; both should depend on abstractions
- abstractions should not depend on details, details should depend upon abstraction
- high level modules are modules written to solve real problems and use cases, they are more abstract and map to the business domain, and its what the software should do
- low level modules contain implementation details that are required to execute the business policies, they are considered the "plumbing" or "internals" of an application and its how the software should do various tasks
- examples of low level modules: logging, data access, network communication, and IO
- high level modules work together with low level modules
- abstraction is something that is not concrete, and something that you can not new up. in java applications we tend to model abstractions using interfaces and abstract classes
- dependency injection is a technique that allows the creation of dependent objects outside of a class and provides those objects to a class
- inversion of control is a design principle in which the control of object creation, configuration, and lifecycle is passed to a container or framework
- you dont "new" up objects, they are created by someone else (IoC containers)
- control of object creation is inverted, so its not the programmer, but someone else who controls the objects
- it makes sense to use it for some objects in an application (services, data access, controllers) and for others it doesnt (entities, value objects)
- IoC container benefits: makes it easy to switch between different implementations at runtime, increased program modularity, manages the lifecycle of objects and their configuration
- spring bean is objects used by your application and that are managed by the spring IoC container. they are created with the configuration that you supply to the container
- DIP, DI, IoC: dependency dependency inversion principle, dependency injection, inversion of control & containers
- classes should depend on abstractions not implementation details, DIP, DI, and IoC work hand in hand to eliminate coupling and make applications less brittle, testability can greatly be improved by using the DIP and the DI technique, and take advantage of the powerful capabilities of the spring IoC container
# tehcnical debt is the silent killer of software projects, coupling is the main reason of technical debt, SOLID is to tackle coupling and promote designs that can evolve and grow
# the SOLID principles are the foundation of clean system design
