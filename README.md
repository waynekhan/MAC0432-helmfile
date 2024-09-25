# MAC0432-Helmfile

```text
# Apply this helmfile to your cluster
helmfile -i apply -l=name=sonarqube

# PostgreSQL localhost:5432
k port-forward svc/sonarqube-postgresql 5432:5432

# SonarQube localhost:9020
k port-forward svc/sonarqube-sonarqube-dce 9020:9000
```
