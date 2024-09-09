# MAC0432-Helmfile

```text
# Apply this helmfile to your cluster
helmfile -i apply

# Listen on port 9020 locally, forward to port 9000 of the service
kubectl port-forward svc/sonarqube-dce-dev-sonarqube-dce-sonarqube-dce 9020:900
```
