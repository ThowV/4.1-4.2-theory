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
