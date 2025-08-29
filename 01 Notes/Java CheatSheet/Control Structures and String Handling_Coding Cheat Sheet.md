# Using Conditional Statements
#Java 

## if statement

The `if` statement checks a condition. If the condition is `true`, it executes the code inside the block. If the condition is `false`, the program skips the `if` block.

|Description|Example|
|---|---|
|A Java class named `Main` with a `main` method. The `main` method is the entry point of the program.|1. 1<br><br>1. public class Main {<br><br>Copied!Wrap Toggled!|
|The `main` method is declared using `public static void main(String[] args)`. This method is required for execution in Java programs.|1. 1<br><br>1. public static void main(String[] args) {<br><br>Copied!Wrap Toggled!|
|A variable `number` of type `int` is declared and initialized with the value `10`.|1. 1<br><br>1. int number = 10;<br><br>Copied!Wrap Toggled!|
|The `if` statement checks if `number` is greater than `5`. If `true`, it prints "The number is greater than 5."|1. 1<br><br>1. if (number > 5) {  <br>        System.out.println("The number is greater than 5.");  <br>    }<br><br>Copied!Wrap Toggled!|
|Closing curly braces to end the `main` method and class definition.|1. 1<br><br>1.     }  <br>    }<br><br>Copied!Wrap Toggled!|

**Explanation:** Since `number` is `10`, which is greater than `5`, the condition evaluates to `true`, and the program prints `"The number is greater than 5."`

---

## if-else statement

The `if-else` statement gives an alternative if the condition is `false`.

|Description|Example|
|---|---|
|A Java class named `Main` with a `main` method. The `main` method is the entry point of the program.|1. 1<br><br>1. public class Main {<br><br>Copied!Wrap Toggled!|
|The `main` method is declared using `public static void main(String[] args)`. This method is required for execution in Java programs.|1. 1<br><br>1. public static void main(String[] args) {<br><br>Copied!Wrap Toggled!|
|A variable `number` of type `int` is declared and initialized with the value `3`.|1. 1<br><br>1. int number = 3;<br><br>Copied!Wrap Toggled!|
|The `if` statement checks if `number` is greater than `5`. If `true`, it prints "The number is greater than 5."|1. 1<br><br>1. if (number > 5) {  <br>        System.out.println("The number is greater than 5.");  <br>    }<br><br>Copied!Wrap Toggled!|
|The `else` block executes when the `if` condition is `false`, printing "The number is not greater than 5."|1. 1<br><br>1. else {  <br>        System.out.println("The number is not greater than 5.");  <br>    }<br><br>Copied!Wrap Toggled!|
|Closing curly braces to end the `main` method and class definition.|1. 1<br><br>1.     }  <br>    }<br><br>Copied!Wrap Toggled!|

---

## else if statement

You can check multiple conditions using `else if`.

|Description|Example|
|---|---|
|A Java class named `Main` with a `main` method. The `main` method is the entry point of the program.|1. 1<br><br>1. public class Main {<br><br>Copied!Wrap Toggled!|
|The `main` method is declared using `public static void main(String[] args)`. This method is required for execution in Java programs.|1. 1<br><br>1. public static void main(String[] args) {<br><br>Copied!Wrap Toggled!|
|A variable `number` of type `int` is declared and initialized with the value `5`.|1. 1<br><br>1. int number = 5;<br><br>Copied!Wrap Toggled!|
|The `if` statement checks if `number` is greater than `5`. If `true`, it prints "The number is greater than 5."|1. 1<br><br>1. if (number > 5) {  <br>        System.out.println("The number is greater than 5.");  <br>    }<br><br>Copied!Wrap Toggled!|
|The `else if` statement checks if `number` is exactly `5`. If `true`, it prints "The number is equal to 5."|1. 1<br><br>1. else if (number == 5) {  <br>        System.out.println("The number is equal to 5.");  <br>    }<br><br>Copied!Wrap Toggled!|
|The `else` block executes when none of the above conditions are met, printing "The number is less than 5."|1. 1<br><br>1. else {  <br>        System.out.println("The number is less than 5.");  <br>    }<br><br>Copied!Wrap Toggled!|
|Closing curly braces to end the `main` method and class definition.|1. 1<br><br>1.     }  <br>    }<br><br>Copied!Wrap Toggled!|

