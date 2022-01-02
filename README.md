g # k8s-ckad-learning commands

# Pods

``` kubectl create -f pods/pod-defenition.yml ```

view pods: ``` kubectl get pods ```

extect pod into file: ``` kubectl get pod <pod-name> -o yaml > pod-definition.yaml ```

edit pod: ``` kubectl edit pod <pod-name> ```

delete pod: ``` kubectl delete pod my-pod ```

# ReplicaControllers & ReplicaSets

replica controller: ``` kubectl create -f ReplicationController/rc-defenition.yml ```

replica set: ``` kubectl create -f replicaset/replicaset-defenition.yml ```

list replication controllers: ``` kubectl get replicationcontroller ```

list replica sets: ``` kubectl get replicaset ```

updated replicas command to replace replica set : ``` kubectl replace -f replicaset-defenition.yml  ```

scale replicas in replicaset with file : ``` kubectl scale --replicas=7 replicaset-defenition.yml ```

scale replicas in replicaset with replicaset namew : ``` kubectl scale --replicas=7 replicaset myapp-replicaset ```

delete replica set: ``` kubectl delete replicaset myapp-replicaset ```

delete replication controller: ``` kubectl delete replicationcontroller myapp-rc ```

# Deployments

``` kubectl create -f deployment/deployment-defenition.yml ```

get deployments: ``` kubectl get deployments ```

delete deployment: ``` kubectl delete deployment my-deployment ```

create deployment: ``` kubectl create deployment blue --image=nginx --replicas=3 ```

# Namespaces

``` kubectl create -f namespace/namespace-dev.yml ```

delete namespace: ``` kubectl delete namespace test ```

create namespace: ``` kubectl create namespace dev ```

get in namspace pod example: ``` kubctl get pods --namespace dev ```

view pods in all namespaces example: ``` kubectl get pods --all-namespaces ```

chnage current context for namespace view: ``` kubectl config set-context $(kubectl config current-context) --namespace dev ```

# Configmaps

``` kubectl create -f config-maps/config-map.yml ```

view config maps: ``` kubectl get configmap ```

descibe config maps: ``` kubectl describe configmap ```

delete config map: ``` kubectl delete configmap config-map ```

# Secrets

``` kubectl create -f secrets/secret-data.yml ```

view secrets: ``` kubectl get secrets ```

describe secrets: ``` kubectl describe secrets ```

describe a secret: ``` kubectl describe secret dashboard-sa-token-m7s2w ```

view secret in yaml format: ``` kubectl get secret app-secret -o yaml ```

creat secret without file: ``` kubectl create secret generic db-secret --from-literal=DB_Host=sql01 --from-literal=DB_User=root --from-literal=DB_Password=password123 ```

# Service accounts

create service account: ``` kubectl create serviceccount dashboard-sa ```

view service accounts: ``` kubectl get serviceaccounts ```

describe service account: ``` kubectl describe serviceaccount dashboard-sa ```

# Taint and tolerance

taint nodes: ```kubectl taint nodes node01 spray=mortein:NoSchedule ```

untaint nodes: ```kubectl taint nodes node01 spray=mortein:NoSchedule- ```

# Docker commands

run a docker container: ``` docker run ubuntu ```

view containers running in docker desktop: ``` docker ps ```

view recently exited conatiners in docker desktop:  ``` docker ps -a ```

add command to docker run command example: ``` docker run ubuntu sleep 5 ```

build docker image: ``` docker build -f [NAME] ```

# Nodes

label nodes: ``` kubectl label nodes node-1 size=large ```

# Other used commands

get all: ``` kubectl get all ```

-o flag example with yaml: ``` kubectl create namespace test-123 --dry-run -o yaml ``` 

-o flag example with json: ``` kubectl create namespace test-123 --dry-run -o json ``` 

turn words into hashed unreadbale code: ``` echo -n "password" | base64 ```

decode hashed unreadble codes to be readable: ``` echo -n "cGFzc3dvcmQ=" | base64 --decode ```

define security standards in docker: ``` docker run --user=1001 ubuntu sleep 1000 ```

