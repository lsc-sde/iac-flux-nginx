# iac-flux-nginx
NGINX Flux Configuration

## Developer Guide
To test the changes, ensure that you are on your developer machine and that the context is set correctly to your local instance please amend the following script to use the target branch:

```bash
kubectl config use-context docker-desktop
kubectl create namespace nginx
flux create source git nginx --url="https://github.com/lsc-sde/iac-flux-nginx" --branch=main --namespace=nginx
flux create kustomization nginx-sources --source="GitRepository/nginx" --namespace=nginx --path="./sources" --interval=1m --prune=true --health-check-timeout=10m --wait=false
```

This should in turn deploy all of the resulting resources on your local cluster.