# Test Driven Development

Tradionally we write implementations and tests afterwords. With TDD we first write our tests, then we write the implementation. These tests should be extremely small and should always indicate that a piece of code works.

-   **Quality checking**: Seek problems;
-   **Quality assurance**: Prevent problems;
-   **TDD** is **Quality assurance**

TDD should:

-   Make tests more relevant;
-   Improve the trust in the source code;
-   Make changes more safe;
-   Make documentation more up-to-date as the tests document the code. Old method of documentation is quickly rendered outdated;
-   Improve the design;
-   Lessen the coupling between parts;

TDD is used in cycles: Red-green-refactor.

## 1. Red-green-refactor

1. Write new tests;
2. Run all tests;
3. Implement the changes;
4. Run all tests again;
5. Refactor;
6. Run all tests again;

All tests should always run as this lessens the regression mistakes. The coupling of external systems should be mocked in order to keep our tests quick.

-   **Red**: Newly written tests should fail;
-   **Green**: Implement the change in order for the test to work again, either write a new test or start refactoring;
-   **Blue**: Refactor the entire function that the tests pertain to in order to make the code cleaner;

## 2. Testing methods

### 2.1 White-box testing

-   The internals of the code are known;
-   Usually created by the developers;
-   Entire code base is tested;

### 2.2 Black-box testing

-   Functional tests;
-   The internals of the code are not known;
-   You write tests based on the acceptation criteria;
-   Can be done by external testers;
-   Some implementations will be skipped over, there's a small coverage of the code base;

## 3. Unit testing

-   Small units of code should be tested;
-   Units are usually methods;
-   External dependencies are replaced with mocks;
-   Use the arrange-act-assert pattern;
    -   **Arrange**: The objects being tested should be configured;
    -   **Act**: Call the method that is being tested;
    -   **Assert**: Make sure the output is valid;

### 3.1 Unit testing using JUnit

-   Every test case in a test class will be ran with a new test class instantiation, which makes tests independant of each other;
-   `@Test` Marks the method that are test cases;
-   `@BeforeAll` en `@AfterAll` are called once before or achter all test cases in a class have ran. These methods must be static;
-   `@BeforeEach` en `@AfterEach` are called once before or achter a single test case in a class has ran;

## 4. Design patterns

### 4.1 SOLID design principles

**SOLID** consists of 5 design principles:

-   **S**ingle Responsibility Principle:
    -   Every class/method has one responsibility;
    -   There's only one reason to change;
    -   This makes it clear what a unit consists of for testing;
-   **O**pen-Closed Principle:
    -   Open for expansion;
    -   Closed for change;
    -   Unit tests don't have to be changed/updated;
    -   You can write new classes/methods and corresponding unit tests for the expansion;
-   **L**iskov Substitution Principle:
    -   An object from a subclass has to be able to be used everywhere where an object of the superclass is requested;
    -   Mocks are, most of the time, instantiations from a subclass;
    -   Not all subclasses have to be tested when the superclass is used;
-   **I**nterface Segregation Principle:
    -   Every interface only holds the minimally required amount of methods to fulfill it's function;
    -   Creating mocks is easier, there are not as many methods to keep in mind;
-   **D**ependency Inversion Principle:
    -   High-level modules are not dependant on low-level modules; Both are dependant on abstractions;
    -   Abstractions are not dependant on details; Details are dependant on abstractions;
    -   Abstractions are interfaces; Details are implementations from interfaces;
    -   Program against interfaces;
    -   This makes it easy to use mocks for tests instead of real objects;

### 4.2 Design Pattern: Singleton pattern

```C#
public enum Singleton {
    INSTANCE;

    public void method() {
        /* ... */
    }
}
```

Attributes of the Singleton pattern:

-   Effectively a static method;
-   Hides dependency;
-   Not open-closed, the class can't be expanded;
-   No dependency inversion, the users are dependant on the concrete implementation;

### 4.3 Design Pattern: Service locator pattern

```C#
public class ServiceLocator {
    public static <T> T get(Class<T> class) {
        /* ... */
    }
}

public class Example {
    public void method() {
        Foo foo = ServiceLocator.get(Foo.class);
    }
}
```

Attributes of the Service locator pattern

