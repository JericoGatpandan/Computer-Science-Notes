#javascript #modules #esm #imports #exports
### Named Imports
```javascript
// one.js
const greeting = "Hello, Odinite!";
const farewell = "Bye bye, Odinite!";
export { greeting, farewell };
```
```javascript
// two.js
import { greeting, farewell } from "./one.js";

console.log(greeting); // "Hello, Odinite!"
console.log(farewell); // "Bye bye, Odinite!"
```

### Default imports

In ESM, no export = no access. Even the browser won’t leak module variables into `window`.

> If you want to export a single main value from a module, use a **default export**.  
> If you want to export multiple things from a module, use **named exports**.

```html
<script type = "module" src="script.js"></script>
```
