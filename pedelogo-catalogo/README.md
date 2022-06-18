## Deploy in K8s

docker build -t saiwmon/pedelogo-catalogo:v1.0.0 -f pedelogo-catalogo/src/PedeLogo.Catalogo.Api/Dockerfile pedelogo-catalogo/

docker push saiwmon/pedelogo-catalogo:v1.0.0

### Deploy do Mongo
kubectl apply -f pedelogo-catalogo/k8s/mongodb/deployment.yml

kubectl apply -f pedelogo-catalogo/k8s/mongodb/service.yml

### Deploy da API em .Net
kubectl apply -f pedelogo-catalogo/k8s/api/deployment.yml

kubectl apply -f pedelogo-catalogo/k8s/api/service.yml

