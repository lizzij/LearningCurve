# Redux

## Basic Examples
- state stored in an object *tree* inside a single *store*
- emit an *action* to chnage state
- use *pure reducers* to specify actions
  - signature: (state, action) => state
  - should not mutate state, but return a *new* object if the state changes

