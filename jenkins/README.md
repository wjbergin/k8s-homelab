

## Running Jekins in K8s using Kind

```
kind create cluster --name jenkins
docker build -t jenkins:0.0.1 .
kind load docker-image jenkins:0.0.1 --name jenkins

k create ns jenkins
k config set-context --current --namespace=jenkins
k apply -f jenkins.rbac.yaml
k apply -f jenkins.pvc.yaml -f jenkins.pv.yaml
k apply -f jenkins.service.yaml -f jenkins.deployment.yaml

k port-forward services/jenkins 8080:ui
```
