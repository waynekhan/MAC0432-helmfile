# MAC0432-Helmfile

Individually apply these releases to your cluster (ref: [https://helmfile.readthedocs.io/en/latest/#cli-reference](https://helmfile.readthedocs.io/en/latest/#cli-reference)):

```text
helmfile -i apply -l=name=sonarqube-dce
```

Access apps running in the cluster (ref: [https://kubernetes.io/docs/tasks/access-application-cluster/port-forward-access-application-cluster/](https://kubernetes.io/docs/tasks/access-application-cluster/port-forward-access-application-cluster/)):

```text
k port-forward svc/sonarqube-dce-postgresql 5432:5432
```

Thereafter, you should see something like:

```text
Forwarding from 127.0.0.1:5432 -> 5432
Forwarding from [::1]:5432 -> 5432
```

In another tab, try `psql`; e.g.,

```text
➜  ~ psql -U sonarUser -d sonarDB -h localhost
Password for user sonarUser:
psql (14.17 (Homebrew), server 11.14)
Type "help" for help.

sonarDB=>
```

Et voilà! Port forwarding will, of course, also work for Prometheus, SonarQube; e.g.,

```text
k port-forward svc/kube-prometheus-stack-prometheus 9090:9090

k port-forward svc/sonarqube-sonarqube 9000:9000
k port-forward svc/sonarqube-dce-sonarqube-dce 9000:9000
```