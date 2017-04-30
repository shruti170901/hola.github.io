---
layout: page
title: Test-Driven Development
permalink: /tdd/
---

# Contents
- [Knowledge](/tdd/knowledge/)
- [Training](/tdd/training/)
- [Exercises](/tdd/exercises/)
- [Books](/tdd/books/)
- [Documents](/tdd/documents/)
- [Videos](/tdd/videos/)
- [Links](/tdd/links)

# Concept

Test-Driven Development (TDD) is a technique for building software that guides software development by writing tests. TDD is a [software development process](https://en.m.wikipedia.org/wiki/Software_development_process) that relies on the repetition of a very short development cycle: requirements are turned into very specific [test cases](https://en.m.wikipedia.org/wiki/Test_case), then the software is improved to pass the new tests, only.

# The Three Steps of TDD

![Three Steps of TDD](/img/three_stepp_of_tdd.png)  

1. __RED__: Write a test for the next bit of functionality you want to add.
2. __GREEN__: Write the functional code until the test passes.
3. __REFACTOR__: Clean up both new and old codes to makt it well structured and remove duplications.

_Source: [martinfowler.com](http://martinfowler.com/bliki/TestDrivenDevelopment.html)_

# The Three Rules Of TDD

1. You are not allowed to write any production code unless it is to make a failing unit test pass.
2. You are not allowed to write any more of a unit test than is sufficient to fail; and compilation failures are failures.
3. You are not allowed to write any more production code than is sufficient to pass the one failing unit test.

You must begin by writing a unit test for the functionality that you intend to write.

But by rule 2, you can't write very much of that unit test. As soon as the unit test code fails to compile, or fails an assertion, you must stop and write production code.

But by rule 3 you can only write the production code that makes the test compile or pass, and no more.

_Source: [butunclebob.com](http://butunclebob.com/ArticleS.UncleBob.TheThreeRulesOfTdd)_

# TDD and ATDD

![TDD and ATDD](/img/unknown.png)

Test-driven development is related to, but different from [acceptance test–driven development](https://en.wikipedia.org/wiki/Acceptance_test%E2%80%93driven_development) (ATDD).

**TDD is primarily a developer’s tool to help create well-written unit of code** (function, class, or module) that correctly performs a set of operations. **ATDD is a communication tool between the customer, developer, and tester to ensure that the requirements are well-defined.**

TDD requires test automation. ATDD does not, although automation helps with regression testing. Tests used in TDD can often be derived from ATDD tests, since the code units implement some portion of a requirement. ATDD tests should be readable by the customer. TDD tests do not need to be.

_Source: [Wikipedia](https://en.wikipedia.org/wiki/Test-driven_development#TDD_and_ATDD)_

# TDD and BDD

![Given When Then](/img/given_when_then.jpg)  
_Source: [Abhay Kumar - LinkedIn](https://www.linkedin.com/pulse/behavior-driven-development-tools-java-developers-abhay-kumar)_

BDD ([behavior-driven development](https://en.wikipedia.org/wiki/Behavior-driven_development)) **combines practices from TDD and from ATDD. It includes the practice of writing tests first, but focuses on tests which describe behavior**, rather than tests which test a unit of implementation. Tools such as Mspec and Specflow provide a syntax which allow non-programmers to define the behaviors which developers can then translate into automated tests.

_Source: [Wikipedia](https://en.wikipedia.org/wiki/Test-driven_development#TDD_and_BDD)_