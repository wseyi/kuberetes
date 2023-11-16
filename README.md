# kuberetes

## Deploying a webapp with mongodb

 **Contents**
├─ kubernetes
│  ├─ [README.md](https://https://github.com/wseyi/kuberetes/blob/main/README.md)
│  ├─ mongo-config.yaml
│  ├─ mongo-secret.yaml
│  ├─ mongo.yaml
│  └─ webapp.yaml

**Dependencies**
-[Minikube](https://https://minikube.sigs.k8s.io/docs/start/)
-[Kubectl](https://https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)

Start minikube in a docker container
`$ minikube start --driver docker`

Check the status of minikube
`$ minikube status`
Get the ip address of minikube
`$ minikube ip` 

Create external components 
`$ kubectl apply -f mongo-config.yaml`
`$ kubectl apply -f mongo-secret.yaml`


`$ kubectl apply -f mongo.yaml` 
`$ kubectl apply -f webapp.yaml`

Confirm all components in minikube 
`$ kubectl get all `

Get basic information
`$ kubectl get node`
`$ kubectl get pod`
`$ kubectl get svc`
`$ kubectl get all`

Check if the web app is running
* Enter the ip address of minikube and the port number of webapp

E.g - 192.***.**.*:30100

If you can't access the NodePort service webapp with **`MinikubeIP:NodePort`**, execute the following command:
    
    minikube service webapp-service

Stop minikube
`$ minikube stop`