-   Effectively the same a multiple singletons;
-   Not open-closed and no dependency inversion;
-   Effectively an unlimited amount of methods for every type;

### 4.4 Design Pattern: Dependency injection pattern

```C#
public class Example {
    private readonly Foo _foo;

    public Example(Foo foo) {
        this._foo = foo;
    }

    public void method() {
        /* ... */
    }
}
```

Attributes of the Dependency injection pattern

-   The dependancies are made explicit;
-   The responsibility for creating the dependencies are outside of the class using them;
-   Constructor injection: Dependencies are passed into the constructor;
-   Setter injection: Dependencies are passed into the setters;

### 4.5 Composition over iheritance

-   Composition: Creating an object using components;
-   Composition gives better incapsulation than inheritance;
-   Changes in a superclass lead to changes in a subclass;
-   With inheritance a relation is determined during compilation;
-   With composition a relation can be made whilst the program is running;

Inheritance looks like this:

```C#
public class Text {
    protected readonly String _s;

    public Text(String s) {
        this._s = s
    }
}

public class UppercaseText extends Text {
    public UppercaseText(String s) {
        super(s);
    }

    public String asString() {
        return _s.toUpperCase();
    }
}

public class SpacedText extends Text {
    public SpacedText(String s) {
        super(s);
    }

    public String asString() {
        return String.join(" ", _s.split(""));
    }
}
```

-   Tests for the subclasses of StringLike are dependant on the superclass itself. Whenever the superclass changes the subclasses need to change as well;
-   Protected methods in the superclass are part of the public interface which means they also have to be tested;

But what if we want the text to be both uppercased and have spaces between each letter? This is where composition is a good choice:

```C#
public interface StringLike {
    String asString();
}

public class UppercaseDecorator implements StringLike {
    private readonly StringLike _s;

    public UppercaseDecorator(String s) {
        this._s = s;
    }

    public String asString() {
        return _s.asString.toUpperCase();
    }
}

public class SpacedDecorator implements StringLike {
    private readonly StringLike _s;

    public SpacedDecorator(String s) {
        this._s = s;
    }

    public String asString() {
        return String.join(" ", _s.asString().split(""));
    }
}
```

## 5. Test designs

Testing takes time and is expensive. Therefore, you should choose wisely what to test and what not to test. Functionality that is going to be used often or that is critical to the product should be tested extensively, whilst functionality that is not going to be used as often should not be tested extensively or at all to save on costs.

A test design is a collection of test cases that are picked in order to fit the budget. A test case consists of the following:

-   Initial situation: Everything that should be setup before the test can take place;
-   Action: The actions that have to take place (input, processing), generates an output;
-   Comparison: The actual output is compared against the expected output;

## 6. Configuration management

Configuration management is more than just version management such as Git. Development environments should mimick production environments as closely as possible.

Example: Development might take place on a windows machine but deployment on a unix machine. File names are treated differently on both machines which means the application might break as the configuration of both machines differ.

Tip: Use Docker. Docker treats the configuration as one whole piece and is universal between machines.

Configuration management also pertains to tests, documentation (of requirements) and external libraries.

So in your version management you should add your configurations, scripts, tests, etc. and commit as frequently as possible. Commit messages should be clear as they are documentation to other developers. Exception: Do not save passwords or secret keys in your version management!

There are a few different types of version management systems:

-   Centralized version management:
    -   There's one central repository;
    -   All commits instantly go to the server;
    -   Pros:
        -   Unambiguous as the what sits on the server is always the truth;
    -   Cons:
        -   If the server breaks the truth is lost.
-   Distributed version management (modern):
    -   There's no central repository, all copies are one and the same;
    -   One copy is often marked as the central/base version;
    -   Commits are local and have to explicitly be pushed to the server;

In version management system we often use branches to distinguish work on certain different features/fixes. Branches are seperate copies of the codebase which can be modified and merged at a later date. Merging means adding one branch to another. Merging is automatically completed whenever changes do not overlap, however, sometimes changes may conflict. Conflicts must manually be fixed.

Some conflicts might not be recognized. Syntactic conflicts for example:

```java
// BASE BRANCH
int method() {
    int x = 5;
    return x;
}
```

```java
// BRANCH A
int method() {
    int y = 5;
    return y;
}
```

