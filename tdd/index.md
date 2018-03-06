---
layout: page
title: Test-Driven Development
description: Here you can find information and resources about Test-Driven Development.
---

# Contents

- [Useful Links](https://trello.com/b/7SwXtDRQ/test-driven-development)
- [Concept](#concept)
- [Documents](#documents)
- [Books](#books)
- [Gurus](#gurus)
- [Knowledge](knowledge.html)
- [Training](training.html)
- [Exercises](exercises.html)

# Concept

## Definitions

> Test-driven Development is a programming practice that instructs developers to write new code only if an automated test has failed, and to eliminate duplication. The goal of TDD is clean code that works.

__*Massol & Husted: JUnit in Action*

> Test Driven Development is the craft of producing automated tests for production code, and using that process to drive design and programming
> 
> For every bit of functionality, you first develop a test that specifies and validates what the code will do.
> 
> You then produce exactly as much code as necessary to pass the test. Then you refactor (simplify and clarify) both production code and test code

__*Agile Aliance*

Source: Brian Nielsen, Arne Skou. *Test Driven Development*. Retrieved May 30, 2017 from https://goo.gl/lfyX48

## The Steps of TDD

![Three Steps of TDD](img/three_step_of_tdd.png)  
Source: Matt Chernosky. (2016, March 14). *How to Write Better Unit Tests For Embedded Software With TDD*. Retrieved from https://goo.gl/4Y6OtZ

Test-driven development (TDD) is a software development process that relies on the repetition of a very short development cycle. It can be succinctly described by the following set of rules:

1. write a "single" unit test describing an aspect of the program
2. run the test, which should fail because the program lacks that feature
3. write "just enough" code, the simplest possible, to make the test pass
4. run the test again to ensure all the tests pass
5. "refactor" the code until it conforms to the [simplicity criteria](https://www.agilealliance.org/glossary/rules-of-simplicity/)
6. repeat, "accumulating" unit tests over time


Adapted from Agile Alliance. *TDD Glossary*. Retreived May 30, 2017 from https://goo.gl/2EcEZz

## The Three Rules Of TDD

1. You are not allowed to write any production code unless it is to make a failing unit test pass.
2. You are not allowed to write any more of a unit test than is sufficient to fail; and compilation failures are failures.
3. You are not allowed to write any more production code than is sufficient to pass the one failing unit test.

You must begin by writing a unit test for the functionality that you intend to write.

But by rule 2, you can't write very much of that unit test. As soon as the unit test code fails to compile, or fails an assertion, you must stop and write production code.

But by rule 3 you can only write the production code that makes the test compile or pass, and no more.

Source: Robert C. Martin (Uncle Bob). *The Three Rules of TDD*. Retrived May 30, 2017 from https://goo.gl/6Y2ir5

## TDD and ATDD

![TDD and ATDD](img/atdd_and_tdd.png)

Test-driven development is related to, but different from [acceptance test–driven development](https://en.wikipedia.org/wiki/Acceptance_test%E2%80%93driven_development) (ATDD).

**TDD is primarily a developer’s tool to help create well-written unit of code** (function, class, or module) that correctly performs a set of operations. **ATDD is a communication tool between the customer, developer, and tester to ensure that the requirements are well-defined.**

TDD requires test automation. ATDD does not, although automation helps with regression testing. Tests used in TDD can often be derived from ATDD tests, since the code units implement some portion of a requirement. ATDD tests should be readable by the customer. TDD tests do not need to be.

Source: [Wikipedia](https://en.wikipedia.org/wiki/Test-driven_development#TDD_and_ATDD)

## TDD and BDD

![Given When Then](img/given_when_then.jpg)  
Source: [Abhay Kumar - LinkedIn](https://www.linkedin.com/pulse/behavior-driven-development-tools-java-developers-abhay-kumar)

BDD ([behavior-driven development](https://en.wikipedia.org/wiki/Behavior-driven_development)) **combines practices from TDD and from ATDD. It includes the practice of writing tests first, but focuses on tests which describe behavior**, rather than tests which test a unit of implementation. Tools such as Mspec and Specflow provide a syntax which allow non-programmers to define the behaviors which developers can then translate into automated tests.

Source: [Wikipedia](https://en.wikipedia.org/wiki/Test-driven_development#TDD_and_BDD)

# Documents

## Recommended Read

- [Test Driven Development: 15 years later](https://goo.gl/VfkjmV) by Petr Jasek, Department of Computer Science, Aalborg University
- [TDD from book 'Scrum and XP from the Trenches'](http://wiki.chairat.me/scrum/#test-driven-development-tdd) by Henrik Kniberg
- [Back to the Future 2018 – Reloaded](https://blogs.sap.com/2018/01/27/back-to-the-future-2018-reloaded/) by Paul Hardy
  - [Introduction – The Wilderness Years](https://blogs.sap.com/2018/01/27/back-to-the-future-2018-reloaded/)
  - [Part 1 – Inheritance – The Sins of the Fathers](https://blogs.sap.com/2018/01/27/back-to-the-future-2018-reloaded/)
  - [Part 2 – Unit Testing – Poltergeist: The Legacy](https://blogs.sap.com/2018/02/03/back-to-the-future-reloaded-part-2/#)
  - [Back to the Future Reloaded – Part 3 – Rewriting Programs](https://blogs.sap.com/2018/02/15/back-to-the-future-reloaded-part-3-rewriting-programs/)

## SAP

- [Agile Software Engineering, OPA5, UI5, Test Automation](https://s3-ap-southeast-1.amazonaws.com/pacroy/Agile+Software+Engineering%2C+OPA5%2C+UI5%2C+Automation.pptx) by SAP - *June 18, 2016*
- [Automated Testing](https://s3-ap-southeast-1.amazonaws.com/pacroy/Automated+Testing.pptx) by Sarah Lottman, SAP - *Septenber 2016*
- [SAP Test Automation](https://s3-ap-southeast-1.amazonaws.com/pacroy/SAP+Test+Management.pdf) by SAP, *July 2012*
- [ABAP Code Refacotring Techniques](https://s3-ap-southeast-1.amazonaws.com/pacroy/abap_code_refactoring_techniques.pdf) by Sukru Ilkel Birakoglu, SAP LABS France - *July 6, 2009*
, 
## TOSCA

- [What's New in Tosca 9.3](https://s3-ap-southeast-1.amazonaws.com/pacroy/What%E2%80%99s+New+in+Tosca+9.3.pdf) by Dr. Gerd Weishaar, Tricentis - *2016*
- [Conquer SAP Testing with Tosca Test Suites](https://s3-ap-southeast-1.amazonaws.com/pacroy/SAP+Tricentis+Tosca+-testing.pdf) by Wolfgang Platz, Tricentis - *2015*
- [Automated Testing in SAP](https://vimeo.com/159330942) (Video) by Tricentis - *2016*
- [Tosca-SAP Solution Manager Integration](https://support.tricentis.com/community/manuals_detail.do?lang=en&version=10.0.0&url=sap_solutionmanager/concept.htm) (Manual) by Tricentis

## Others

- [Key Test Design Techniques](https://s3-ap-southeast-1.amazonaws.com/pacroy/Key+Test+Design+Techniques.pdf) by Lee Copeland, Software Quality Engineering - *June 5, 2014*

## Videos
- [Fast Test, Slow Test](https://youtu.be/RAxiiRPHS9k) by Gary Bernhardt - *March 11, 2012*
- [MCE 2014: Jon Reid - Test Driven Development for iOS (and anything)](https://youtu.be/Jzlz3Bx-NzM) by Jon Reid - *February 14, 2014*
  - [Presentation Material](http://qualitycoding.org/files/ControllingDependencies.pdf)
- [The BEST way to do mocking - FunFunFunction #8](https://youtu.be/fgqh-OZjpYY) by Mattias Johanson - *November 19, 2015*
  - [Gary Bernhardt's talk 'Boundaries'](https://www.destroyallsoftware.com/talks/boundaries)
  - [Codes in the video](https://github.com/mpj/workroom-lights-killer)

# Books

| &nbsp; | &nbsp; | &nbsp; |
|:---:|:---:|:---:|
| ![](img/tdd_by_example.jpg)<br />[Test-Driven Development by Example](https://www.amazon.com/Test-Driven-Development-Kent-Beck/dp/0321146530) :<br />_Java_ | ![](img/art_of_unit_testing.jpg)<br />[The Art of Unit Testing](https://www.amazon.com/Art-Unit-Testing-examples/dp/1617290890/) :<br />_C#_ | ![](img/clean_code.jpg)<br />[Clean Code: A Handbook of Agile Software Craftsmanship](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882) |
| ![](img/working_effectively_with_legacy_code.jpg)<br />[Working Effectively with Legacy Code](https://www.amazon.com/Working-Effectively-Legacy-Michael-Feathers/dp/0131177052/) :<br />_Java, C++, C#_ | ![](img/head_first_design_patterns.jpg)<br />[Head First Design Patterns: A Brain-Friendly Guide](https://www.amazon.com/Head-First-Design-Patterns-Brain-Friendly/dp/0596007124) :<br />_Java_ | ![](img/pragmatic_programmer.jpg)<br />[The Pragmatic Programmer: From Journeyman to Master](https://www.amazon.com/Pragmatic-Programmer-Journeyman-Master/dp/020161622X/) |
|![](img/abap_unit.jpg)<br />[ABAP Unit: Writing and Executing Unit Tests](https://www.sap-press.com/abap-unit-writing-and-executing-unit-tests_4298/) :<br />_ABAP_ | ![](img/abap_to_the_future.jpg)<br />[ABAP to the Future](https://www.sap-press.com/abap-to-the-future_4161/) :<br />_ABAP_ | ![](img/design_patterns_in_abap_objects.jpg)<br />[Design Patterns in ABAP Objects](https://www.sap-press.com/design-patterns-in-abap-objects_4277/) :<br />_ABAP_ |
|![](img/refactoring_to_patterns.jpg)<br />[Refactoring to Patterns](https://www.amazon.com/Refactoring-Patterns-Joshua-Kerievsky/dp/0321213351) | ![](img/xunit_test_patterns.jpg)<br />[xUnit Test Patterns: Refactoring Test Code](https://www.amazon.com/xUnit-Test-Patterns-Refactoring-Code/dp/0131495054/) | ![](img/dependency_injection_dotnet.jpg)<br />[Dependency Injection in .NET](https://www.amazon.com/Dependency-Injection-NET-Mark-Seemann/dp/1935182501/) |
|![](img/testable_javascript.jpg)<br />[Testable JavaScript: Ensuring Reliable Code](https://www.amazon.com/Testable-JavaScript-Ensuring-Reliable-Code/dp/1449323391) |  ![](img/pattern_of_enterprise_application_architecture.jpg)<br />[Patterns of Enterprise Application Architecture](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/) |  |

See more books at [Suggested Reading for Professional Scrum Developer](https://www.scrum.org/resources/suggested-reading-professional-scrum-developer)

# Gurus

|  |  |  |
|:---:|:---:|:---:|
| ![](img/robert_martin.jpg)<br />[**Robert C. Martin (Uncle Bob)**](http://twitter.com/unclebobmartin) <br /> [CleanCoder.com](http://blog.cleancoder.com/) | ![](img/martin_fowler.jpg)<br />[**Martin Fowler**](http://www.martinfowler.com/aboutMe.html) <br /> [MartinFowler.com](http://www.martinfowler.com/) | ![](img/roy_osherove.jpg)<br />[**Roy Oserove**](http://osherove.com/about/) <br /> [Oserove.com](http://osherove.com/)<br />[ArtOfUnitTesting.com](http://artofunittesting.com/) - Ruby, Java, .NET<br />[Osherove Online Training](http://courses.osherove.com/)<br />[Unit Testing and TDD 101](http://courses.osherove.com/courses/the-art-of-unit-testing-tdd-master-class-in-net/lectures/54779) |
| ![](img/micheal_feathers.jpg)<br />[**Micheal C. Feather**](https://michaelfeathers.silvrback.com/bio) <br /> [Blogs](https://michaelfeathers.silvrback.com/) | ![](img/eric_elliott.jpg)<br />[**Eric Elliott**](https://twitter.com/_ericelliott) <br /> Book: [Programming JavaScript Applications](https://ericelliottjs.com/product/programming-javascript-applications-paper-ebook-bundle/)<br />[Stories on Medium](https://medium.com/@_ericelliott)<br />[Learn JavaScript with Eric Elliott](http://ericelliottjs.com/product/lifetime-access-pass/) | ![](img/jon_reid.jpg)<br />[**Jon Reid**](http://twitter.com/qcoding) <br /> [QualityCoding.org](http://qualitycoding.org/) - iOS |
| ![](img/harry_percival.jpg)<br />[**Harry J.W. Percival**](obeythetestinggoat@gmail.com) <br /> [ObeyTheTestingGoat.com](http://www.obeythetestinggoat.com/) - Python | ![](img/somkiat_puisungnoen.jpg)<br />[**Somkiat Puisungnoen**](https://www.linkedin.com/in/somkiat) <br /> [Blogs in Thai](http://www.somkiat.cc/tag/tdd/)<br />[Facebook Page](https://www.facebook.com/somkiat.cc) |  |
