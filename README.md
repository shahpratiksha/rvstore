# rvstore
Trying out kubernetes logic with a sample rvstore


```
cd kubernetes
kubectl apply -f . 
```

This will start up a whole bunch of services and pods 

View dashboard https://github.com/kubernetes/dashboard

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v1.10.1/src/deploy/recommended/kubernetes-dashboard.yaml
kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep admin-user | awk '{print $1}')
```
get the token from above, and run: 

```
kubectl proxy
```

go to:
http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/overview?namespace=default

and paste the token you obtained


In order to stop the application, 

```
cd kubernetes
kubectl delete -f .
```

misc commands: 
```
kubectl get all
kubectl get configmap
kubectl get jobs
kubectl logs pod/hello-world-pod
kubectly describe configmap
```
