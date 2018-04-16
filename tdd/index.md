---
layout: default
---

# Sections
- [Exercises](exercises)
- [Knowledge](knowledge)
- [Training](training)

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

![Three Step Of Tdd](/uploads/tdd/three-step-of-tdd.png "Three Step Of Tdd")
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

![Atdd And Tdd](/uploads/tdd/atdd-and-tdd.png "Atdd And Tdd")

Test-driven development is related to, but different from [acceptance test–driven development](https://en.wikipedia.org/wiki/Acceptance_test%E2%80%93driven_development) (ATDD).

**TDD is primarily a developer’s tool to help create well-written unit of code** (function, class, or module) that correctly performs a set of operations. **ATDD is a communication tool between the customer, developer, and tester to ensure that the requirements are well-defined.**

TDD requires test automation. ATDD does not, although automation helps with regression testing. Tests used in TDD can often be derived from ATDD tests, since the code units implement some portion of a requirement. ATDD tests should be readable by the customer. TDD tests do not need to be.

Source: [Wikipedia](https://en.wikipedia.org/wiki/Test-driven_development#TDD_and_ATDD)

## TDD and BDD

![Given When Then](/uploads/tdd/given-when-then.jpg "Given When Then")
    Source: [Abhay Kumar - LinkedIn](https://www.linkedin.com/pulse/behavior-driven-development-tools-java-developers-abhay-kumar)

BDD ([behavior-driven development](https://en.wikipedia.org/wiki/Behavior-driven_development)) **combines practices from TDD and from ATDD. It includes the practice of writing tests first, but focuses on tests which describe behavior**, rather than tests which test a unit of implementation. Tools such as Mspec and Specflow provide a syntax which allow non-programmers to define the behaviors which developers can then translate into automated tests.

Source: [Wikipedia](https://en.wikipedia.org/wiki/Test-driven_development#TDD_and_BDD)

# Useful Links

## Recommended Read

- [Test Driven Development: 15 years later](https://goo.gl/VfkjmV) by Petr Jasek, Department of Computer Science, Aalborg University
- [TDD from book 'Scrum and XP from the Trenches'](http://wiki.chairat.me/scrum/#wiki-toc-test-driven-development-tdd) by Henrik Kniberg
- [Key Test Design Techniques](https://s3-ap-southeast-1.amazonaws.com/pacroy/Key+Test+Design+Techniques.pdf) by Lee Copeland, Software Quality Engineering - *June 5, 2014*

## Videos
- [Fast Test, Slow Test](https://youtu.be/RAxiiRPHS9k) by Gary Bernhardt - *March 11, 2012*
- [MCE 2014: Jon Reid - Test Driven Development for iOS (and anything)](https://youtu.be/Jzlz3Bx-NzM) by Jon Reid - *February 14, 2014*
    - [Presentation Material](http://qualitycoding.org/files/ControllingDependencies.pdf)
- [The BEST way to do mocking - FunFunFunction #8](https://youtu.be/fgqh-OZjpYY) by Mattias Johanson - *November 19, 2015*
    - [Gary Bernhardt's talk 'Boundaries'](https://www.destroyallsoftware.com/talks/boundaries)
    - [Codes in the video](https://github.com/mpj/workroom-lights-killer)

# Books

- [Test-Driven Development by Example](https://www.amazon.com/Test-Driven-Development-Kent-Beck/dp/0321146530) : _Java_
- [The Art of Unit Testing](https://www.amazon.com/Art-Unit-Testing-examples/dp/1617290890/) : _C#_
- [Clean Code: A Handbook of Agile Software Craftsmanship](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)
- [Working Effectively with Legacy Code](https://www.amazon.com/Working-Effectively-Legacy-Michael-Feathers/dp/0131177052/) : _Java, C++, C#_
- [Head First Design Patterns: A Brain-Friendly Guide](https://www.amazon.com/Head-First-Design-Patterns-Brain-Friendly/dp/0596007124) : _Java_
- [The Pragmatic Programmer: From Journeyman to Master](https://www.amazon.com/Pragmatic-Programmer-Journeyman-Master/dp/020161622X/)
- [Refactoring to Patterns](https://www.amazon.com/Refactoring-Patterns-Joshua-Kerievsky/dp/0321213351)
- [xUnit Test Patterns: Refactoring Test Code](https://www.amazon.com/xUnit-Test-Patterns-Refactoring-Code/dp/0131495054/)
- [Dependency Injection in .NET](https://www.amazon.com/Dependency-Injection-NET-Mark-Seemann/dp/1935182501/)
- [Testable JavaScript: Ensuring Reliable Code](https://www.amazon.com/Testable-JavaScript-Ensuring-Reliable-Code/dp/1449323391)
- [Patterns of Enterprise Application Architecture](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/)

See more books at [Suggested Reading for Professional Scrum Developer](https://www.scrum.org/resources/suggested-reading-professional-scrum-developer)

# Gurus

- [**Robert C. Martin (Uncle Bob)**](http://twitter.com/unclebobmartin) 
    - [CleanCoder.com](http://blog.cleancoder.com/)
- [**Martin Fowler**](http://www.martinfowler.com/aboutMe.html) 
    - [MartinFowler.com](http://www.martinfowler.com/)
- [**Roy Oserove**](http://osherove.com/about/) 
    - [Oserove.com](http://osherove.com/)
    - [ArtOfUnitTesting.com](http://artofunittesting.com/) - Ruby, Java, .NET
    - [Osherove Online Training](http://courses.osherove.com/)
    - [Unit Testing and TDD 101](http://courses.osherove.com/courses/the-art-of-unit-testing-tdd-master-class-in-net/lectures/54779)
- [**Micheal C. Feather**](https://michaelfeathers.silvrback.com/bio)
    - [Blogs](https://michaelfeathers.silvrback.com/)
- [**Eric Elliott**](https://twitter.com/_ericelliott)
    - Books: [Programming JavaScript Applications](https://ericelliottjs.com/product/programming-javascript-applications-paper-ebook-bundle/)
    - [Stories on Medium](https://medium.com/@_ericelliott)
    - [Learn JavaScript with Eric Elliott](http://ericelliottjs.com/product/lifetime-access-pass/)
- [**Jon Reid**](http://twitter.com/qcoding)
    - [QualityCoding.org](http://qualitycoding.org/) - iOS
- [**Harry J.W. Percival**](obeythetestinggoat@gmail.com)
    - [ObeyTheTestingGoat.com](http://www.obeythetestinggoat.com/) - Python
- [**Somkiat Puisungnoen**](https://www.linkedin.com/in/somkiat)
    - [Blogs in Thai](http://www.somkiat.cc/tag/tdd/)
    - [Facebook Page](https://www.facebook.com/somkiat.cc)