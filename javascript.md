# JavaScript

### random
- check if is array
  ```JavaScript
  Array.isArray([1, 2, 3]);  // true
  Array.isArray({foo: 123}); // false
  Array.isArray('foobar');   // false
  Array.isArray(undefined);  // false
  ```

- reduce
  ```javascript
  array.reduce(function(total, currentValue, currentIndex, arr), initialValue)
  ```

- map
  ```javascript
  var new_array = arr.map(function callback(currentValue[, index[, array]]) {
      // Return element for new_array
  }[, thisArg])
  ```

- includes
  ```javascript
  arr.includes(valueToFind[, fromIndex])
  ```

- binds to type
  ```javascript
  function foo(e:MouseEvent) {
     ...
  }
  ```
  - `e` is binded to type `MouseEvent`

- renaming to avoid conflict in the scope
  ```javascript
  const Family = (
    { project, family, fields = [], showVariantDetails, compact, useFullWidth, disablePedigreeZoom,
      showFamilyPageLink, annotation, updateFamily: dispatchUpdateFamily,
    }) => {
    if (!family) {
      return <div>Family Not Found</div>
    }
  ```
  - the `:` in `updateFamily: dispatchUpdateFamily` is renaming `updateFamily` to `dispatchUpdateFamily` in the scope.

- spread syntax
  ```javascript
  function sum(x, y, z) {
    return x + y + z;
  }

  const numbers = [1, 2, 3];

  console.log(sum(...numbers));
  // expected output: 6

  console.log(sum.apply(null, numbers));
  // expected output: 6
  ```

- rest parameters (ellipsis)
  ```javascript
  function restParam(...restArgs){
    console.log(restArgs.length); // Logs the number of arguments passed
    console.log(restArgs[3]); // Logs the 4th argument
  }

  restParam(1,2,3,4,5);
  // Log would be as follows
  // 5
  // 4

  // 5 is the number of arguments
  // 4 is the 4th argument
  ```

- call back function
  - A function that is to be executed after another function has finished executing, i.e., higher-order functions

- `typeof ()`

- `reduce()`

- `let` and `const`

- print array of Object
  - `console.log(arr)`
  - `JSON.stringify(arr)`

- increment / decrement
  ```javascript
  // Increment
  let a = 1;M
  a++;
  ++a;
  // Decrement
  let b = 1;
  b--;
  --b;
  ```

- `.forEach()` vs `.map()`
  - `.forEach()`: in place
  - `.map()`: creates new array

- `Object.entries()` and `Object.values()`
  - `Object.entries()` returns an array of a given object's own enumerable string-keyed property [key, value] pairs, in the same order as that provided by a `for...in` loop
  - `Object.values()` returns an array of a given object's own enumerable property values, in the same order as that provided by a `for...in` loop
  - the difference: array of [key, value] pairs (`[Array(2), Array(2)...]`) vs array of value

- `Array.prototype.find()` returns the value of the first element in the provided array that satisfies the provided testing function

- `Array.prototype.some()` tests whether at least one element in the array passes the test implemented by the provided function. It returns a Boolean value

### ES6 shorthand
- if else `const ans = x > 10 ? 'greater than 10' : 'less or equal to 10'`
- short-circuit evaluation shorthand `const variable1 = variable2 || 'if variable2 is null'`
- decleration shorthand `let x, y, z=3`
- if true or not null `if (isPresent) ... ` and `if (!notTrue)`
- for loop shorthand `for (let fruit of fruits)` or `for (let index in fruits)`


### Working with JSON
- JSON: a string, a **data format** following JavaScript object syntax
- access in dot/bracket notation, can be used with index

  ```
  superHeroes.homeTown
  superHeroes['active']
  superHeroes['members'][1]['powers'][2]
  ```
- arrays as JSON
  - `[object0, object1, object2]`


### null vs undefined vs not defined in javascript
- nothing
  ```
  let nothing;
  typeof nothing === 'undefined';   // => true
  ```
  (btw, use `const` or `let` instead of `var`)
