# TDD/BDD Workshop

This workshop is designed to help you start or improve your [Test Driven Development](https://en.wikipedia.org/wiki/Test-driven_development) and [Behaviour Driven Development](https://en.wikipedia.org/wiki/Behavior-driven_development) skills.

## What is TDD

[Test Driven Development](https://en.wikipedia.org/wiki/Test-driven_development) or Test First Development is a process that consists of turning the requirements of the software application into specific test cases (acceptance criteria) and then implement the source code.

This process uses the **red/green/refactor** pattern and consists of the following steps:

1. Create Test
2. Run Tests (should fail - Red)
3. Write Code
4. Run Tests (should pass - Green)  
5. Refactor

Repeat  

## What is BDD

[Behaviour Driven Development](https://en.wikipedia.org/wiki/Behavior-driven_development) is a methodology that specifies acceptance criteria using a syntax that can be managed by business and by technology. The most well known implementation for this syntax is [Gherkin](https://github.com/cucumber/cucumber/wiki/Gherkin).

The Gherkin syntax has 3 main components that are represented by the following *keywords*:

* **Feature** - maps to a feature of the software. e.g.: Login

* **Scenario** - maps to a particular scenario of the usage of the feature.

* **Step** - a step of the scenario. A step starts with one of the following keywords:

    * **Given** - used for definition of context.
    * **And** or **When** - used for events.
    * **Then** or **But** - used for assertions.


## Quick start
To get started, go to the README of the desired language.
- [Java](./Java/README.md)