# k8s-home

Home k8s on kind


## Kind

`
kind create cluster --config kind-config.yaml
`

## Cilium

`
helm upgrade --install --namespace kube-system --repo https://helm.cilium.io cilium cilium --values cillium-values.yaml
`


## Bootstrap

```
flux bootstrap github \
  --owner=$GITHUB_OWNER \
  --repository=$GITHUB_REPO \
  --branch=main \
  --path=./clusters/kind \
  --personal
```


