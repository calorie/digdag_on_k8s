```
docker-compose build
helm install prometheus-operator prometheus-community/kube-prometheus-stack -f helm-values/prometheus-operator.yml
helm install prometheus-adapter prometheus-community/prometheus-adapter -f helm-values/prometheus-adapter.yml
kubectl create secret generic digdag-secret --from-env-file=k8s/digdag-secret/secrets.properties
kubectl apply -R -f k8s
```
