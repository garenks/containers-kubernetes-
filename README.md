# Como rodar Apache e Nginx no Minikube - Passo a Passo Rápido

```bash
minikube start

docker build -t apache-custom:v2 -f ./trab/apache/arquivo-apache ./.trab/apache
docker build -t nginx-custom:v2 -f ./trab/nginx/arquivo-nginx ./.trab/nginx

minikube kubectl -- apply -f ./apache.yaml
minikube kubectl -- apply -f ./nginx.yaml

minikube kubectl -- get pods
minikube kubectl -- get services

minikube service --all

minikube stop

