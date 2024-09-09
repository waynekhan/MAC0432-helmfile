# MAC0432-Helmfile

```text
# Apply this helmfile to your cluster
helmfile -i apply -l=name=sonarqube

# Listen on port 9020 locally, forward to port 9000 of the service
k port-forward svc/sonarqube-sonarqube-dce 9020:9000
```
