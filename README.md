# Helm Chart Demo
This repo showcases how can we set up a helm chart.  
This is just a demo - **NOT FULLY WORKING EXAMPLE**

### Commands to run:
```shell
#!/bin/bash

helm repo add cnpg https://cloudnative-pg.github.io/charts

helm upgrade --install cnpg \
  --namespace cnpg-system \
  --create-namespace \
  cnpg/cloudnative-pg

helm upgrade --install database \
  --namespace lowry \
  --create-namespace \
  cnpg/cluster

helm install lowry .
```

PosgreSQL helm chart:  
https://github.com/cloudnative-pg/charts?tab=readme-ov-file


### To Cleanup:
```shell
helm uninstall cnpg -n cnpg-system
helm uninstall database -n database
helm uninstall lowry
kubectl delete ns cnpg-system
helm repo remove cnpg 
```
