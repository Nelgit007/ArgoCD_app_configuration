# GitOps with Argo CD: Project

## About
This is a fully automated CD pipeline for kubernetes configuration changes with argocd.

## Prerequisite:
- Deployment.yaml & Service.yaml files
- Docker registry with image versions for deployment

## Commands/Set-up:

```bash
# install argocd in kubernetes cluster:
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
```bash
# access the argocd UI:
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd
```
```bash
# login with admin user and below token (as in documentation):
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo
```
</br>

#### Read:
* Getting started guide [https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd]


