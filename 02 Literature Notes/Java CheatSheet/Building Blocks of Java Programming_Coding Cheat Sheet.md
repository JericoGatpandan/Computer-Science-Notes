# Structuring Java Code and Comments
#Java 
## Types of comments

|Description|Code Example|
|---|---|
|A Java statement used to print text or other data to the standard output, typically the console.|1. 1<br><br>1. System.out.println("Hello, World!")<br><br>Copied!Wrap Toggled!|
|Use two forward slashes to precede a single line comment in Java|1. 1<br><br>1. // This is a single-line comment.</pre<br><br>Copied!Wrap Toggled!|
|All text after the two forward slash marks on this line is treated as a comment|1. 1<br><br>1. int number = 10; // This variable stores the number 10 <br><br>Copied!Wrap Toggled!|
|These comments start with `/*` and end with `*/`. They can span multiple lines.|1. 1<br><br>1. /* This is a multi-line comment It can be used to explain a block of code or provide detailed information <br><br>Copied!Wrap Toggled!|
|This also is a multiline comment. Multiline comments start with `/*` and end with `*/`. They can span multiple lines.|1. 1<br><br>1. */ int sum = 0;  <br>     */ This variable will hold the sum of numbers */. <br><br>Copied!Wrap Toggled!|
|The documentation comments start with `/*` and ends with `*/` . These comments are used for generating documentation using tools like Javadoc.|1. 1<br><br>1. /*  <br>     This method calculates the square of a number.    <br>     @param number The number to be squared    <br>     @return The square of the input number    <br>     */   <br>    public int square(int number) {   <br>     return number * number;   <br>     } <br><br>Copied!Wrap Toggled!|

## Creating a package

|Description|Code Example|
|---|---|
|To create a package, use the package keyword at the top of your Java source file.|1. 1<br><br>1. package com.example.myapp; // Declare a package   <br>    public class MyClass {   <br>     // Class code goes here  <br>     } <br><br>Copied!Wrap Toggled!|

## Folder structure for a package

|Description|Folder Structure Example|
|---|---|
|The folder structure on your filesystem should match the package declaration. For instance, if your package is com.example.myapp, your source file should be located in the following path example.|1. 1<br><br>1. /src  <br>    └── com   <br>    └── example   <br>    └──>└──>  <br>    └──>└── └──>myapp  <br>    └──>└── └──>└── MyClass.java <br><br>Copied!Wrap Toggled!|

## Class and Methods Structure

|Description|Code Example|
|---|---|
|In Java, a class is a blueprint for creating objects and can contain methods (functions) that define behaviors. For instance, the second line of this code displays the public class `library`, with methods like calculatePrice() or applyDiscount().|1. 1<br><br>1.  package com.example.library;    <br>     public class Library    <br>    {  <br>    private List <Book> books; // Private attribute to hold books    <br>     public Library()    <br>    {  <br>    books = new ArrayList<>(); // Initialize the list in the constructor   <br>     }   <br>    }public void addBook(Book book) {  <br>    books.add(book); // Method to add a book to the library   <br>    } <br }   <br>    <br><br>Copied!Wrap Toggled!|

## Creating methods

|Description|Code Example|
|---|---|
|Every Java application needs an entry point, which is typically a main method within a public class. In this code, the second line of code identifies the method named Main in the public class.|1. 1<br><br>1. package com.example.library;  <br>      <br>    public class Main {  <br>      <br>    public static void main(String[] args) {  <br>      <br>    Library library = new Library(); // Create an instance of Library  <br>      <br>    // Add books to the library  <br>     library.addBook(new Book("1984", "George Orwell"));  <br>    library.addBook(new Book("To Kill a Mockingbird", "Harper Lee"));  <br>      <br>    // Display all books  <br>     library.displayBooks();  <br>    }  <br>    }  <br>    <br><br>Copied!Wrap Toggled!|
|||

## Organizing source files in directories

|Description|Directory Structure|
|---|---|
|As your project grows, organizing your source files into directories can keep your code manageable. The following example illustrates typical Java organizaton.|1. 1<br><br>1.  MyProject/  <br>    └── src/     # Source code goes here  <br>    └── lib/     # External libraries/JARs  <br>    └── resources/     # Configuration files, images, and others   <br>    └── doc/     # Documentation  <br>    └── test/    # Test files  <br>    <br><br>Copied!Wrap Toggled!|
|||

## Using imports

|Description|Code Example|
|---|---|
|When you need to use classes from other packages, you need to import them at the top of your source file. These examples illustrate two examples of importing classes.|1. 1<br><br>1. import java.util.List;<br><br>Copied!Wrap Toggled!<br><br>1. 1<br><br>1. import java.util.ArrayList; // Importing classes from Java's standard library </pre<br><br>Copied!Wrap Toggled!|

# Exploring Data Types in Java

## Primitive data types

|Description|Code Example|
|---|---|
|Use the `byte` data type when you need to save memory in large arrays where the memory savings are critical, and the values are between -128 and 127.|1. 1<br><br>1. byte age = 25; // Age of a person <br><br>Copied!Wrap Toggled!|
|Use the `short` small integers data type for numbers from −32,768 to 32,767.|1. 1<br><br>1. short temperature = -5; // Temperature in degrees <br><br>Copied!Wrap Toggled!|
|Use the `int` integer data type to store whole numbers larger than what byte and short can hold. This is the most commonly used integer type.|1. 1<br><br>1. int population = 1000000; // Population of a city <br><br>Copied!Wrap Toggled!|
|Use the `long` data type when you need to store very large integer values that exceed the range of `int`.|1. 1<br><br>1. long distanceToMoon = 384400000L; // Distance in meters <br><br>Copied!Wrap Toggled!|
|Use the `float` when you need to store decimal numbers but do not require high precision (for example, up to 7 decimal places).|1. 1<br><br>1. float price = 19.99f; // Price of a product <br><br>Copied!Wrap Toggled!|
|Use the `double` data type when you need to store decimal numbers and require high precision (up to 15 decimal places).|1. 1<br><br>1.  double pi = 3.141592653589793; // Value of Pi <br><br>Copied!Wrap Toggled!|
|Use the `char` data type when you need to store a single character such as a single letter or an initial.|1. 1<br><br>1.  char initial = 'A'; // Initial of a person's name <br><br>Copied!Wrap Toggled!|
|Use `boolean` when you need to represent a true/false value. Boolean is often used for conditions and decisions.|1. 1<br><br>1. boolean isLoggedIn = true; // User login status <br><br>Copied!Wrap Toggled!|

## Reference data types

|Description|Code Example|
|---|---|
|A `string` data type is a sequence of characters. The `string` data type is very useful for handling text in your programs.|1. 1<br><br>1. String greeting = "Hello, World!"; <br><br>Copied!Wrap Toggled!|
|An `array` is a collection of multiple values stored under a single variable name. All the values in an array must be of the same type. Arrays are great for storing lists of items, like student scores or names. The following code defines an integer array type of scores that include 85, 90, 78, and 92.|1. 1<br><br>1. int[] scores = {85, 90, 78, 92};<br><br>Copied!Wrap Toggled!|
|The reference data type `class` is like a blueprint for creating objects. You can see the class identified in the first line of code.|1. 1<br><br>1. class Car {   <br>     String color;   <br>     int year;   <br>     void displayInfo() {  <br>     System.out.println("Color: " + color + ", Year: " + year);   <br>     }    <br>    }  <br><br>Copied!Wrap Toggled!|
|Objects are classes that contain both data and functions. In this code `Car myCar = new Car();` is the object.|1. 1<br><br>1. public class Main {   <br>     public static void main(String[] args) {   <br>        Car myCar = new Car();  <br>         myCar.color = "Red";  <br>         myCar.year = 2026;  <br>         myCar.displayInfo(); // Output: Color: Red, Year: 2026  <br>       }  <br>    }<br><br>Copied!Wrap Toggled!|
|When you create an interface, you only declare the methods without providing their actual code. All methods in an interface are empty by default. Here's an example of an interface called MyInterfaceClass with three methods.|1. 1<br><br>1. // The interface class   <br>    interface MyInterfaceClass {  <br>         void methodExampleOne();  <br>         void methodExampleTwo();  <br>         void methodExampleThree();  <br>    }<br><br>Copied!Wrap Toggled!|
|An `enum` is a special data type that defines a list of named values. An enum is useful for representing fixed sets of options, such as days of the week or colors.|1. 1<br><br>1. enum DaysOfWeek {  <br>    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY;  <br>    }<br><br>Copied!Wrap Toggled!|

# Introduction to Operators in Java

## Arithemtic operators

The following operators perform basic mathematical functions.  
In these code examples `int a = 10;` and `int b = 5;`

|Description|Example|
|---|---|
|The plus symbol `+` performs addition operations.|1. 1<br><br>1. System.out.println("Addition: " + (a + b));         // 15<br><br>Copied!Wrap Toggled!|
|The minus symbol `-` performs subtraction operations.|1. 1<br><br>1. System.out.println("Subtraction: " + (a - b));      // 5<br><br>Copied!Wrap Toggled!|
|The asterisk symbol `*` performs multiplication operations.|1. 1<br><br>1. System.out.println("Multiplication: " + (a * b));   // 50<br><br>Copied!Wrap Toggled!|
|The division symbol `/` performs division operations.|1. 1<br><br>1. System.out.println("Division: " + (a / b));          // 2<br><br>Copied!Wrap Toggled!|
|The percentage symbol `%` performs modulus (percentage) operations.|1. 1<br><br>1. ystem.out.println("Modulus: " + (a % b));           // 0<br><br>Copied!Wrap Toggled!|

## Relational operators

You use relational operators to compare two values. These operators return a boolean result (true or false).

In the following examples `int a = 10;` and `int b = 5;`.

|Description|Example|
|---|---|
|The double equal symbols `==` check for equality.|1. 1<br><br>1. System.out.println("Is a equal to b? " + (a == b));      // false<br><br>Copied!Wrap Toggled!|
|The exclamation point and equal symbol together `!=` check for a not equal result.|1. 1<br><br>1. System.out.println("Is a not equal to b? " + (a != b));  // true <br><br>Copied!Wrap Toggled!|
|The greater than symbol `>` checks for the greater than result.|1. 1<br><br>1. System.out.println("Is a greater than b? " + (a > b));   // true 0<br><br>Copied!Wrap Toggled!|
|The less than symbol `<` checks if the result for a less than state.|1. 1<br><br>1. System.out.println("Is a less than  b? " + (a < b)); // false<br><br>Copied!Wrap Toggled!|
|The greater than equal symbols `>=`  compares the values to check for a greater than or equal to result.|1. 1<br><br>1. System.out.println("Is a greater than or equal to b? " + (a >= b)); // true <br><br>Copied!Wrap Toggled!|
|The less than equal symbols `<=`  compares the values to check for a less than or equal to result.|1. 1<br><br>1. System.out.println("Is a less than or equal to b? " + (a <= b)); // false<br><br>Copied!Wrap Toggled!|

## Logical operators

You can use logical operators to combine boolean expressions. The following code examples use `boolean x = true;` and `boolean y = false;`.

| Description                                                                                                                                                                      | Example                                                                  |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| The double ampersands `&&` combines two boolean expressions (both must be true).                                                                                                 | 1. 1<br><br>1. if (a > b && b < c) { ... }  <br><br>Copied!Wrap Toggled! |
| The double vertical bar symbols `\|` used with boolean values always evaluates both expressions, even if the first one is true.                                                  | 1. 1<br><br>1. if (a > b \| b < c) { ... }<br><br>Copied!Wrap Toggled!   |
| The single exclamation point symbol `!` operator in Java is the logical NOT operator. This operator is used to negate a boolean expression, meaning it reverses the truth value. | 1. 1<br><br>1. if (!(a > b)) { ... } <br><br>Copied!Wrap Toggled!        |

# Using Advanced Operators in Java

## Assignment operators

You can use assignment operators to assign values to a variable.

|Description|Example|
|---|---|
|The single equal symbol `=` assigns the right operand to left|1. 1<br><br>1. a = 10 <br><br>Copied!Wrap Toggled!|
|The plus sign and equal symbols combined `+=` adds and assigns values to variables|1. 1<br><br>1. a += 5<br><br>Copied!Wrap Toggled!|
|The minus sign and equal symbols combined `-=` subtracts values to variables|1. 1<br><br>1. a -= 2<br><br>Copied!Wrap Toggled!|
|The asterisk sign and equal symbols combined `*=` multipies and assigns values to variables|1. 1<br><br>1. a *= 3<br><br>Copied!Wrap Toggled!|
|The forward slash sign and equal symbols combined `/=` divides and assigns values to variables|1. 1<br><br>1. a /= 2<br><br>Copied!Wrap Toggled!|
|The percentage and equal symbols combined `%=` take the modulus (percentage) and assigns values to the variables|1. 1<br><br>1. a %= 4<br><br>Copied!Wrap Toggled!|

## Unary operators

A unary operation is a mathematical or programming operation that uses only one operand or input. Developers use unary operations to manipulate data and perform calculations. You would use the following assignment operators to assign values to variables.

|Description|Example|
|---|---|
|Use the plus symbol to indicate a positive value.|1. 1<br><br>1. int positive = +a; <br><br>Copied!Wrap Toggled!<br><br>  <br><br>1. 1<br><br>1. int a = 10;   <br>    System.out.println("Unary plus: " + (+a));   // 10 <br><br>Copied!Wrap Toggled!|
|||

## Ternary operators

Ternary operators are a shorthand form of the conditional statement. They can use three operands.

| Description                                                                                                                    | Example                                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ternary operators uses the Syntax: condition ? expression1 : expression2;. In the following code, `int max = (a > b) ? a : b;` | 1. 1<br><br>1. int a = 10;  <br>    int b = 20;  <br>    int max = (a > b) ? a : b; // If a is greater than b, assign a; otherwise assign b  <br>    System.out.println("Maximum value is: " + max); // 20 <br><br>Copied!Wrap Toggled! |

# Working with Arrays

## Declaring an array

|Description|Example|
|---|---|
|To declare an array in Java, you use the following syntax: `dataType[] arrayName;`. The following doce displays the data type of int and creates an array named `numbers`.|1. 1<br><br>1. int[] numbers;<br><br>Copied!Wrap Toggled!|

## Initializing an array

After you declare an array, you need to initialize the array to allocate memory for it.

|Description|Example|
|---|---|
|These code samples display three methods used to create an array of 5 integers. You can initialize an array using the `new` keyword. You can also declare and initialize an array in a single line. Alternatively, you can create an array and directly assign values using curly braces.|1. 1<br><br>1. numbers = new int[5]; <br><br>Copied!Wrap Toggled!<br><br>  <br><br>1. 1<br><br>1. int[] numbers = new int[5];<br><br>Copied!Wrap Toggled!<br><br>  <br><br>1. 1<br><br>1. int[] numbers = {1, 2, 3, 4, 5};<br><br>Copied!Wrap Toggled!|

## Accessing an array

You can access individual elements in an array by specifying the index inside square brackets.

|Description|Example|
|---|---|
|Remember that indices start at zero. Here are two examples:|1. 1<br><br>1. System.out.println(numbers[0]);System.out.println(numbers[0]); // Outputs: 1<br><br>Copied!Wrap Toggled!<br><br>1. 1<br><br>1. System.out.println(numbers[4]); // Outputs: 5<br><br>Copied!Wrap Toggled!|

## Modifying array elements

|Description|Example|
|---|---|
|Modify the array element value by accessing it within its index.|1. 1<br><br>1. numbers[2] = 10; // Changing the third element to 10<br><br>Copied!Wrap Toggled!<br><br>  <br><br>1. 1<br><br>1. System.out.println(numbers[2]);>System.out.println(numbers[2]); // Outputs: 10<br><br>Copied!Wrap Toggled!|

## Verify the array length

|Description|Example|
|---|---|
|Verify the array length by using the length property|1. 1<br><br>1. System.out.println("The length of the array is: " + numbers.length);<br><br>Copied!Wrap Toggled!|

## Using a for loop to iterate through an array

|Description|Example|
|---|---|
|You can use a `for` loop for to iterarate through and array. Here's an example that prints all elements in the numbers array. The `for` loop includes this code `for (int i = 0` in the following code snippet.|1. 1<br><br>1. for (int i = 0; i < numbers.length; i++) {  <br>          System.out.println(numbers[i]);  <br>    }<br><br>Copied!Wrap Toggled!|

## Using a for each loop to iterate through an array

|Description|Example|
|---|---|
|You can also use the enhanced `for` loop, known as the "for-each" loop. The enhanced `for each` loop code include this portion, `for (int`  of the following code snippet.|1. 1<br><br>1.  for (int number : numbers) {  <br>         System.out.println(number);  <br>    }<br><br>Copied!Wrap Toggled!|

## Declare and intialize a multidimensional array

Java supports multi-dimensional arrays, which are essentially arrays of arrays. The most common type is the two-dimensional array.

|Description|Example|
|---|---|
|Here's how to declare and initialize a 2D array. You will declare the integer data type and create the matrix array.|1. 1<br><br>1.  int[][] matrix = {  <br>         {1,{1, 2, 3},  <br>         {4, 5, 6},  <br>        {7, 8, 9}  <br>    }; <br><br>Copied!Wrap Toggled!|
|You can access elements in a two-dimensional array by specifying both indices, which are shown in this code inside of the square brackets.|1. 1<br><br>1. System.out.println(matrix[0][1]); // Outputs: 2<br><br>Copied!Wrap Toggled!|

Iterating Through a 2D Array

| Description                                                            | Example                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| You can use nested loops to iterate through all elements of a 2D array | 1. 1<br><br>1. for (int i = 0; i < matrix.length; i++) {  <br>         for (int j = 0; j <    matrix[i].length; j++) {  <br>             System.out.print(matrix[i][j]>System.out.print(matrix[i][j] + " ");  <br>    }   <br>         System.out.println(); // Move to the next line after each row |