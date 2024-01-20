# nginx-kustomize

Install the necessary stuff:

```
brew install kustomize
brew install tree
```

## Dev

Review the patches before you deploy:

```
kustomize build overlays/dev
```

Deploy the manifests:

```
kustomize build overlays/dev | kubectl apply -f -
kubectl apply -k overlays/dev
```

Check all resources:

```
kubectl get all
```

## Prod

Review the patches before you deploy:

```
kustomize build overlays/prod
```

Deploy the manifests:

```
kustomize build overlays/prod | kubectl apply -f -
kubectl apply -k overlays/prod
```

Check all resources:

```
kubectl get all
```

## Generators

Apply the generator example:

```
kustomize build overlays/generators | k apply  -f -
```

To apply the manifests and prune any old configmaps:

```
kustomize build overlays/generators | kubectl apply --prune -l app=web-service  -f -
```
