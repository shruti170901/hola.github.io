---
layout: page
title: TDD Knowledge
---

![TDD Knowledge Map](/img/tdd_knowledge.jpg)

# Fundamental Knowledge

## Object-Oriented Programming

- Encapsulation
- Composition, inheritance, and delegation
- Polymorphism
- Objects and classes
- Open recursion

_Source: [Wikipedia](https://en.wikipedia.org/wiki/Object-oriented_programming)_

## Code Refactoring

- Target
  - Production Code
  - Test Code
  - Between Production and Test Code
- Techniques
  - More [Abstraction](https://en.m.wikipedia.org/wiki/Abstraction_(software_engineering))
    - [Field Encapsulation](https://en.m.wikipedia.org/wiki/Field_encapsulation)
    - [Type Generialization](https://en.m.wikipedia.org/wiki/Type_generalization)
    - Replace Conditional with [Polymorphism](https://en.m.wikipedia.org/wiki/Polymorphism_(computer_science))
  - Breaking Code Apart
    - [Extract Class](https://en.m.wikipedia.org/wiki/Extract_Class)
    - Extract Method
  - Improving Names and Location
    - Move Methos or Move Field
    - [Rename Method](https://en.m.wikipedia.org/wiki/Rename_Method) or Rename Field
    - [Pull Up](https://en.m.wikipedia.org/wiki/Pull_Up_refactoring), move to a [superclass](https://en.m.wikipedia.org/wiki/Superclass_(computer_science))
    - [Push Down](https://en.m.wikipedia.org/wiki/Push_Down), move to a [subclass](https://en.m.wikipedia.org/wiki/Subclass_(computer_science))

_Source: [Wikipedia](https://en.wikipedia.org/wiki/Code_refactoring)_

## Design Pattern

- [Creational Pattern ](https://en.m.wikipedia.org/wiki/Creational_pattern)
  - [Factory Method Pattern](https://en.m.wikipedia.org/wiki/Factory_method_pattern)
  - [Singleton Pattern](https://en.m.wikipedia.org/wiki/Singleton_pattern)
- [Structural Pattern](https://en.m.wikipedia.org/wiki/Structural_pattern)
  - [Adapter Pattern](https://en.m.wikipedia.org/wiki/Adapter_pattern)
  - [Decorator Pattern](https://en.m.wikipedia.org/wiki/Decorator_pattern)
  - [Facade Pattern](https://en.m.wikipedia.org/wiki/Facade_pattern)
- [Behavior Pattern](https://en.m.wikipedia.org/wiki/Behavioral_pattern)
  - [Observer Pattern](https://en.m.wikipedia.org/wiki/Observer_pattern)
  - [Strategy Pattern](https://en.m.wikipedia.org/wiki/Strategy_pattern)
- [Concurrency Pattern](https://en.m.wikipedia.org/wiki/Concurrency_pattern)

_Source: [Wikipedia](https://en.wikipedia.org/wiki/Software_design_pattern)_

# Essential Knowledge

## Writing Unit Test

- [F.I.R.S.T Principles](https://en.m.wikipedia.org/wiki/Concurrency_pattern)
  - Fast
  - Independent
  - Repeatable
  - Self-Validating
  - Thorough and Timely
- [Testing Frameworks](https://en.wikipedia.org/wiki/List_of_unit_testing_frameworks)
- [3A's Pattern](http://xp123.com/articles/3a-arrange-act-assert/)
  - Arrange
  - Act
  - Assert
  
## Design Principles

- [KISS](https://en.m.wikipedia.org/wiki/KISS_principle): Keep it simple, stupid
- [DRY](https://en.m.wikipedia.org/wiki/Don't_repeat_yourself): Don't repeat yourself
- [YAGNI](https://en.wikipedia.org/wiki/You_aren't_gonna_need_it): You aren't gonna need it
- [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)) ([Motivational Posters](https://blogs.msdn.microsoft.com/cdndevs/2009/07/15/the-solid-principles-explained-with-motivational-posters/))
  - [Single Responsibility Principle (SRP)](https://en.m.wikipedia.org/wiki/Single_responsibility_principle)
  - [Open Closed Principle (OCP)](https://en.m.wikipedia.org/wiki/Open/closed_principle)
  - [Liskov Substitution Principle (LSP)](https://en.m.wikipedia.org/wiki/Liskov_substitution_principle)
  - [Interface Segregation Principle (ISP)](https://en.m.wikipedia.org/wiki/Interface_segregation_principle)
  - [Dependency Inversion Principle (DIP)](https://en.m.wikipedia.org/wiki/Dependency_inversion_principle)
    - [Inversion of Control (IoC)](https://en.wikipedia.org/wiki/Inversion_of_control)
      - [Dependency Injection (DI)](https://en.m.wikipedia.org/wiki/Dependency_injection)
        - Constructor injection
        - Parameter injection
        - Setter injection
        - Interface injection
  
## Test Double

- Types
  - Dummy
  - [Stub](https://en.m.wikipedia.org/wiki/Test_stubs)
  - [Mock](https://en.m.wikipedia.org/wiki/Mock_object)
  - Spy
  - [Fake](https://en.m.wikipedia.org/wiki/Fake_object)
- Frameworks
  - SAP ABAP
    - [ABAP Test Double Framework (ATDF)](https://blogs.sap.com/?p=361154)
    - [ABAP CDS Test Double Framework](https://blogs.sap.com/2016/10/19/introduction-cds-test-double-framework-write-unit-tests-abap-cds-entities/)
  - Java
    - [Stubby4j](https://github.com/azagniotov/stubby4j)
    - [dbUnit](http://dbunit.sourceforge.net/)
    - [WireMock](http://wiremock.org/)