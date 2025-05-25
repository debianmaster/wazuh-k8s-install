# Provision cert first

```
kubectl apply -f wazuh-cert.yaml -n wazuh
```
# wazuh-k8s-install

```
helm upgrade --install wazuh  wazuh-helm/wazuh -n wazuh --create-namespace --set dashboard.ingress.enabled=true --set dashboard.ingress.ingressClassName=nginx --set dashboard.ingress.tls[0].secretName=ezy-waz-tls --set dashboard.ingress.tls[0].hosts[0]=waz.ezy.dev --set dashboard.ingress.host=waz.ezy.dev --set dashboard.ingress.className=nginx
```
