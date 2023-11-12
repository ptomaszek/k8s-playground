App:
```
mvn package -f app/pom.xml
```

Docker plain:
```shell
docker build -t app -f infrastructure/docker/Dockerfile .
docker run  -p 8080:8080 app
```

Docker by Kaniko:
```shell
minikube start
minikube mount $(pwd):/k8s-playground

kubectl apply -f infrastructure/k8s/kaniko/pod.yaml --force

kubectl describe po kaniko
kubectl logs -f kaniko
```
