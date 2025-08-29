#flashcards 
## Q: What are the two main types of quantifiers in FOPL?
?
## A: Universal (∀) and Existential (∃)

## Q: Translate “All UNCeans are intelligent” to FOPL.
?
## A: ∀x(UNCean(x) ⟶ Intelligent(x))

## Q: What’s the correct FOPL for “Some scholars are either diligent or wise”?
?
## A: ∃x(Scholar(x) ∧ (Diligent(x) ∨ Wise(x)))

## Q: What does it mean for a variable to be free?
?
## A: It’s not within the scope of any quantifier.

## Q: What’s the proper translation of “Not all youngsters are students”?
?
## A: ∃x(Youngster(x) ∧ ¬Student(x))

## Q: What rule allows removing a ∃ quantifier?
?
## A: Existential Instantiation (EI)

## Q: What is the scope of a quantifier?
?
## A: The part of the formula the quantifier applies to.

## Q: How do you read this: ∃x(Student(x) ∧ Intelligent(x))?
?
## A: Some student is intelligent.

## Q: When is ∀x P(x) true?
?
## A: When P(x) is true for all values in the universe.

## Q: What is resolution in FOPL used for?
?
## A: To prove validity by contradiction using CNF.
