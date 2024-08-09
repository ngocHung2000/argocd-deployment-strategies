### Add repo to charts
```shell
helm repo add argo https://argoproj.github.io/argo-helm
helm search repo argo
```
### Setup values.yaml cho argocd
```yaml
controller:
  replicas: 1

server:
  service:
    type: NodePort

applicationSet:
  replicas: 1
```
### Deploy
```shell
helm install argocd argo/argo-cd -f argocd.yaml -n argocd
```
### Install Argo Rollouts
```shell
helm install argo-rollouts argo/argo-rollouts -n argocd
wget https://github.com/argoproj/argo-rollouts/releases/download/v1.7.1/kubectl-argo-rollouts-linux-amd64
chmod +x kubectl-argo-rollouts-linux-amd64
sudo mv kubectl-argo-rollouts-linux-amd64 /usr/local/bin/kubectl-argo-rollouts

kubectl argo rollouts version
kubectl argo rollouts dashboard
```