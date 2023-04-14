Based on [this](https://www.youtube.com/watch?v=s_o8dwzRlu4) tutorial.

To apply everything:

```shell
kubectl apply mongo-config.yaml

kubectl apply mongo-secret.yaml

kubectl apply mongo.yaml

kubectl webapp.yaml
```

To list:
```shell
kubectl get all

kubectl get pods

kubectl get configmap

kubectl get secret
```

Get node information:

```shell
kubectl get node

kubectl get node -o wide
```

To get logs inside the pod:

```shell
kubectl logs webapp-deployment-65d4754f9d-9szdb 

# streaming
kubectl logs webapp-deployment-65d4754f9d-9szdb -f     
```
