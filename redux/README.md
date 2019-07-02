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