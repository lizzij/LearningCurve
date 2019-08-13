# React
a declarativce, efficient, and flexible JS library for building UI, by using "components"

- React component class/type takes in props,and turns a view via render method
  - render returns a description of view (a React element)
  - components use state to remember things (constructor for state)
  
- Props

- State

  
- Controlled components
  - mutate the data
  - replace the data with a new changed copy
    - simple complex features (like "time travel", i.e. redo/undo)
    - detecting changes
    - determining when to re-render in react
  ```javascript
  var player = {score: 1, name: 'Jeff'};

  var newPlayer = Object.assign({}, player, {score: 2});
  // Now player is unchanged, but newPlayer is {score: 2, name: 'Jeff'}

  // Or if you are using object spread syntax proposal, you can write:
  // var newPlayer = {...player, score: 2}
  ```
  
- Function components
  - components that only contain a render method and don’t have their own state
  

---

  
- Arrow function (basically just lambda)
```javascript
(param1, param2, …, paramN) => { statements } 
(param1, param2, …, paramN) => expression
// equivalent to: => { return expression; }

// Parentheses are optional when there's only one parameter name:
(singleParam) => { statements }
singleParam => { statements }

// The parameter list for a function with no parameters should be written with a pair of parentheses.
() => { statements }

---
// Parenthesize the body of function to return an object literal expression:
params => ({foo: bar})

// Rest parameters and default parameters are supported
(param1, param2, ...rest) => { statements }
(param1 = defaultValue1, param2, …, paramN = defaultValueN) => { 
statements }

// Destructuring within the parameter list is also supported
var f = ([a, b] = [1, 2], {x: c} = {x: a + b}) => a + b + c;
f(); // 6
```

* rest parameters 
  * only the last parameter cna be a "rest parameter"
  
```javascript
function myFun(a, b, ...manyMoreArgs) {
  console.log("a", a); 
  console.log("b", b);
  console.log("manyMoreArgs", manyMoreArgs); 
}

myFun("one", "two", "three", "four", "five", "six");

// Console Output:
// a, one
// b, two
// manyMoreArgs, [three, four, five, six]
```

* (spread syntax)