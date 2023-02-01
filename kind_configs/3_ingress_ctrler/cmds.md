kind create cluster -n kind1 --config kind-conf.yml

# install nginx ingress
k apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml

# apply test deployment
k apply -f k8s-test-deployment.yml  
k port-forward service/test-service 5678:5678

# access the service :
curl localhost:5678

