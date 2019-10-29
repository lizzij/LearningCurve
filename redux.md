# Redux

## Basic Examples
- state stored in an object *tree* inside a single *store*
- emit an *action* to chnage state
- use *pure reducers* to specify actions
  - signature: (state, action) => state
  - should not mutate state, but return a *new* object if the state changes
- Actions, Reducers, Store
  - default return state

## Advanced Examples
- asynchronous API: request began, finish successfully, request failed

```javascript
const mapStateToProps = (state, ownProps) => ({
  // ... computed data from state and optionally ownProps
})

const mapDispatchToProps = {
  // ... normally is an object full of action creators
}

// `connect` returns a new function that accepts the component to wrap:
const connectToStore = connect(
  mapStateToProps,
  mapDispatchToProps
)
// and that function returns the connected, wrapper component:
const ConnectedComponent = connectToStore(Component)

// We normally do both in one step, like this:
connect(
  mapStateToProps,
  mapDispatchToProps
)(Component)
```

### Redux Chrome Extension
in configureStore.js line 21-43
```javascript
/* eslint-disable no-underscore-dangle */
const composeEnhancers = window.__REDUX_DEVTOOLS_EXTENSION_COMPOSE__ || compose
const enhancer = composeEnhancers(
  applyMiddleware(thunkMiddleware, persistStoreMiddleware),
)
/* eslint-enable */

/**
 * Initialize the Redux store
 * @param rootReducer
 * @param initialState
 * @returns {*}
 */
export const configureStore = (
  rootReducer = state => state,
  initialState = {},
) => {

  PERSISTING_STATE.forEach((key) => { initialState[key] = loadState(key) })

  console.log('Creating store with initial state:')
  console.log(initialState)

  return createStore(rootReducer, initialState, /* preloadedState, */ enhancer)
}

```

### Data Flow
A data life cycle:
- Call `store.dispatch(action)`
  - **Action** describes what happened
    ```javascript
    { type: 'ADD_TODO', text: 'Read the Redux docs.' }
    ```
- Redux store calls the **reducer** function
  - the store pass: the current state tree, and the action
    ```javascript
    // The current application state (list of todos and chosen filter)
    let previousState = {
      visibleTodoFilter: 'SHOW_ALL',
      todos: [
        {
          text: 'Read the docs.',
          complete: false
        }
      ]
    }

    // The action being performed (adding a todo)
    let action = {
      type: 'ADD_TODO',
      text: 'Understand the flow.'
    }

    // Your reducer returns the next application state
    let nextState = todoApp(previousState, action)
    ```
    - reducer is a pure function that only computes the next state
- Root reducer may combine the output of multiple reducers into a single state tree
  - using combined reducer `combineReducers()`
- Redux store saves the complete state tree returned by the root reducer
  - UI can be updated to reflect the new state

#### Selectors
- A “selector” is simply a function that accepts Redux state as an argument and returns data that is derived from that state.

#### Reducers

### Connect
Material
- https://react-redux.js.org/api/connect
- https://blog.logrocket.com/react-redux-connect-when-and-how-to-use-it-f2a1edab2013/
- [React documentation](https://reactjs.org/docs/getting-started.html)
- [Redux documentation](https://redux.js.org/)

Data
- props: read-only, allow a parent component to pass attribute to a child component
- state: local and encapsulated within the component and can change at any time in the component's lifecycle

Manage application state
- Redux: state container for js apps

React Redux Connect
- Presentational Components: how things look, not aware of Redux state, get data from props, might trigger callbacks passed to then via props
- Container Components: how thins work, aware of Redux state, created using React Redux and may dispatch Redux actions, subscribe to change in the Redux state

When to use `connect()`
1. Creating container components
2. Avoiding manual subscription to the Redux store

How to use `connect()`
- Invoke with base React component to convert it into a higher-orfer container component
  ```javascript
  const ContainerComponent = connect()(BaseComponent;
  ```
- Signature of the `connect()` function
  ```javascript
  connect([mapStateToProps], [mapDispatchToProps], [mergerProps], [options])
  ```

  - `mapStateToProps(state, [ownProps]) => stateProps`
    - a function that returns a plain object or another function
    - if no store updates: leave as `undefined` or `null`
    - the first pararmeter is the current state of the Redux store, the second parameter is an object of the props passed to the component (*optional*)

### State
- Functional (stateless) component
```javascript
const MyStatelessComponent = props => <div>{props.name}</div>;
```
  - state look like this:
  ```
  {
   type: 'div',
   props: {
     children: props.name,
   }
  ```
- Component class has a state, lifecycle hooks
```javascript
class MyComponentClass extends React.Component {
  render() {
    return <div>{this.props.name}</div>;
  }
}
```
- Comparison
  - functional components saves time and space complexity
  - functional is just for rendering, class component works with state

### Toggle with stateless


### Ducks: Redux Reducer Bundles
- associate `actions` and `reducer` without using `{actionTypes, actions, reducer}` tuples
- an example
  ```js
  // widgets.js

  // Actions
  const LOAD   = 'my-app/widgets/LOAD';
  const CREATE = 'my-app/widgets/CREATE';
  const UPDATE = 'my-app/widgets/UPDATE';
  const REMOVE = 'my-app/widgets/REMOVE';

  // Reducer
  export default function reducer(state = {}, action = {}) {
    switch (action.type) {
      // do reducer stuff
      default: return state;
    }
  }

  // Action Creators
  export function loadWidgets() {
    return { type: LOAD };
  }

  export function createWidget(widget) {
    return { type: CREATE, widget };
  }

  export function updateWidget(widget) {
    return { type: UPDATE, widget };
  }

  export function removeWidget(widget) {
    return { type: REMOVE, widget };
  }

  // side effects, only as applicable
  // e.g. thunks, epics, etc
  export function getWidget () {
    return dispatch => get('/widget').then(widget => dispatch(updateWidget(widget)))
  ```
