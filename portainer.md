# Portainer

Install Portainer:
```
helm upgrade -i portainer portainer/portainer \
  --create-namespace \
  --namespace portainer \
  --set enterpriseEdition.enabled=true \
  --set service.type=LoadBalancer
```
