# Home k8s on kind


## Kind

```
kind create cluster --config kind-config.yaml
```

## Cilium

```
helm upgrade --install --namespace kube-system \
  --repo https://helm.cilium.io cilium cilium \
  --values cilium-values.yaml
```


## Deploy Flux with the rest

```
export $GITHUB_TOKEN=<token>

flux bootstrap github \
  --owner=$GITHUB_USER \
  --repository=$GITHUB_REPO \
  --branch=main \
  --path=./clusters/kind \
  --personal
```


