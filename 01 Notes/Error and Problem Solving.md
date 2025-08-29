#coding #planning #software-design
## Things to ask before coding
Some of the questions you should answer at this stage of the process:

- Does your program have a user interface? What will it look like? What functionality will the interface have? Sketch this out on paper.
- What inputs will your program have? Will the user enter data or will you get input from somewhere else?
- What’s the desired output?
- Given your inputs, what are the steps necessary to return the desired output?
## Error
- A `ReferenceError` is thrown when one refers to a variable that is not declared and/or initialized within the current scope. In our case, the error message explains that the error has occurred because `c is not defined`.
- We covered reference errors in the first example in this lesson, but it’s important to remember that these arise because whatever variable you are trying to reference does not exist (within the current scope) - or it has been spelled incorrectly!
- These errors are thrown for a few different reasons:

Per MDN, a `TypeError` may be thrown when:
> - an operand or argument passed to a function is incompatible with the type expected by that operator or function;
> - or when attempting to modify a value that cannot be changed;
> - or when attempting to use a value in an inappropriate way.