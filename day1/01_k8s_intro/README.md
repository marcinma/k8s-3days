# K8s


Do this first!

```sh
kubectl get nodes
kubectl config current-context
kubectl config get-contexts
kubectl get componentstatuses
kubectl get --raw '/readyz?verbose'
```

info:
```sh
kubectl cluster-info
```

Really verbose

```sh
kubectl -n kube-system get pods -v=9
```

Show pods labels
```sh
kubectl -n kube-system get pods --show-labels
```

Get pods by label

```sh
kubectl get pods -l app=myapp
kubectl -n kube-system get pods -l k8s-app=kube-dns
```

Get specific pod name

```sh
kubectl get pods -l app=myapp -o jsonpath='{.items[0].metadata.name}'
kubectl -n kube-system get pods -l k8s-app=kube-dns -o jsonpath='{.items[0].metadata.name}'
```

Gell all logs

```sh
kubectl logs -l app=myapp
kubectl -n kube-system logs  -l k8s-app=kube-dns
```

Get the manifest of a running pod
```sh
PO=$(kubectl -n kube-system get pods -l k8s-app=kube-dns -o jsonpath='{.items[0].metadata.name}')
kubectl get pods $PO -n kube-system -o yaml
```

```sh
kubectl -n kube-system get all
```

Get cluster events no older than 1h

```sh
kubectl get events
kubectl get events -o json
```
