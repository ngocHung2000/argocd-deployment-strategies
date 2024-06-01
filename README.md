What is Argo-rollouts

Why argo-rollout
    - The native kubernetes deployment object and argo-rollouts
    - limitations of deployment object
    - features of argo-rollouts
Use cases of argo-rollouts:
    - Blue-green deployment strategy: active svc, preview svc
    - Canary deployment strategy

Deployment strategies:
    - The native kubernetes deployment object
        - Rolling-update
        - Recreate
    - Argo-rollouts
        - Rolling-update
        - Blue-Green
        - Canary
Components of argo-rollouts:
    - controller
    - resource
    - ingress/service
    - AnalysisTemplate
    - MetricProviders

# Installation
kubectl create namespace argo-rollouts
kubectl apply -n argo-rollouts -f https://github.com/argoproj/argo-rollouts/releases/latest/download/install.yaml

# Install command tools
wget https://github.com/argoproj/argo-rollouts/releases/download/v1.6.6/kubectl-argo-rollouts-linux-amd64
mv kubectl-argo-rollouts-linux-amd64 /usr/local/bin/kubectl-argo-rollouts

kubectl argo rollouts dashboard