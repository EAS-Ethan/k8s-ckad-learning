# k8s-ckad-learning commands

``` kubectl create -f [YAML_FILE_PATH] ```

# Pods

view pods: ``` kubectl get pods ```

extect pod into file: ``` kubectl get pod [POD_NAME] -o yaml > [YAML_FILE_PATH] ```

edit pod: ``` kubectl edit pod [POD_NAME] ```

delete pod: ``` kubectl delete pod [POD_NAME] ```

describe pods: ``` kubectl describe pod ```

describe a pod ``` kubectl describe pod [POD_NAME] ```

get pods by label: ``` kubectl get pods --selector [KEY]=[VALUE] ```

# ReplicaControllers & ReplicaSets

list replication controllers: ``` kubectl get replicationcontroller ```

list replica sets: ``` kubectl get replicaset ```

updated replicas command to replace replica set : ``` kubectl replace -f [YAML_FILE_PATH]  ```

scale replicas in replicaset with file : ``` kubectl scale --replicas=[NUMBER] [YAML_FILE_PATH] ```

scale replicas in replicaset with replicaset namew : ``` kubectl scale --replicas=[NUMBER] replicaset [REPLICASET_NAME] ```

delete replica set: ``` kubectl delete replicaset [REPLICASET_NAME] ```

delete replication controller: ``` kubectl delete replicationcontroller [REPLICASET_NAME] ```

# Deployments

get deployments: ``` kubectl get deployments ```

delete deployment: ``` kubectl delete deployment [DEPLOYMENT_NAME] ```

create deployment: ``` kubectl create deployment [NAME] --image=[IMAGE] --replicas=[NUMBER] ```

update deployment: ```kubectl apply -f [YAML_FILE_PATH] ```

update image in deployment: ```kubectl set image [RESOURCE_TYPE] [RESOURCE_NAME] \ [EXISTING_IMAGE]=[NEW_IMAGE ```]

# Namespaces

delete namespace: ``` kubectl delete namespace [NAMESPACE_NAME] ```

create namespace: ``` kubectl create namespace [NAME] ```

get in namspace pod example: ``` kubctl get pods --namespace [NAMESPACE_NAME] ```

view pods in all namespaces example: ``` kubectl get pods --all-namespaces ```

chnage current context for namespace view: ``` kubectl config set-context $(kubectl config current-context) --namespace [NAMESPACE_NAME] ```

# Configmaps

view config maps: ``` kubectl get configmap ```

descibe config maps: ``` kubectl describe configmap ```

delete config map: ``` kubectl delete configmap [CONFIGMAP_NAME] ```

# Secrets

view secrets: ``` kubectl get secrets ```

describe secrets: ``` kubectl describe secrets ```

describe a secret: ``` kubectl describe secret [SECRET_NAME] ```

view secret in yaml format: ``` kubectl get secret [SECRET_NAME] -o yaml ```

creat secret without file: ``` kubectl create secret generic [NAME] --from-literal=[KEY]=[VALUE] --from-literal=[KEY]=[VALUE] --from-literal=[KEY]=[VALUE] ```

turn words into hashed unreadbale code: ``` echo -n "[WORD]" | base64 ```

decode hashed unreadble codes to be readable: ``` echo -n "[ENCODED_WORD]" | base64 --decode ```

# Jobs 

get jobs: ``` kubectl get jobs ```

get logs of job: ```kubectl logs [POD_NAME] ```

delete job: ``` kubectl delete job [JOB_NAME] ```

# Cron Jobs 

get cron jobs: ``` kubectl get cronjob ```

delete cron job: ``` kubectl delete cronjob [CRON_JOB_NAME] ```

# Services

get services: ``` kubectl get services ```

delete service: ``` kubectl delete service [SERVICE_NAME] ```

# Ingress

get ingresses: ``` kubectl get ingress ```

describe ingress: ``` kubectl describe ingress [INGRESS_NAME] ```

delete ingress: ``` kubectl delete ingress [INGRESS_NAME] ```

# Service accounts

view service accounts: ``` kubectl get serviceaccounts ```

describe service account: ``` kubectl describe serviceaccount [SERVICE_ACCOUNT_NAME] ```

# Taint and tolerance

taint nodes: ```kubectl taint nodes [NODE_NAME] spray=mortein:NoSchedule ```

untaint nodes: ```kubectl taint nodes [NODE_NAME] spray=mortein:NoSchedule- ```

# Monitor and debug

enable metric server on minikube: ``` minikube addons enable metrics-server ```

clone metric server repo for metric server: ``` git clone https://github.com/kubernetes-sigs/metrics-server.git ```

view node cpu% and memory%: ``` kubectl get top node ```

view pod cpu% and memory%: ``` kubectl get top pod ```

# Rollout

view rollout resource : ```kubectl rollout status [RESOURCE_TYPE] [RESOURCE_NAME] ```

view rollout resource history: ```kubectl rollout history [RESOURCE_TYPE] [RESOURCE_NAME] ```

undo a rollout: ```kubectl rollout undo [RESOURCE_TYPE] [RESOURCE_NAME] ```

# Viewing logs

view logs of pod: ``` kubectl logs -f [POD_NAME] ```

view logs of pod specifying a container: ``` kubectl logs -f [POD_NAME] [CONTAINER_NAME] ```

# Docker commands

run a docker container: ``` docker run [IMAGE] ```

view containers running in docker desktop: ``` docker ps ```

view recently exited conatiners in docker desktop:  ``` docker ps -a ```

add command to docker run command example: ``` docker run [IMAGE] sleep 5 ```

view docker logs: ``` docker logs -f [NAME] ```

run image in background: ``` docker run -d [IMAGE] ```

build docker image: ``` docker build -f [IMAGE] ```

run math equation: ``` kubectl run ubuntu expr 3 + 2 ```

# Nodes

label nodes: ``` kubectl label nodes [NODE_NAME] size=[MEDIUM_OR_LARGE] ```

# Other used commands

get all: ``` kubectl get all ```

-o flag example with yaml: ``` kubectl create namespace [NAME] --dry-run -o yaml ``` 

-o flag example with json: ``` kubectl create namespace [NAME] --dry-run -o json ``` 

define security standards in docker: ``` docker run --user=[NUMBER] [IMAGE]```

update image in resource: ```kubectl set image [RESOURCE_TYPE] [RESOURCE_NAME] \ [EXISTING_IMAGE]=[NEW_IMAGE ```]