**Explanation:** Since `number` is exactly `5`, the program prints `"The number is equal to 5."`

---

## switch statement

A `switch` statement checks a single variable against multiple values.

|Description|Example|
|---|---|
|A Java class named `Main` with a `main` method. The `main` method is the entry point of the program.|1. 1<br><br>1. public class Main {<br><br>Copied!Wrap Toggled!|
|The `main` method is declared using `public static void main(String[] args)`. This method is required for execution in Java programs.|1. 1<br><br>1. public static void main(String[] args) {<br><br>Copied!Wrap Toggled!|
|A variable `day` of type `int` is declared and initialized with the value `3`.|1. 1<br><br>1. int day = 3;<br><br>Copied!Wrap Toggled!|
|The `switch` statement checks the value of `day` and compares it against the `case` labels. If `day` is `3`, it prints `"Wednesday"`.|1. 1<br><br>1. switch (day) {  <br>        case 1:   <br>            System.out.println("Monday");  <br>            break;  <br>        case 2:   <br>            System.out.println("Tuesday");  <br>            break;  <br>        case 3:   <br>            System.out.println("Wednesday");  <br>            break;  <br>        case 4:   <br>            System.out.println("Thursday");  <br>            break;  <br>        case 5:   <br>            System.out.println("Friday");  <br>            break;  <br>        default:   <br>            System.out.println("Weekend");  <br>    }<br><br>Copied!Wrap Toggled!|
|Closing curly braces to end the `main` method and class definition.|1. 1<br><br>1.     }  <br>    }<br><br>Copied!Wrap Toggled!|

---

## default case in a switch statement

When using a `switch` statement, it's a good practice to specify a `default` case. This case runs if none of the specified cases match, acting as a fallback option.

