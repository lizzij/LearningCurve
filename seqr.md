# seqr

### server side
(in bash `exec bash`)
- `./manage.py runserver`  
- `./manage.py test -p '*tests.py' seqr`
- `http://localhost:8000  

### client side
- `cd /seqr/ui`
- `npm run start`
- `npm run test`
- http://localhost:3000

### elasticsearch
- In the top-level seqr code directory, run:  
```bash
source ~/.bash_profile
./servctl set-env gcloud-prod-es  
pod_name=$(kubectl get pods -l name=es-client -o jsonpath="{.items[0].metadata.name}")  
kubectl port-forward $pod_name 9200
```
- https://github.com/macarthur-lab/seqr-private/blob/master/tunnel_to_production_data.md
- https://kubernetes.io/docs/tasks/tools/install-kubectl/
- update elasticsearch index
  - start mongoDB `brew services start mongodb`
  - go to staff/elasticsearch_status [page](https://seqr.broadinstitute.org/staff/elasticsearch_status)

### db migration
- to create an automated .py file in seqr/migrations
```shell
./manage.py makemigrations
./manage.py migrate
```

- to undo a migration (e.g. undo `0060`)
- `./manage.py migrate seqr 0059` where `0059` is the previous migration
- remove `0060...` file
- run the above `makemigrations` and `migrate`

### redis
- `./deploy/install_local.step5.install_redis.sh` install and have it running
- check if Redis is working `redis-cli ping`
