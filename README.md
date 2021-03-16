```
docker-compose build
kubectl create secret generic digdag-secret --from-env-file=k8s/digdag-config/secrets.properties
kubectl apply -R -f k8s
```
