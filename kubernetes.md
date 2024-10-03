# Kubernetes (K8s)

## Defination
Kubernetes is detailed as `Manage a cluster of Linux containers as a single system to accelerate Dev and simplify Ops`. Kubernetes is an open source orchestration system for Docker containers. It handles scheduling onto nodes in a compute cluster and actively manages workloads to ensure that their state matches the users declared intentions.

az login
az account set --subscription "PMT-HPS-DIGITALFACTORY-NONPROD"
az aks get-credentials --resource-group df-aks-rg --name df-dev-aks-cluster --admin
az aks get-credentials --resource-group DF-qa-RG --name df-qa-aks-cluster --admin
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
docker login digitalfactory-docker-unstable-local.artifactory-na.honeywell.com
username:  pmt-devsecops-team        
Password:  Honeywell@2052

docker images
docker run -p 8888:80 940bfe98426b:DF-1000.1

docker run -e ASPNETCORE_ENVIRONMENT='Development' -e TENANT_ID='96ece526-9c7d-48b0-8daf-8b93c90a5d18' -e INSTANCE_NAME='https://login.microsoftonline.com/' -e RESOURCE_ID='api://d39cb913-ef82-48ba-9b16-81800731aa4b' -e AD_AUTH_REQUIRED='false' -e LOG_LEVEL='Information' -e AzureKeyVaultUrl='https://digitalfactory-keyvault.vault.azure.net/' -e COMPlus_EnableDiagnostics='0' -e RetryCounter='3' -e RetrySleepDurationInSeconds='3' -e EventsAllowedBeforeBreaking='5' -e BreakDurationInSeconds='20' -e ClientTimeoutInSeconds='10000' -e HandlerTimeoutInSeconds='20000' -p 8888:80 940bfe98426b
docker run --env-file .\env_file.txt -p 8888:80 940bfe98426b
docker network inspect bridge

docker-compose -f docker-compose.yml  build --no-cache df-configuration-service
docker tag df-configuration-service:latest "digitalfactory-docker-unstable-local.artifactory-na.honeywell.com/df-configuration-service:Dev892_22_09_05"
docker push "digitalfactory-docker-unstable-local.artifactory-na.honeywell.com/df-configuration-service:Dev892_22_09_05"
kubectl apply -f .\AKS\Services-Non-Prod\Dev\df-configuration-service.yaml

--------------------------------------------
dotnet dev-certs https --clean
dotnet dev-certs https --trust

---------------------
kc.bat start-dev
