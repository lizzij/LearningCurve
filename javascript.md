# JavaScript

### random
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