```java
// BRANCH B
int method() {
    int x = 5;
    x += 2;
    return x;
}
```

```java
// BRANCHES A AND B ARE MERGED
int method() {
    int y = 5;
    x += 2;
    return y;
}
```

## 7. Continuous intergration

Build automation automatically builds your code into excecutables. Build automation can also do other tasks such as running tests. Most of the time build automation systems are used to handle dependencies/external libraries. These dependencies are locked into versions in order for builds to be reproducable.

Build automation is used to enable Continuous Intergration. In Continuous Intergration we often merge changes into the mainline-branch. This merging is supported by automatically running some tests beforehand so you can be certain that your code still works.

The process goes as follows:

-   The developer pushes changes to the Version Control Server (VCS).
-   The Continuous Intergration Server fetches these changes and:
    -   Builds;
    -   Tests;
    -   Either fails or succeeds;
-   The Continuous Intergration Server notifies the manager and a couple of developers of the succes or server;

Locally, changes should also be tested:

-   Commit locally;
-   Test locally;
-   Push to the VCS;
-   Wait intull the CIS checked the build;
-   Fix issues as they arise;

Continuous Intergration only works when the following guidelines are followed:

-   Commit as often as possible:
    -   Multiple times a day;
    -   Merge conflicts stay small;
    -   You can always revert to a working version;
-   Have an automatic test suite:
    -   Application doesn't just compile but is also tested to make sure it works;
    -   Automatic unit tests to find issues as quickly as possible;
    -   Automatic intergration and accaptence tests to test the entire application;
-   Make sure builds and tests are quick:
    -   Long builds or tests are frustrating;
    -   Developers are going to undermine the system;
    -   Multiple commits are made while tests are still running causing a jam;
    -   Create smoke tests instead of entire acceptance tests;
-   Make sure development environments are managed:
    -   Makes sure that local development always works;
    -   Makes sure that reverting to a known working state is easy;
    -   Configuration management for test data, build scripts, ...;
    -   Configuration management for dependencies;
    -   Tests should be runnable on the local system;

When branches are made in Continuous Intergration the following should be taken note of:

-   Large branches are often not tested using the CI-tools;
-   Large branches are often merged right before a release;
-   In order for everything to keep working you should merge the mainline branch with the feature branch to keep eventual merge conflicts as small as possible;

Development has the following steps: Code > Build > Intergrate > Release > Deploy.

Continuous Intergration only covers the first three steps, there are other terms that cover the other steps:

-   Continuous Delivery: Continuous Intergration + Release:
    -   Automatically build a release so they can be deployed easily;
    -   Automatically run acceptance tests on a stage environment/branch;
    -   Deployment has to be done manually;
-   Continuous Deployment: Continuous Delivery + Deploy:
    -   Automatically deploy the release;
    -   Every commit is essentialy placed into the live enviroment;
    -   Is only viable if the test suite is thorough;

## 8. Test piramid

Tests come in different forms which form the test pyramid:

-   Manual tests (slow and expensive);
    -   All tests should be able to be automated but wherever it isn't possible manual tests should fill the gap;
-   UI tests (a bit faster and a bit cheaper);
    -   Tests the system through the eyes of the user;
    -   Are fragile as small changes in the UI can break the test;
-   Integration tests (fast and cheap):
    -   Tests parts that have to work together such as the connection between code and database;
    -   Uses actual services such as an actual database connection;
    -   Code functionality is not being tested, just the code that calls the service;
    -   Slower than unit tests but fewer are needed;
-   Unit tests (fastest and cheapest):
    -   Tests individual parts of the software;
    -   Uses mocks to simulate external services such as a database;

## 9. Behaviour-driven development

-   The behaviour of the application is described in standard language;
-   Does not have to be written by developers;
-   BDD is outside-in: From features to units;
-   TDD is inside-out: From units to features;

A BDD test looks like the following:

-   Narrative: "In order to ..., as a ..., I want to ...";
-   Scenario's: "Given ..., when ..., then ...";
-   Scenario'sserve as the acceptance criteria for the narrative;
-   "Given" defines the precondition (arrange);
-   "When" defines the actions (act);
-   "Then" defines the expectations (assert);
