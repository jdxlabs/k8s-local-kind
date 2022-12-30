kind create cluster -n kind1 --config kind-conf.yml

k create deployment nginx --image=nginx --port=80
k create service nodeport nginx --tcp=80:80 --node-port=30000

# access the service :
curl localhost:30000
