```
docker-compose build
kubectl create secret generic digdag-secret --from-env-file=k8s/digdag-config/secrets.properties
kubectl apply -f k8s/digdag-config
kubectl apply -f k8s/db
kubectl apply -f k8s/digdag-master
```
