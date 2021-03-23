```
docker-compose build
helmfile apply
kubectl create secret generic digdag-secret --from-env-file=k8s/digdag-secret/secrets.properties
kubectl apply -R -f k8s
```
