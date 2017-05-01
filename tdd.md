---
layout: page
title: Test-Driven Development
permalink: /tdd/
---

# Contents

- [Concept](#concept)
- [Documents](#documents)
- [Books](#books)
- [Videos](#videos)
- [Knowledge](/tdd/knowledge/)
- [Training](/tdd/training/)
- [Exercises](/tdd/exercises/)
- [Links](/tdd/links/)

# Concept

Test-Driven Development (TDD) is a technique for building software that guides software development by writing tests. TDD is a [software development process](https://en.m.wikipedia.org/wiki/Software_development_process) that relies on the repetition of a very short development cycle: requirements are turned into very specific [test cases](https://en.m.wikipedia.org/wiki/Test_case), then the software is improved to pass the new tests, only.

## The Three Steps of TDD

![Three Steps of TDD](/img/three_stepp_of_tdd.png)  

1. __RED__: Write a test for the next bit of functionality you want to add.
2. __GREEN__: Write the functional code until the test passes.
3. __REFACTOR__: Clean up both new and old codes to makt it well structured and remove duplications.

_Source: [martinfowler.com](http://martinfowler.com/bliki/TestDrivenDevelopment.html)_

## The Three Rules Of TDD

1. You are not allowed to write any production code unless it is to make a failing unit test pass.
2. You are not allowed to write any more of a unit test than is sufficient to fail; and compilation failures are failures.
3. You are not allowed to write any more production code than is sufficient to pass the one failing unit test.

You must begin by writing a unit test for the functionality that you intend to write.

But by rule 2, you can't write very much of that unit test. As soon as the unit test code fails to compile, or fails an assertion, you must stop and write production code.

But by rule 3 you can only write the production code that makes the test compile or pass, and no more.

_Source: [butunclebob.com](http://butunclebob.com/ArticleS.UncleBob.TheThreeRulesOfTdd)_

## TDD and ATDD

![TDD and ATDD](/img/atdd_and_tdd.png)

Test-driven development is related to, but different from [acceptance test–driven development](https://en.wikipedia.org/wiki/Acceptance_test%E2%80%93driven_development) (ATDD).

**TDD is primarily a developer’s tool to help create well-written unit of code** (function, class, or module) that correctly performs a set of operations. **ATDD is a communication tool between the customer, developer, and tester to ensure that the requirements are well-defined.**

TDD requires test automation. ATDD does not, although automation helps with regression testing. Tests used in TDD can often be derived from ATDD tests, since the code units implement some portion of a requirement. ATDD tests should be readable by the customer. TDD tests do not need to be.

_Source: [Wikipedia](https://en.wikipedia.org/wiki/Test-driven_development#TDD_and_ATDD)_

## TDD and BDD

![Given When Then](/img/given_when_then.jpg)  
_Source: [Abhay Kumar - LinkedIn](https://www.linkedin.com/pulse/behavior-driven-development-tools-java-developers-abhay-kumar)_

BDD ([behavior-driven development](https://en.wikipedia.org/wiki/Behavior-driven_development)) **combines practices from TDD and from ATDD. It includes the practice of writing tests first, but focuses on tests which describe behavior**, rather than tests which test a unit of implementation. Tools such as Mspec and Specflow provide a syntax which allow non-programmers to define the behaviors which developers can then translate into automated tests.

_Source: [Wikipedia](https://en.wikipedia.org/wiki/Test-driven_development#TDD_and_BDD)_

# Documents

## SAP

- [Agile Software Engineering, OPA5, UI5, Test Automation](https://s3-ap-southeast-1.amazonaws.com/pacroy/Agile+Software+Engineering%2C+OPA5%2C+UI5%2C+Automation.pptx)
- [Automated Testing](https://s3-ap-southeast-1.amazonaws.com/pacroy/Automated+Testing.pptx)
- [SAP Test Automation](https://s3-ap-southeast-1.amazonaws.com/pacroy/SAP+Test+Management.pdf)
- [ABAP Code Refacotring Techniques](https://s3-ap-southeast-1.amazonaws.com/pacroy/abap_code_refactoring_techniques.pdf)

## TOSCA

- [What's New in Tosca 9.3](https://s3-ap-southeast-1.amazonaws.com/pacroy/What%E2%80%99s+New+in+Tosca+9.3.pdf)
- [Conquer SAP Testing with Tosca Test Suites](https://s3-ap-southeast-1.amazonaws.com/pacroy/SAP+Tricentis+Tosca+-testing.pdf)

## Others

- [Key Test Design Techniques](https://s3-ap-southeast-1.amazonaws.com/pacroy/Key+Test+Design+Techniques.pdf)

# Books

## Recommended

- [Kent Beck. _Test-Driven Development by Example_.](https://www.amazon.com/Test-Driven-Development-Kent-Beck/dp/0321146530) - Java
- [Roy Osherove. _The Art of Unit Testing_.](https://www.amazon.com/Art-Unit-Testing-examples/dp/1617290890/) - C#
- [Robert C. Martin. _Clean Code: A Handbook of Agile Software Craftsmanship_.](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)
- [Michael Feathers. _Working Effectively with Legacy Code_.](https://www.amazon.com/Working-Effectively-Legacy-Michael-Feathers/dp/0131177052/) - Java, C++, C#
- [Eric Freeman et all. _Head First Design Patterns: A Brain-Friendly Guide_.](https://www.amazon.com/Head-First-Design-Patterns-Brain-Friendly/dp/0596007124) - Java
- [Andrew Hunt et all. _The Pragmatic Programmer: From Journeyman to Master_.](https://www.amazon.com/Pragmatic-Programmer-Journeyman-Master/dp/020161622X/)
- [James Wood et all. _ABAP Unit: Writing and Executing Unit Tests_.](https://www.sap-press.com/abap-unit-writing-and-executing-unit-tests_4298/) - ABAP
- [Paul Hardy. _ABAP to the Future_.](https://www.sap-press.com/abap-to-the-future_4161/) - ABAP

## Worth to Note

- [Joshua Kerievsky. _Refactoring to Patterns_.](https://www.amazon.com/Refactoring-Patterns-Joshua-Kerievsky/dp/0321213351)
- [Gerard Meszaros. _xUnit Test Patterns: Refactoring Test Code_.](https://www.amazon.com/xUnit-Test-Patterns-Refactoring-Code/dp/0131495054/)
- [Mark Seemann. _Dependency Injection in .NET_.](https://www.amazon.com/Dependency-Injection-NET-Mark-Seemann/dp/1935182501/)
- [Mark Ethan Trostler. _Testable JavaScript: Ensuring Reliable Code_.](https://www.amazon.com/Testable-JavaScript-Ensuring-Reliable-Code/dp/1449323391)
- [Martin Fowler. _Patterns of Enterprise Application Architecture_.](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/)

## More Books

- [Suggested Reading for Professional Scrum Developer](https://www.scrum.org/resources/suggested-reading-professional-scrum-developer)

# Videos

- [Gary Bernhardt. _Fast Test, Slow Test_.](https://youtu.be/RAxiiRPHS9k)
- [Jon Reid. _MCE 2014: Jon Reid - Test Driven Development for iOS (and anything)_.](MCE 2014: Jon Reid - Test Driven Development for iOS (and anything))
  - [Presentation Material](http://qualitycoding.org/files/ControllingDependencies.pdf)
- [Mattias Johanson. _The BEST way to do mocking - FunFunFunction #8_.](https://github.com/mpj/workroom-lights-killer)
  - [Gary Bernhardt's talk 'Boundaries'](https://www.destroyallsoftware.com/talks/boundaries)
  - [Codes in the video](https://github.com/mpj/workroom-lights-killer)
