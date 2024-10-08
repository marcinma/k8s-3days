```sh
kubectl apply -f 00-role.yml \
              -f 00-account.yml \
              -f 01-role-binding.yml \
              -f 02-traefik.yml \
              -f 02-traefik-services.yml

kubectl apply -f 03-whoami.yml \
              -f 03-whoami-services.yml \
              -f 04-whoami-ingress.yml
              
kubectl port-forward svc/traefik-dashboard-service 8080:8080
http://localhost:8080/dashboard/#/    
kubectl port-forward svc/traefik-web-service 8080:80
http://localhost:8080/dashboard/

kubectl apply -f 04-hello-ingress.yml
kubectl port-forward svc/traefik-web-service 8080:80
http://localhost:8080/hello
```              