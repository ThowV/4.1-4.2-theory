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
-   Hides dependancy;
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

Attributes of the Dependancy injection pattern

-   The dependancies are made explicit;
-   The responsibility for ceating the dependencies are outside of the class using them;
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