|Description|Example|
|---|---|
|A `switch` statement checks the value of a variable `color`.|1. 1<br><br>1. switch (color) {<br><br>Copied!Wrap Toggled!|
|A `case` checks if `color` is `"red"`, printing `"Color is red."`|1. 1<br><br>1.     case "red":  <br>            System.out.println("Color is red.");  <br>            break;<br><br>Copied!Wrap Toggled!|
|A `case` checks if `color` is `"blue"`, printing `"Color is blue."`|1. 1<br><br>1.     case "blue":  <br>            System.out.println("Color is blue.");  <br>            break;<br><br>Copied!Wrap Toggled!|
|The `default` case prints `"Unknown color."` if `color` doesn't match `"red"` or `"blue"`.|1. 1<br><br>1.     default:  <br>            System.out.println("Unknown color.");  <br>    }<br><br>Copied!Wrap Toggled!|

---

## Nested Conditional Statements

You can place conditional statements within each other to create more complex decisions. The process of placing conditional statements within other conditional statements is called nesting.

| Description                                                                                                                           | Example                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| A Java class named `Main` with a `main` method. The `main` method is the entry point of the program.                                  | 1. 1<br><br>1. public class Main {<br><br>Copied!Wrap Toggled!                                                                       |
| The `main` method is declared using `public static void main(String[] args)`. This method is required for execution in Java programs. | 1. 1<br><br>1. public static void main(String[] args) {<br><br>Copied!Wrap Toggled!                                                  |
| A variable `age` of type `int` is declared and initialized with the value `20`.                                                       | 1. 1<br><br>1. int age = 20;<br><br>Copied!Wrap Toggled!                                                                             |
| The `if` statement checks if `age` is greater than or equal to `18`. If `true`, it prints `"You are an adult."`                       | 1. 1<br><br>1. if (age >= 18) {  <br>        System.out.println("You are an adult.");  <br>    }<br><br>Copied!Wrap Toggled!         |
| Another `if` statement checks if `age` is greater than or equal to `65`, printing `"You are a senior citizen."` if true.              | 1. 1<br><br>1. if (age >= 65) {  <br>        System.out.println("You are a senior citizen.");  <br>    }<br><br>Copied!Wrap Toggled! |
| The `else` block executes if `age` is less than `18`, printing `"You are a minor."`                                                   | 1. 1<br><br>1. else {  <br>        System.out.println("You are a minor.");  <br>    }<br><br>Copied!Wrap Toggled!                    |
| Closing curly braces to end the `main` method and class definition.                                                                   | 1. 1<br><br>1.     }  <br>    }<br><br>Copied!Wrap Toggled!                                                                          |
# Introduction to Loops in Java

## for Loop

The for loop is used when the number of iterations is known beforehand. It consists of three parts:

- Initialization: This sets a counter variable.
- Condition: This checks if the loop should continue executing.
- Increment/Decrement: This updates the counter variable after each iteration.

|Description|Example|
|---|---|
|A Java class named `ForLoopExample` with a `main` method. The `main` method is the entry point of the program.|1. 1<br><br>1. public class ForLoopExample {<br><br>Copied!Wrap Toggled!|
|The `main` method is declared using `public static void main(String[] args)`. This method is required for execution in Java programs.|1. 1<br><br>1. public static void main(String[] args) {<br><br>Copied!Wrap Toggled!|
|A for loop is initialized with `int i = 1`, which starts the counter at 1. The counter variable `i` is incremented by `i++` after each iteration.|1. 1<br><br>1. for (int i = 1; i <= 5; i++) {<br><br>Copied!Wrap Toggled!|
|The loop checks if `i <= 5`, and if true, it prints the value of `i`.|1. 1<br><br>1. System.out.println(i);<br><br>Copied!Wrap Toggled!|
|Close the `for` loop.|1. 1<br><br>1.         }<br><br>Copied!Wrap Toggled!|
|Close the `main` method.|1. 1<br><br>1.     }<br><br>Copied!Wrap Toggled!|
|Close the `ForLoopExample` class.|1. 1<br><br>1. }<br><br>Copied!Wrap Toggled!|

## while Loop

The while loop is used when the number of iterations is not known in advance. It continues executing as long as the specified condition remains true.

|Description|Example|
|---|---|
|A Java class named `WhileLoopExample` with a `main` method. The `main` method is the entry point of the program.|1. 1<br><br>1. public class WhileLoopExample {<br><br>Copied!Wrap Toggled!|
|The `main` method is declared using `public static void main(String[] args)`. This method is required for execution in Java programs.|1. 1<br><br>1. public static void main(String[] args) {<br><br>Copied!Wrap Toggled!|
|A variable `i` is initialized to `1`.|1. 1<br><br>1. int i = 1;<br><br>Copied!Wrap Toggled!|
|The while loop continues as long as `i <= 5`.|1. 1<br><br>1. while (i <= 5) {<br><br>Copied!Wrap Toggled!|
|Inside the loop, the value of `i` is printed, then incremented by `i++`.|1. 1<br><br>1. System.out.println(i);  <br>    i++;  <br>    }<br><br>Copied!Wrap Toggled!|
|The `main` method and class are closed with curly braces.|1. 1<br><br>1. }  <br>    }<br><br>Copied!Wrap Toggled!|

## do-while Loop

The do-while loop is similar to the while loop but guarantees that the code block executes at least once before checking the condition.

|Description|Example|
|---|---|
|A Java class named `DoWhileLoopExample` with a `main` method. The `main` method is the entry point of the program.|1. 1<br><br>1. public class DoWhileLoopExample {<br><br>Copied!Wrap Toggled!|
|The `main` method is declared using `public static void main(String[] args)`. This method is required for execution in Java programs.|1. 1<br><br>1. public static void main(String[] args) {<br><br>Copied!Wrap Toggled!|
|A variable `i` is initialized to `1`.|1. 1<br><br>1. int i = 1;<br><br>Copied!Wrap Toggled!|
|The do-while loop starts and executes at least once before checking if `i <= 5`.|1. 1<br><br>1. do {<br><br>Copied!Wrap Toggled!|
|Inside the loop, the value of `i` is printed, then incremented by `i++`.|1. 1<br><br>1. System.out.println(i);  <br>    i++;<br><br>Copied!Wrap Toggled!|
|The condition `i <= 5` is checked after each iteration.|1. 1<br><br>1. } while (i <= 5);<br><br>Copied!Wrap Toggled!|
|The `main` method and class are closed with curly braces.|1. 1<br><br>1. }  <br>    }<br><br>Copied!Wrap Toggled!|

## Nested loops

You can also use loops inside other loops, known as nested loops. This is useful for working with multi-dimensional data structures, like arrays or matrices.

|Description|Example|
|---|---|
|A Java class named `NestedLoopsExample` with a `main` method. The `main` method is the entry point of the program.|1. 1<br><br>1. public class NestedLoopsExample {<br><br>Copied!Wrap Toggled!|
|The `main` method is declared using `public static void main(String[] args)`. This method is required for execution in Java programs.|1. 1<br><br>1. public static void main(String[] args) {<br><br>Copied!Wrap Toggled!|
|The outer loop controls the rows, running 10 times.|1. 1<br><br>1. for (int i = 1; i <= 10; i++) {<br><br>Copied!Wrap Toggled!|
|The inner loop controls the columns, also running 10 times for each row.|1. 1<br><br>1. for (int j = 1; j <= 10; j++) {<br><br>Copied!Wrap Toggled!|
|The product of `i * j` is printed for each combination of rows and columns.|1. 1<br><br>1. System.out.print(i * j + "\t");}<br><br>Copied!Wrap Toggled!|
|After the inner loop, a newline is printed to separate the rows.|1. 1<br><br>1. System.out.println();}<br><br>Copied!Wrap Toggled!|
|The `main` method and class are closed with curly braces.|1. 1<br><br>1. }  <br>    }<br><br>Copied!Wrap Toggled!|

## break statement

The break statement is used to terminate a loop immediately, regardless of the loop's condition. This can be useful when you want to exit a loop based on a specific condition that may occur during its execution.

|Description|Example|
|---|---|
|A Java class named `BreakExample` with a `main` method. The `main` method is the entry point of the program.|1. 1<br><br>1. public class BreakExample {<br><br>Copied!Wrap Toggled!|
|The `main` method is declared using `public static void main(String[] args)`. This method is required for execution in Java programs.|1. 1<br><br>1. public static void main(String[] args) {<br><br>Copied!Wrap Toggled!|
|An array `numbers` is declared and initialized.|1. 1<br><br>1. int[] numbers = {1, 3, 5, 7, 9, 2, 4};<br><br>Copied!Wrap Toggled!|
|The loop iterates through the array, checking if any number is greater than 5.|1. 1<br><br>1. for (int num : numbers) {<br><br>Copied!Wrap Toggled!|
|When a number greater than 5 is found, it is printed and the loop exits with the `break` statement.|1. 1<br><br>1. if (num > 5) {  <br>    System.out.println(num);  <br>    break;  <br>    }<br><br>Copied!Wrap Toggled!|
|The `main` method and class are closed with curly braces.|1. 1<br><br>1. }  <br>    }  <br>    }<br><br>Copied!Wrap Toggled!|

## continue statement

The continue statement is used to skip the current iteration of a loop and move to the next iteration. It's useful when you want to skip certain conditions but continue executing the rest of the loop.

| Description                                                                                                                           | Example                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| A Java class named `ContinueExample` with a `main` method. The `main` method is the entry point of the program.                       | 1. 1<br><br>1. public class ContinueExample {<br><br>Copied!Wrap Toggled!               |
| The `main` method is declared using `public static void main(String[] args)`. This method is required for execution in Java programs. | 1. 1<br><br>1. public static void main(String[] args) {<br><br>Copied!Wrap Toggled!     |
| The loop iterates through the numbers from 1 to 10.                                                                                   | 1. 1<br><br>1. for (int i = 1; i <= 10; i++) {<br><br>Copied!Wrap Toggled!              |
| When `i == 5`, the `continue` statement is executed, skipping the `System.out.println(i);` statement for that iteration.              | 1. 1<br><br>1. if (i == 5) {  <br>     continue;  <br>    }<br><br>Copied!Wrap Toggled! |
| The value of `i` is printed for all numbers except 5.                                                                                 | 1. 1<br><br>1. System.out.println(i);<br><br>Copied!Wrap Toggled!                       |
| The `main` method and class are closed with curly braces.                                                                             | 1. 1<br><br>1. }  <br>    }  <br>    }                                                  |
# Working with Strings in Java

## Creating strings

You can create a string in Java in two main ways:

**Using string literals**: This means writing the string directly inside double quotes.

|Description|Example|
|---|---|
|Create a string using string literal.|1. 1<br><br>1. String greeting = "Hello, World!";<br><br>Copied!Wrap Toggled!|

In this example, we created a string called greeting that contains "Hello, World!".

**Using the new Keyword**: This method involves using the new keyword to create a string object.

|Description|Example|
|---|---|
|Create a string using the new keyword.|1. 1<br><br>1. String message = new String("Hello, World!");<br><br>Copied!Wrap Toggled!|

Although this works, it's more common to use string literals because it's simpler.

---

## String length

To find out how many characters are in a string, you can use the length() method. This method tells you the total number of characters in the string.

|Description|Example|
|---|---|
|Create a string and use length() to get the number of characters.|1. 1<br><br>1. String text = "Java Programming";<br><br>Copied!Wrap Toggled!|
|Use the length() method to find the string length.|1. 1<br><br>1. int length = text.length();<br><br>Copied!Wrap Toggled!|
|Print the length of the string.|1. 1<br><br>1. System.out.println("Length of the string: " + length); // Output: 16<br><br>Copied!Wrap Toggled!|

Here, we created a string called text and then checked its length. The output tells us that there are 16 characters in "Java Programming".

---

## Accessing characters

If you want to look at individual characters in a string, you can use the charAt() method. This method allows you to get a character at a specific position in the string.

|Description|Example|
|---|---|
|Create a string and access a character using charAt().|1. 1<br><br>1. String word = "Java";<br><br>Copied!Wrap Toggled!|
|Access the first character of the string.|1. 1<br><br>1. char firstChar = word.charAt(0);<br><br>Copied!Wrap Toggled!|
|Print the first character of the string.|1. 1<br><br>1. System.out.println("First character: " + firstChar); // Output: J<br><br>Copied!Wrap Toggled!|

In this example, we accessed the first character of the string "Java". Remember that counting starts at 0, so charAt(0) gives us 'J'.

---

## Concatenating strings

Sometimes you might want to combine two or more strings together. You can do this easily using the + operator or the concat() method.

|Description|Example|
|---|---|
|Combine two strings using the + operator.|1. 1<br><br>1. String firstName = "John";<br><br>Copied!Wrap Toggled!|
|Combine two strings using the + operator.|1. 1<br><br>1. String lastName = "Doe";<br><br>Copied!Wrap Toggled!|
|Concatenate first and last names using the + operator.|1. 1<br><br>1. String fullName = firstName + " " + lastName;<br><br>Copied!Wrap Toggled!|
|Print the full name.|1. 1<br><br>1. System.out.println("Full Name: " + fullName); // Output: John Doe<br><br>Copied!Wrap Toggled!|

Here, we combined firstName and lastName using the + operator and added a space between them.

You can also use the concat() method:

|Description|Example|
|---|---|
|Combine strings using the concat() method.|1. 1<br><br>1. String anotherFullName = firstName.concat(" ").concat(lastName);<br><br>Copied!Wrap Toggled!|
|Print the concatenated string.|1. 1<br><br>1. System.out.println("Another Full Name: " + anotherFullName); // Output: John Doe<br><br>Copied!Wrap Toggled!|

---

## String comparison

When you want to check if two strings are the same, use the equals() method. This checks if both strings have identical content.

|Description|Example|
|---|---|
|Create three strings to compare.|1. 1<br><br>1. String str1 = "Hello";<br><br>Copied!Wrap Toggled!|
|Create another string to compare.|1. 1<br><br>1. String str2 = "Hello";<br><br>Copied!Wrap Toggled!|
|Create a third string to compare.|1. 1<br><br>1. String str3 = "World";<br><br>Copied!Wrap Toggled!|
|Check if str1 is equal to str2.|1. 1<br><br>1. boolean isEqual = str1.equals(str2);<br><br>Copied!Wrap Toggled!|
|Print comparison result.|1. 1<br><br>1. System.out.println("str1 equals str2: " + isEqual); // Output: true<br><br>Copied!Wrap Toggled!|
|Check if str1 is equal to str3.|1. 1<br><br>1. boolean isNotEqual = str1.equals(str3);<br><br>Copied!Wrap Toggled!|
|Print comparison result.|1. 1<br><br>1. System.out.println("str1 equals str3: " + isNotEqual); // Output: false<br><br>Copied!Wrap Toggled!|

In this example, isEqual returns true because both strings are "Hello". However, isNotEqual returns false since "Hello" and "World" are different.

---

## String immutability

One important thing to know about strings in Java is that they are immutable. This means that once a string is created, it cannot be changed. If you try to change it, you will actually create a new string instead.

|Description|Example|
|---|---|
|Create an original string.|1. 1<br><br>1. String original = "Hello";<br><br>Copied!Wrap Toggled!|
|Add to the string (creates a new string).|1. 1<br><br>1. original = original + " World";<br><br>Copied!Wrap Toggled!|
|Print the new string.|1. 1<br><br>1. System.out.println(original); // Output: Hello World<br><br>Copied!Wrap Toggled!|

In this case, we added "World" to original, but instead of changing the original string, we created a new string that combines both parts.

---

## Finding substrings

You may want to get a smaller part of a string. You can do this using the substring() method, which allows you to specify where to start and where to stop.

|Description|Example|
|---|---|
|Create a string and extract a substring.|1. 1<br><br>1. String phrase = "Java Programming";<br><br>Copied!Wrap Toggled!|
|Extract a substring from the string.|1. 1<br><br>1. String sub = phrase.substring(5, 16);<br><br>Copied!Wrap Toggled!|
|Print the extracted substring.|1. 1<br><br>1. System.out.println("Substring: " + sub); // Output: Programming<br><br>Copied!Wrap Toggled!|

In this example, we started at index 5 and went up to (but did not include) index 16 to extract "Programming".

---

## String methods

Java has many built-in methods for strings that help you manipulate and process them. Here are some useful ones:

**toUpperCase()**: This method converts all letters in a string to uppercase.

|Description|Example|
|---|---|
|Create a string.|1. 1<br><br>1. String text = "hello";<br><br>Copied!Wrap Toggled!|
|Convert the string to uppercase.|1. 1<br><br>1. System.out.println(text.toUpperCase()); // Output: HELLO<br><br>Copied!Wrap Toggled!|

**toLowerCase()**: This converts all letters in a string to lowercase.

|Description|Example|
|---|---|
|Create a string.|1. 1<br><br>1. String text = "WORLD";<br><br>Copied!Wrap Toggled!|
|Convert the string to lowercase.|1. 1<br><br>1. System.out.println(text.toLowerCase()); // Output: world<br><br>Copied!Wrap Toggled!|

**trim()**: This method removes any extra spaces at the beginning or end of a string.

|Description|Example|
|---|---|
|Create a string with extra spaces and trim it.|1. 1<br><br>1. String textWithSpaces = "   Hello   ";<br><br>Copied!Wrap Toggled!|
|Remove spaces from the string.|1. 1<br><br>1. System.out.println(textWithSpaces.trim()); // Output: Hello<br><br>Copied!Wrap Toggled!|

**replace()**: If you want to change all instances of one character or substring to another, use this method.

|Description|Example|
|---|---|
|Create a sentence and replace a word.|1. 1<br><br>1. String sentence = "I like cats.";<br><br>Copied!Wrap Toggled!|
|Replace a word in the sentence.|1. 1<br><br>1. String newSentence = sentence.replace("cats", "dogs");<br><br>Copied!Wrap Toggled!|
|Print the new sentence.|1. 1<br><br>1. System.out.println(newSentence); // Output: I like dogs.<br><br>Copied!Wrap Toggled!|

---

## Splitting strings

You can break a string into smaller pieces using the split() method. This is useful when you have data separated by commas or spaces.

|Description|Example|
|---|---|
|Create a CSV string and split it.|1. 1<br><br>1. String csv = "apple,banana,cherry";<br><br>Copied!Wrap Toggled!|
|Split the string at each comma.|1. 1<br><br>1. String[] fruits = csv.split(",");<br><br>Copied!Wrap Toggled!|
|Print each fruit in the array.|1. 1<br><br>1. for (String fruit : fruits) {  <br>        System.out.println(fruit);  <br>    }<br><br>Copied!Wrap Toggled!|
|Output:|1. 1<br><br>1. apple  <br>    banana  <br>    cherry<br><br>Copied!Wrap Toggled!|

---

## Joining strings

If you have an array of strings and want to combine them back into one single string, you can use the String.join() method.

|Description|Example|
|---|---|
|Create an array of strings.|1. 1<br><br>1. String[] colors = {"Red", "Green", "Blue"};<br><br>Copied!Wrap Toggled!|
|Join the strings with a separator.|1. 1<br><br>1. String joinedColors = String.join(", ", colors);<br><br>Copied!Wrap Toggled!|
|Print the joined string.|1. 1<br><br>1. System.out.println(joinedColors); // Output: Red, Green, Blue<br><br>Copied!Wrap Toggled!|
# Using Packages and Imports

## Creating a package

To create a package, you simply declare it at the top of your Java source file using the package keyword followed by the package name. For example:

|Description|Example|
|---|---|
|Declare a package at the top of the file.|1. 1<br><br>1. package com.example.myapp;<br><br>Copied!Wrap Toggled!|

In this example, com.example.myapp is the name of the package. It's common practice to use a reverse domain name as the package name to ensure uniqueness.

|Description|Example|
|---|---|
|Define a class inside the package.|1. 1<br><br>1. public class MyClass {  <br>        // Class code here  <br>    }<br><br>Copied!Wrap Toggled!|

---

## Creating and using a package

|Description|Example|
|---|---|
|Define a class inside the shapes package.|1. 1<br><br>1. package shapes;<br><br>Copied!Wrap Toggled!|
|Create the Circle class with a constructor and a method.|1. 1<br><br>1. public class Circle {  <br>        private double radius;  <br>      <br>        public Circle(double radius) {  <br>            this.radius = radius;  <br>        }  <br>      <br>        public double area() {  <br>            return Math.PI * radius * radius;  <br>        }  <br>    }<br><br>Copied!Wrap Toggled!|

To use this class in another Java file, you need to import it.

---

## Importing classes

To import a specific class from a package, use the following syntax:

|Description|Example|
|---|---|
|Import a specific class from a package.|1. 1<br><br>1. import package_name.ClassName;<br><br>Copied!Wrap Toggled!|

## Importing all classes from a package

You can also import all classes from a package using an asterisk (*).

|Description|Example|
|---|---|
|Import all classes from the shapes package.|1. 1<br><br>1. import shapes.*;<br><br>Copied!Wrap Toggled!|

This imports all classes in the shapes package, allowing you to use any class without needing to import them individually.
# Implementing Functions and Methods

## Function structure

|Description|Example|
|---|---|
|The structure of a function in Java.|1. 1<br><br>1. returnType functionName(parameter1Type parameter1, parameter2Type parameter2) {  <br>        // code to be executed  <br>        return value; // optional  <br>    }<br><br>Copied!Wrap Toggled!|

---

## Example of a Simple Function

Let's create a simple function that adds two numbers:

|Description|Example|
|---|---|
|Create a function that adds two numbers.|1. 1<br><br>1. public static int add(int a, int b) {  <br>        return a + b;  <br>    }<br><br>Copied!Wrap Toggled!|
|Call the add function in the main method and print the result.|1. 1<br><br>1. int sum = add(5, 3);  <br>    System.out.println("The sum is: " + sum);<br><br>Copied!Wrap Toggled!|

## Example of a simple method

Let's create a method within a class:

|Description|Example|
|---|---|
|Define a multiply method inside the Calculator class.|1. 1<br><br>1. public class Calculator {<br><br>Copied!Wrap Toggled!|
|The multiply method takes two integers and returns their product.|1. 1<br><br>1.  public int multiply(int x, int y) {<br><br>Copied!Wrap Toggled!|
|Close the multiply method.|1. 1<br><br>1.  return x * y;  <br>    }<br><br>Copied!Wrap Toggled!|
|Define the main method, which is the program’s entry point.|1. 1<br><br>1.  public static void main(String[] args) {<br><br>Copied!Wrap Toggled!|
|Create an instance of the Calculator class in the main method.|1. 1<br><br>1.  Calculator calc = new Calculator();<br><br>Copied!Wrap Toggled!|
|Call the multiply method with 4 and 5 and store the result.|1. 1<br><br>1.  int product = calc.multiply(4, 5);<br><br>Copied!Wrap Toggled!|
|Print the result to the screen.|1. 1<br><br>1.  System.out.println("The product is: " + product);<br><br>Copied!Wrap Toggled!|
|Close the main method and class.|1. 1<br><br>1.  }  <br>    }<br><br>Copied!Wrap Toggled!|

---

## Parameters and arguments

Parameters are the inputs to functions or methods, while arguments are the values passed when calling these functions or methods.

|Description|Example|
|---|---|
|Define a method with multiple parameters.|1. 1<br><br>1. public void greet(String name, int age) {  <br>        System.out.println("Hello " + name + ", you are " + age + " years old.");  <br>    }<br><br>Copied!Wrap Toggled!|
|Call the greet method with arguments in the main method.|1. 1<br><br>1. Greeting greeting = new Greeting();  <br>    greeting.greet("Alice", 30);<br><br>Copied!Wrap Toggled!|

---

## Return values

Functions and methods can return values or perform actions without returning anything.

|Description|Example|
|---|---|
|Define a method that returns a value.|1. 1<br><br>1. public double area(double length, double width) {  <br>        return length * width;  <br>    }<br><br>Copied!Wrap Toggled!|
|Call the area method and print the returned value.|1. 1<br><br>1. Rectangle rect = new Rectangle();  <br>    double area = rect.area(4.5, 3.0);  <br>    System.out.println("The area of the rectangle is: " + area);<br><br>Copied!Wrap Toggled!|

---

## Overloading methods

Java allows defining multiple methods with the same name but different parameters. This is known as method overloading.

|Description|Example|
|---|---|
|Define the `Display` class.|1. 1<br><br>1. public class Display {<br><br>Copied!Wrap Toggled!|
|Define an overloaded method that takes an `int`.|1. 1<br><br>1.  public void show(int number) {<br><br>Copied!Wrap Toggled!|
|Print the number.|1. 1<br><br>1.  System.out.println("Number: " + number);<br><br>Copied!Wrap Toggled!|
|Close the first method.|1. 1<br><br>1.  }<br><br>Copied!Wrap Toggled!|
|Define an overloaded method that takes a `String`.|1. 1<br><br>1.  public void show(String text) {<br><br>Copied!Wrap Toggled!|
|Print the text.|1. 1<br><br>1.  System.out.println("Text: " + text);<br><br>Copied!Wrap Toggled!|
|Close the second method.|1. 1<br><br>1.  }<br><br>Copied!Wrap Toggled!|
|Define the `main` method to call the overloaded methods.|1. 1<br><br>1.  public static void main(String[] args) {<br><br>Copied!Wrap Toggled!|
|Create a `Display` object.|1. 1<br><br>1.  Display display = new Display();<br><br>Copied!Wrap Toggled!|
|Call `show(int)` and `show(String)`.|1. 1<br><br>1.  display.show(10);<br><br>Copied!Wrap Toggled!|
|display.show("Hello World");||
|Close the `main` method.|1. 1<br><br>1. }  <br>    }<br><br>Copied!Wrap Toggled!|

---

## Scope of identifiers

The scope of an identifier refers to the part of the program where the identifier can be accessed.

|Description|Example|
|---|---|
|Local Scope: Identifiers are accessible only within the method or block.|1. 1<br><br>1. int x = 10; // x is local to this block<br><br>Copied!Wrap Toggled!|
|Instance Scope: Variables are accessible by all methods in the class.|1. 1<br><br>1. private int x; // x is accessible by all methods<br><br>Copied!Wrap Toggled!|
|Static Scope: Static variables belong to the class and are accessible throughout the class.|1. 1<br><br>1. private static int count;<br><br>Copied!Wrap Toggled!|

---

## Void methods

A void method does not return a value.

|Description|Example|
|---|---|
|Define a void method that prints a message.|1. 1<br><br>1. public void printMessage() {  <br>        System.out.println("Hello, World!");  <br>    }<br><br>Copied!Wrap Toggled!|

---

## Empty parameter lists

An empty parameter list means the method does not take any parameters.

|Description|Example|
|---|---|
|Define a method with an empty parameter list.|1. 1<br><br>1. public void show() {  <br>        System.out.println("No parameters here.");  <br>    }|