# Portainer

Install Portainer:
```
helm upgrade -i portainer portainer/portainer \
  --create-namespace \
  --namespace portainer \
  --set enterpriseEdition.enabled=true \
  --set service.type=LoadBalancer
```

https://10.10.159.85:9443

```
kubectl label ns portainer \
  pod-security.kubernetes.io/enforce=privileged \
  pod-security.kubernetes.io/audit=privileged \
  pod-security.kubernetes.io/warn=privileged \
  --overwrite
```

```
kubectl rollout restart deployment -n portainer
```
