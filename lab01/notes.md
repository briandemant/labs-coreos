# Notes

## Config Map

```bash
# install
kubectl create configmap nginx-config --from-literal index.html="`cat intro.html`"
# update
kubectl create configmap nginx-config --from-literal index.html="`cat intro.html`" -o yaml --dry-run| kubectl replace -f -
# display
kubectl describe configmap nginx-config
```

## Deployment / Service

```bash
kubectl create -f intro-app.yaml
```

## Ingress

### Lab Server

```bash
kubectl create -f intro-ingress.yaml
```

### Minikube Changes

```bash
kubectl apply -f <(sed "s/lab..*.xip.io/lab.$(minikube ip).xip.io/" intro-ingress.yaml)
```