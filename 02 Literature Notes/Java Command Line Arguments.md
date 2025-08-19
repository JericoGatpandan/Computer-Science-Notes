#java #cli #input #arrays
First, command line arguments are code that you provide after `java <classname>` when you run a Java program. Command line arguements are useful ways you can provide user input to the program.

1. Click the **Open ArrayAcess.java in IDE** button to open the file for editing if the IDE environment is not already open.

2. Read each statement in the following program to understand how the method considers the main method's input parameters. Paste the following content in `ArrayAccess.java`.
```
public class ArrayAccess {
```

`int num_args = s.length;` - Creates a variable named `num_args` and stores the value of the length of the array of command line arguments in it.

3. Compile the Java program, specifying the destination directory using the `classes` directory that you previously created.
```
javac -d classes src/ArrayAccess.java
```
4. Now run the Java program.
```
java ArrayAccess
```

You will not see any output as the code did not pass command line arguments.

4. Run the Java program again. However, with this run include the following command line arguments when running the program.
```
java ArrayAccess first second third fourth fifth
```

Here `first`,`second`,`third`,`fourth` and `fifth` are command line arguments.

You will see the following output:

```
the length of the array is 5
```