```sh
kubectl delete limitrange mem-limit-range
kubectl apply -f .
kubectl port-forward svc/wordpress-service 8181:80
go 127.0.0.1:8181
# OR:
IP=$(kubectl get node k8s-playground-worker -o jsonpath='{.status.addresses[0].address}')
curl -v $IP:31519/wp-admin/install.php
```