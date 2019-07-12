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