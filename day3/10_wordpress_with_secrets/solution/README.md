```sh
kubectl delete limitrange mem-limit-range
kubectl apply -f .
IP=$(kubectl get node k8s-playground-worker -o jsonpath='{.status.addresses[0].address}')
curl -v $IP:31519/wp-admin/install.php
```