# Kubernetes (K8s)

## Defination
Kubernetes is detailed as `Manage a cluster of Linux containers as a single system to accelerate Dev and simplify Ops`. Kubernetes is an open source orchestration system for Docker containers. It handles scheduling onto nodes in a compute cluster and actively manages workloads to ensure that their state matches the users declared intentions.

az login
az account set --subscription "subscription name"
az aks get-credentials --resource-group resource-group-name --name clustername --admin

kubectl get po -n df-dev-services

kubelogin convert-kubeconfig
kubectl config get-contexts
kubectl config use-context <docker-desktop>
kubectl logs --namespace df-qa-services df-alert-management-service-5f8498d7b4-bgw8w
kubectl -n df-qa-services exec df-machine-kpi-service-69bb9d96bb-8rsfp -- env
kubectl get po -n df-dev-services df-configuration-service-7bf899f5cb-hgx5f -o yaml // change to json
kubectl get po -n df-dev-services -l app=df-configuration-service -o yaml // change to json
kubectl logs -n df-dev-services -l app=df-configuration-service

kubectl get ing -n df-qa-services //ingress
kubectl get ing -n df-qa-services -o yaml
--------------------------------------------
docker login 


docker images
docker run -p 8888:80 940bfe98426b:DF-1000.1

docker run -e ASPNETCORE_ENVIRONMENT='Development' -p 8888:80 940bfe98426b
docker run --env-file .\env_file.txt -p 8888:80 940bfe98426b
docker network inspect bridge

docker-compose -f docker-compose.yml  build --no-cache df-configuration-service
docker tag df-configuration-service:latest "digitalfactory-docker-unstable-local.artifactory-na.localhost.com/df-configuration-service:Dev892_22_09_05"
docker push "digitalfactory-docker-unstable-local.artifactory-na.localhost.com/df-configuration-service:Dev892_22_09_05"
kubectl apply -f .\AKS\Services-Non-Prod\Dev\df-configuration-service.yaml

--------------------------------------------
dotnet dev-certs https --clean
dotnet dev-certs https --trust

---------------------
kc.bat start-dev
