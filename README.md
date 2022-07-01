# contact-manager
Contact Manager application developed for Junit 5 Tutorial


#### Junit is a simple framework to write repeatable tests

* Junit 5 is the combination of three module
* junit platform: The Junit Platform project provides an API to launch the tests from either the IDE’s, Build Tools or Console. It defines a TestEngine API which enables development of new Testing Frameworks on top of the Platform.
* junit jupiter : This project provides API to write our Junit tests and extensions, it contains new annotations and a TestEngine implementation to run these tests on the platform.
junit vintage This project provides a TestEngine implementation to support backward compatibility for tests written with Junit 3 and Junit4.


#### Different phase of junit 5
- @BeforeAll :It will execute before all test case
- @BeforeEach: It will run before each test case
- @Test : It will run the test case
- @AfterEach : It will run after each test case
- @AfterAll : It will run after all test case.

_Note: @BeforeAll and @BeforeEach is  used to perform initialization tasks for tests._

_Note: @AfterAll and @AfterEach is used to perform the cleanup tasks for tests._

Junit instantiate  the test class only once in java using the @TestInstance(TestInstance.Lifecycle.PER_CLASS) then we can remove static keyword from @beforeAll method and @AfterAll method

#### Conditional execution of test class.
@EnabledOnOs -> enable on os level
@DisabledOnOs -> disable on os level


#### Assumptions

The test will not fail but aborted if the testing environment is different.


#### RepeatedTest

@RepeatedTest annotation

Repeat test for certain number of time in case of random number.

It will repeat 5 times.
@RepeatedTest(value = 5)

@RepeatedTest(value = 5 , name="Repeating Contact creation Test {currentRepeatition} of {totalRepeatitions})
Junit automatically fills {currentRepeatition} and {totalRepeatitions} values to show current count.


#### Parameterized Tests in Junit
@ParameterizedTest annotation

Similar to repeated test but difference is we can run the test repeatedly by different set of input.

- Test are executed with different set of input.
- substitute @Test
- Data is provided using different annotations:
- @ValueSource, @CsvSource, @MethodSource, @CsvFileSource

@ValueSource accepts different literal value like strings, ints, longs, shorts, floats, double, byte, char, classes

Another way of providing value to parameterized test is using the @MethodSource

#### Nested Test
- Used to group tests together into a logical group.
- Makes the test class more organized
- @Nested used on the  top of the class
- Can only use @BeforeEach and @AfterEach
- Cannot use @BeforeAll and @AfterAll by default. Because java doesnot allow static method in the innner classes.
- If we want to use static method in nested class we can do that using @TestInstance(TestInstance.Lifecycle.PER_CLASS) at the top of class.


#### Disabled test
@Disabled is use to disable some test
