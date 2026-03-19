### How to Run the Tests

1. Navigate to the project directory.

2. Compile the source code and tests (all .java files):
        javac -cp .:junit-4.13.2.jar:hamcrest-core-1.3.jar *.java

3. Run the test suite:
        java -cp .:junit-4.13.2.jar:hamcrest-core-1.3.jar org.junit.runner.JUnitCore TestSuiteAll

4. Run individual test class:
    To run an individual test class, such as **`CalculatorTest`**, use:
        java -cp .:junit-4.13.2.jar:hamcrest-core-1.3.jar org.junit.runner.JUnitCore CalculatorTest

5. Output logs
    To generate a detailed output log of all the tests(150 in total), redirect the output to a file named **`OUTPUT.txt`** with the following command:
        java -cp .:junit-4.13.2.jar:hamcrest-core-1.3.jar org.junit.runner.JUnitCore TestSuiteAll > OUTPUT.txt

    Additionally, if running the test suite using the custom **`main`** method in **`TestSuiteAll`** that adds a **`TestListener`** for detailed logging is desired, direct this output to **`OUTPUT.txt`** like so:
        java -cp ".:junit-4.13.2.jar:hamcrest-core-1.3.jar" TestSuiteAll >> OUTPUT.txt


!!!**If you are on Windows, replace `:` with `;`.**






## Description

This project is designed to showcase the fundamentals of unit testing using Java and its framework. It includes a main program along with multiple classes, and unit tests for all methods in each class (with three test cases per method), excluding the main class.

## Class Descriptions

1. Calculator: This class handles basic arithmetic operations such as addition, subtraction, multiplication, division and square.
2. Checker: This class handles checking if a number is even, odd, positive, prime, or a palindrome.
3. Converter: This class handles converting units such as temperature, weight and distance.
4. ArraySorter: This class handles sorting arrays in ascending or descending order. It also includes methods for finding the maximum and minimum values, and calculating the sum of all values in an array.
5. Randomizer: This class handles generating random numbers within a given range. It can also generate a list of random integers within a specified range, and an array of random integers within a specified range. It can also pick a random element from a given list and generate a random boolean value.
6. Board: This class manages the game board, including setting up the board and handling moves from players.
7. PlayerProfile: This class stores and manages information about a player, such as their username, score history, and other profile details.
8. PatternDrawer: This class is used to create and draw patterns, including squares, rectangles, triangles, diamonds, and hearts.
9. SequenceGenerator: This class generates a variety of sequences such as even, prime, arithmetic, geometric, and Fibonacci.
10. BankAccount: This class simulates a bank account, tracking the balance, handling deposits and withdrawals, and adds interset.


## Software Requirements

- Java Development Environment (JDK and JRE)
- JUnit Library
- Hamcrest Library
- CPSuite Library


## **Testing Different Types of Methods**

- **void methods:** Test for changes in the system state or specific interactions. For example, if a method modifies an object, you can test whether the object is modified as expected.
- **Methods returning a value:** Test the returned value against the expected value. For example, if a method is supposed to return a sum of two numbers, you can test whether the returned value is the expected sum.
- **Methods that change the state of an object:** Test if the state of the object has changed as expected after the method call.
- **Methods that return a boolean:** Test for both true and false cases.
- **Methods that return an array or collection:** Test the size and content of the returned array or collection.
- **Methods that throw exceptions:** Test whether the expected exceptions are thrown under the specified conditions.
- **Methods that interact with dependencies:** Test whether the method interacts with its dependencies as expected using mocks or stubs.

## **JUnit Testing Methods**

- **assertEquals(expected, actual):** This method asserts that the expected value and the actual value are equal. If they are not, the test fails. For example, `assertEquals(5, calculator.add(2, 3));`.
- **assertNotEquals(expected, actual):** This method asserts that the expected value and the actual value are not equal. If they are equal, the test fails.
- **assertTrue(condition):** This method asserts that the condition is true. If it's not, the test fails. For example, `assertTrue("Should be true", condition);`.
- **assertFalse(condition):** This method asserts that the condition is false. If it's not, the test fails. For example, `assertFalse("Should be false", condition);`.
- **assertNull(object):** This method asserts that the object is null. If it's not, the test fails.
- **assertNotNull(object):** This method asserts that the object is not null. If it is, the test fails.
- **assertSame(expected, actual):** This method asserts that the expected and actual refer to the exact same object. If they do not, the test fails.
- **assertNotSame(expected, actual):** This method asserts that the expected and actual do not refer to the exact same object. If they do, the test fails.
- **assertArrayEquals(expectedArray, resultArray):** This method asserts that the expected array and the result array are equal in terms of length and content. If they are not, the test fails.

## **Examples of Test Methods**

```java
@Test
	public void testAdd1() {
		// Test if the addition function adds positive numbers correctly
		assertEquals(7, calculator.add(3, 4));
	}
```

```java
@Test
	public void testSortAscending1() {
		// Test sorting an already sorted array
		assertArrayEquals(new int[]{1, 2, 3},
				sorter.sortAscending(new int[]{1, 2, 3}));
	}
```

```java
@Test
	public void testIsValidMove1() {
		this.board.initializeBoard(); // Initialize the board
		// Check if a valid cell is indeed valid
		assertTrue(this.board.isValidMove(0, 0));
		// Check if an out-of-bound cell is detected as invalid
		assertFalse(this.board.isValidMove(3, 3));
	}
```

```java
@Test(expected = IllegalArgumentException.class)
	public void testDivide3() {
		// Test if the division function throws an exception
		// when dividing by zero
		calculator.divide(1, 0);
	}
```

```java
@Test
	public void testDrawSquare1() {
		String expected = "* * \n" +
                                  "* * \n";
		patternDrawer.drawSquare(2, '*');
		assertEquals(expected, outContent.toString());
		outContent.reset();
	}
```

```java
@Test
	public void testInitializeBoard2() {
		this.board.initializeBoard(); // Initialize the board
		// Check if the winner is initialized to null
		assertNull(this.board.getWinner());
	}
```
