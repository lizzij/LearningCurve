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

### Kibana & Elastic Search
change `debug` to `print` to get Json file in terminal 

### Django ORM
Create an automated .py file in seqr/migrations
```shell
./manage.py makemigration
./manage.py migrate
```

1-to-n relationship in model
```python
assigned_to = models.ForeignKey(User, null=True, on_delete=models.SET_NULL, related_name='assigned_families')
```
Here `related_name` attribute provide a reverse accessor to prevent duplicated backwards relationship

### API
1. define api usage in corresponding `seqr/views/apis/*_api.py` file
2. test api in corresponding `seqr/views/apis/*_api_tests.py` file
3. update urls in `urls.py` (import and regex pattern)