# Django

### Python Debugger
```python3
import pdb
pdb.set_trace()
```
- commands
  - n (next): continue execution until return
  - s (step): stop at the first possible occasion
- print
  - list all the attributes of an object  `p dir(family)`
  - `type(family)`
  - `print repr(family)`
  - `print(family)`
  - `print(str(family))`
  - print an object/class (e.g.: user)   
    ```python
    from pprint import pprint
    print pprint(vars(user))
    ```

### Kibana & Elastic Search
change `debug` to `print` to get Json file in terminal

### Django ORM
Create an automated .py file in seqr/migrations
```shell
./manage.py makemigrations
./manage.py migrate
```

To undo a migration (e.g. undo `0060`)
- `./manage.py migrate seqr 0059` where `0059` is the previous migration
- remove `0060...` file
- run the above `makemigrations` and `migrate`

1-to-n relationship in model
```python
assigned_to = models.ForeignKey(User, null=True, on_delete=models.SET_NULL, related_name='assigned_families')
```
Here `related_name` attribute provide a reverse accessor to prevent duplicated backwards relationship

- https://docs.djangoproject.com/en/2.2/ref/models/fields/

### API
1. define api usage in corresponding `seqr/views/apis/*_api.py` file
2. test api in corresponding `seqr/views/apis/*_api_tests.py` file
3. update urls in `urls.py` (import and regex pattern)

### Model (database)
- a `Model` has `Fields` with `Field types` and `Field options`
- relationships
  - many-to-one relationships
  - many-to-many relationships
  - extra fields on many-to-many relationships
  - one-to-one relationship
