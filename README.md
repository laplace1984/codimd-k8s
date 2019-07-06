# Codimd on k8s (minikube)

## how to run

### create postgres pod
```bash
# at first, create volumes & volume claim.
kubectl apply -f postgres/postgres-storage.yaml
# create config (postgres pod use this configuration)
kubectl apply -f postgres/postgres-configmap.yaml
# create postgres pod by deployment
kubectl apply -f postgres/postgres-deployment.yaml
# finally, publish postgres port at node.
kubectl apply -f postgres/postgres-service.yaml
```

### create hackmd pod
```bash
# at first, create config (hackmd pod use this configuration)
kubectl apply -f hackmd-configmap.yaml
# create hackmd pod by deployment
kubectl apply -f hackmd-deployment.yaml
# finally, publish hackmd port at node.
kubectl apply -f hackmd-service.yaml
```
