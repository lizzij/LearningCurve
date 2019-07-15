# seqr

### server side
(in bash `exec bash`)
- `./manage.py runserver `  
- `./manage.py test -p '*tests.py' seqr`  
- `http://localhost:8000  

### client side 
- `cd /seqr/ui`
- `npm run start`
- `npm run test`
- http://localhost:3000

### elasticsearch 
- In the top-level seqr code directory, run:  
```zsh
./servctl set-env gcloud-prod-es  
pod_name=$(kubectl get pods -l name=es-client -o jsonpath="{.items[0].metadata.name}")  
kubectl port-forward $pod_name 9200
```
- https://github.com/macarthur-lab/seqr-private/blob/master/tunnel_to_production_data.md
- https://kubernetes.io/docs/tasks/tools/install-kubectl/

### orm to json 
```javascript
/**
 * Factory function that creates a reducer for managing a state object that looks like:
 *
 * { id1: { key1: valueA, key2: valueB, key3: valueC },
 *   id2: { key1: valueI, key2: valueJ, key3: valueK },
 *   id3: ...
 * }
 *
 * This state object is analogous to a database table, where the contained objects represent table
 * rows and have identical sets of keys but different values, so that each key can be thought of as
 * a column in the table.
 *
 * This reducer supports a single action type that can be used to transform the underlying state
 * in several ways:
 *    - adding new objects by id
 *    - deleting objects by id
 *    - updating the values within one or more existing objects by id
 *
 * As an example, the reducer can be created as follows:
 *
 *      const tableRowReducer = createObjectsByIdReducer('UPDATE_TABLE_X')
 *
 * Here, the 'UPDATE_TABLE_X' argument specifies the action type that will later be dispatched
 * to perform modifications. For example, the action below will change some of the values and also
 * both delete some ids and add some new ids:
 *
 * dispatch({
 *   type: 'UPDATE_TABLE_X',
 *   updatesById: {
 *     id1: { key2: valueM },                                 // update key2 value in object with id1
 *     idNew: { key1: valueX, key2: valueY, key3: valueZ },   // add new object and id
 *     id2: null,                                             // delete id2
 *   }
 *  })
 *
 * The resulting state after this action would look like:
 *
 * { id1: { key1: valueA, key2: valueM, key3: valueC },
 *   idNew: { key1: valueX, key2: valueY, key3: valueZ },
 *   id3: ...
 * }
 *
 * @param updateStateActionId (string) action.type that will later be used to update the state object.
 */
```