## Quick start

Prerequisites

* You have an IDE or a text editor (e.g.: [IntelliJ IDEA](https://www.jetbrains.com/idea/download))
* You have [Maven](https://maven.apache.org/) installed

## Testing Tools/Frameworks

We will be using a few tools/frameworks to facilitate our job.

* [JUnit](https://junit.org/junit4/) - Unit Testing Framework
* [mockito](http://site.mockito.org/) - Mocking Framework for Unit Tests
* [junit-dataprovider](https://github.com/TNG/junit-dataprovider) - Data Provider Runner for JUnit
* [Cucumber-JVM](https://cucumber.io/docs/reference/jvm) - A BDD testing framework implementation for Java

## Getting started
In the folder [./src/test/java/workshop/calculator/README.md](./src/test/java/workshop/calculator/README.md) you will find the acceptance criteria for the calculator functionality. Try to implement these criteria by the TDD approach en BDD approach. The outcome should at least have 15 tests passing.

## Naming conventions

Tests serve 3 purposes:

* [Acceptance Criteria](https://en.wikipedia.org/wiki/Acceptance_testing) - Ensures developed code meets specification
* [Regression Testing](https://en.wikipedia.org/wiki/Regression_testing) - Ensures new changes don't impact previous developed code
* **Documentation** - Demonstrates how the application behaves

To achieve proper documentation, a good starting point is to create naming conventions for the tests.

You can define your own conventions keeping in mind that the test methods should clearly identify:

* What is being tested
* What is the Scenario (Input)
* What should be the outcome (Output)

Example with a traditional approach (simple JUnit):

```java
@Test
public void testSum_BothNumbersArePositive_ShouldReturnPositiveNumber() {
...
}
```

The method name should be read as :

Test sum **IF** both numbers are positive **THEN** should return positive number.

Example with a BDD approach:

```gherkin
Feature: Calculator
  The calculator supports the sum operation.

  Scenario: Adding positive numbers
    Given I use a calculator
    When I add positive numbers
    Then The result should be positive
```


### AAA Pattern

Tests typically follow the AAA pattern:

* **A**rrange - Setup of the Scenario, e.g.: creating the input data
* **A**ct - Executing the action/method
* **A**ssert - Validation of the outcome

Example:


```java
@Test
public void testSum_BothNumbersArePositive_ShouldReturnPositiveNumber() {
    // Arrange
    int a = 10;
    int b = 20;
    Calculator calc = new Calculator();

    // Act
    int result = calc.sum(a, b);

    // Assert
    Assert.assertTrue(result > 0);
}
```

## Mocks & Stubs

[Mocks](https://en.wikipedia.org/wiki/Mock_object) and [Stubs](https://en.wikipedia.org/wiki/Method_stub) are used to facilitate testing by solving the problem of dependencies.

When the code you are implementing has a dependency, using this technique, you create a fake object that emulates that dependency. If you are required to define specific return values to emulate a certain scenario then you'll need to use a **stub** otherwise you'll simply use a **mock**.


Example:


* **Mock**

```java
provider = mock(PaymentProviderInterface.class);
broker = new PaymentBroker(provider);
```

* **Stub**
```java
provider = mock(PaymentProviderInterface.class);
broker = new PaymentBroker(provider);
when(provider.isAvailable()).thenReturn(false);