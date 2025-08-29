#javascript #arrays #functional-programming #tdd
### map
`map` is one such function. It expects a `callback` as an argument, which is a fancy way to say “I want you to pass another function as an argument to my function”.
```JavaScript
function addOne(num) {
  return num + 1;
}
const arr = [1, 2, 3, 4, 5];
const mappedArr = arr.map(addOne);
console.log(mappedArr); // Outputs [2, 3, 4, 5, 6]
```

```JavaScript
const arr = [1, 2, 3, 4, 5];
const mappedArr = arr.map((num) => num + 1);
console.log(mappedArr); // Outputs [2, 3, 4, 5, 6]
```
Inline Declaration of addOne function

### filter
`filter` is somewhat similar to `map`. It still iterates over the array and applies the callback function on every item. However, instead of transforming the values in the array, it returns a new array where each item is only included _if_ the callback function returns `true` for it.

### reduce
- `reduce` itself also takes in an `initialValue` as an optional second argument (after the callback), which helps when we don’t want our initial value to be the first element in the array. For instance, if we wanted to sum all numbers in an array, we could call reduce without an `initialValue`, but if we wanted to sum all numbers in an array and add 10, we could use 10 as our `initialValue`.

```javascript
const arr = [1, 2, 3, 4, 5];
const productOfAllNums = arr.reduce((total, currentItem) => {
  return total * currentItem;
}, 1);
console.log(productOfAllNums); // Outputs 120;
console.log(arr); // Outputs [1, 2, 3, 4, 5]
```

In the above function, we:

- Pass in a callback function, which is `(total, currentItem) => total * currentItem`.
- Initialize total to `1` in the second argument.

So what `.reduce()` will do is go through every element in `arr` and apply the `callback` function to it. It updates `total` without actually changing the array itself. After it’s done, it returns `total`.


```JavaScript
let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
function sumOfTripledEvens(array) {
    return array
    .filter((num) => num % 2 == 0)
    .map((num) => num * 3)
    .reduce((total, currentItem) => total + currentItem);
}
```
Do the same thing
```JavaScript
function sumOfTripledEvens(array) {
  let sum = 0;
  for (let i = 0; i < array.length; i++) {
    // Step 1: If the element is an even number
    if (array[i] % 2 === 0) {
      // Step 2: Multiply this number by three
      const tripleEvenNumber = array[i] * 3;

      // Step 3: Add the new number to the total
      sum += tripleEvenNumber;
    }
  }
  return sum;
}
```

### Test-driven development (TDD)

[[09 Loops and Arrays  The Odin Project]]