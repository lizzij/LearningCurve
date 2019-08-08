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
```zsh
source ~/.bash_profile
./servctl set-env gcloud-prod-es  
pod_name=$(kubectl get pods -l name=es-client -o jsonpath="{.items[0].metadata.name}")  
kubectl port-forward $pod_name 9200
```
- https://github.com/macarthur-lab/seqr-private/blob/master/tunnel_to_production_data.md
- https://kubernetes.io/docs/tasks/tools/install-kubectl/
