#javascript #closures #functions #scope #encapsulation
**Summary:** Closures preserve lexical environment; used in factory functions to encapsulate state and enable scalable patterns.

-  Lexical Environment - consists of any local variables that were in scope at the time the closure was made.
  - **Factory Function** 
```javascript
function createUser (name) {
  const discordName = "@" + name;
  return { name, discordName };
}
```
### closure
- A function with preserved data
- Give you access to an outer function's scope from an inner function
- **Advantage** - state of variables in the outer scope are *"saved"* .
			- variables in the outer scope are considered *"private"*.
- Closures → Power factory functions → Enable encapsulation → Support scalable architecture