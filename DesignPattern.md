# Design Pattern
Solution to the problem that occurs over and over again in our environment.

* `Creational Patterns`: These deal with object construction and referencing.

* `Structural Patterns`: These deal with the relationships between objects and how they interact with each other to form larger complex objects.

* `Behavioral Patterns`: These deal with the communication between objects, especially in terms of responsibility and algorithms.

>23 Gang of Four design

## Common Design Principles

* Keep It Simple Stupid (KISS )
* Don’t Repeat Yourself (DRY)
* Tell, Don’t Ask
* You Ain’t Gonna Need It (YAGNI ) `TDD`
* Separation of Concerns (SoC)

## The S.O.L.I.D. Design Principles
### Single Responsibility Principle (SR P)
The principle of SRP is closely aligned with SoC. It states that every object should only have one
reason to change and a single focus of responsibility. By adhering to this principle, you avoid the
problem of monolithic class design that is the software equivalent of a Swiss army knife. By having
concise objects, you again increase the readability and maintenance of a system.
### Open-Closed Principle (OCP)
The OCP states that classes should be open for extension and closed for modification, in that you
should be able to add new features and extend a class without changing its internal behavior. The
principle strives to avoid breaking the existing class and other classes that depend on it, which
would create a ripple effect of bugs and errors throughout your application.
### Liskov Substitution Principle (LS P)
The LSP dictates that you should be able to use any derived class in place of a parent class and have it
behave in the same manner without modification. This principle is in line with OCP in that it ensures
that a derived class does not affect the behavior of a parent class, or, put another way, derived classes
must be substitutable for their base classes.
### Interface Segregation Principle (IS P)
The ISP is all about splitting the methods of a contract into groups of responsibility and assigning
interfaces to these groups to prevent a client from needing to implement one large interface and a
host of methods that they do not use. The purpose behind this is so that classes wanting to use the
same interfaces only need to implement a specific set of methods as opposed to a monolithic interface
of methods.
### Dependency Inversion Principle (DIP)
The DIP is all about isolating your classes from concrete implementations and having them depend on
abstract classes or interfaces. It promotes the mantra of coding to an interface rather than an implementation,
which increases flexibility within a system by ensuring you are not tightly coupled to one
implementation.

## Layered Architechture
![Clean Architecture](/images/LayeredArchitechture.png)

### Sequence Flow of Layered System
![imagess](/images/SequenceFlowProduct.png)

## Fowler’s Patterns of Enterprise Application Architecture
* Transaction Script
* Active Record
* Anemic Model
* Domain Model

## DDD (Domain Driven Design)

### Ubiquitious Language
Act as a common vocabulary that is used by
developers, domain experts, and anyone else involved in a project to describe the domain.

### Entities
Encompass the data and behavior of the real entity in an abstract manner. Any logic pertaining to an entity should be contained within it.

### Value Objects
Value objects have no identity; they are of value because of their attributes only. Value objects generally don’t live on their own; they are typically, but not always, attributes of an entity.

### Aggregates and Aggregate Roots

>An `aggregate` is simply “a cluster of associated objects that are treated as a unit for the purpose of data
changes.”

The notion of an aggregation `groups logical entities and value objects`. From the DDD definition, an aggregate is simply “a cluster of associated objects that are treated as a unit for the purpose of data changes.” The aggregate root is an entity, which is the only member of the aggregate that any object outside the aggregate is allowed to hold a reference to. The idea of an aggregate exists in DDD to
ensure data integrity within the domain model. An aggregate root is a special entity that acts as the logical way into the aggregate. For example, if you take an order in the context of an e-commerce shop, you can regard it as the aggregate root, because you only want to be able to edit an order line or apply a voucher by going through the root of the aggregate—that is, the order entity.

### Domain Services
Methods that don’t really fit on a single entity or `require access to the repository` are contained within domain services. The domain service layer can also contain domain logic of its own and is as much part of the domain model as
entities and value objects.
### Application Services
The Application service is a thin layer that `sits above the domain model` and coordinates the application activity. It does not contain business logic and does not hold the state of any entities; however, it can `store the state of a business workflow transaction`. You use an Application service to provide an API into the domain model using the `Request-Reply messaging` pattern.
### Repository
The Repository pattern `acts as an in-memory collection` or repository for business entities, completely abstracting away the underlying data infrastructure. This pattern allows you to keep your domain model free of any infrastructure concerns, making it `POCO` (*plain old common runtime object*) and `PI` (*persistent ignorance*).
Layering
Layering is an important concept in DDD because it helps to enforce the separation of concerns.
Figure 4-7 shows a graphical representation of the layers and concepts that make up DDD; however,
I should stress that DDD is much more about your mindset when developing complex business applications
than how you set up your solution.




















## Refrence book
>Test Driven Development: By Example by Kent Beck

>The Art of Unit Testing: With Examples in .NET by Roy Osherove

>Professional Enterprise .NET by Jon Arking and Scott Millett

>Domain-Driven Design: Tackling Complexity in the Heart of Software by Eric Evans

>Applying Domain-Driven Design and Patterns: With Examples in C# and .NET by Jimmy Nilsson

>.NET Domain-Driven Design with C#: Problem - Design - Solution by Tim 

