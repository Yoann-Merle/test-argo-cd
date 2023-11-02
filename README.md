# Install

```bash
# install ArgoCD in k8s
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```


# access ArgoCD UI

## On beta
Apply both ingresses present in `beta folder` after the creation of certificates

## Locally
kubectl port-forward svc/argocd-server 8080:443 -n argocd


# First login with admin user:
```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo
```
One connected, change the password within UI

# Auth and webhook

Both are managed through GithubApp.
Check https://github.com/organizations/elmy-team/settings/installations/43579616
