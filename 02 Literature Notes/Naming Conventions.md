#javascript #clean-code
#### Naming Variables and Functions
```JavaScript
// Preferable
const numberOfThings = 10;
const myName = "Thor";
const selected = true;

// Not preferable (these start with verbs, could be confused for functions)
const getCount = 10;
const showNorseGods = ["Odin", "Thor", "Loki"];

// Preferable
function getCount() {
  return numberOfThings;
}

// Not preferable (myName doesn't represent some kind of action)
function myName() {
  return "Thor";
}
```

- Variables should preferably begin with a noun or an adjective (that is, a noun phrase), as they typically represent “things”, whether that thing is a string, a number etc. Functions represent actions so ideally begin with a verb.
- **camelCase**
```JavaScript
const ONE_HOUR = 3600000; // Can even write as 60 * 60 * 1000;

setTimeout(stopTimer, ONE_HOUR);
```
- You might wonder why this variable is declared with all caps when we recommended camelCase earlier. This is a convention to be used when the programmer is absolutely sure that the variable is _truly_ a constant, especially if it represents some kind of concept like a specific duration of time. We know that the milliseconds in an hour will never change, so it’s appropriate here. Remember, this is only a convention. Not everyone will necessarily do things the same way.

```JavaScript
// Extracts text inside square brackets (excluding the brackets)
function extractText(s) {
  return s.substring(s.indexOf("[") + 1, s.indexOf("]"));
}
```

> Great code comes from experience. Experience comes from not-so-great code.


[[10 Clean Code  The Odin Project]]
