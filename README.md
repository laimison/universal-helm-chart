# Universal Helm Chart

A Helm chart to deploy any Kubernetes resource dynamically.

Use cases:

* You want to deploy extra resources on top of another chart eg Prometheus, ArgoCD, etc so one of these charts limits that action

* You don't want to use templates/ directory, for example here you can use multiple Helm sources, but no templates/ directory is supported https://argo-cd.readthedocs.io/en/stable/user-guide/multiple_sources/#helm-value-files-from-external-git-repository

* You don't find required functionality in existing chart

* You're waiting for pull request to be merged in another chart so you want extra resources right now using universal-helm-chart

* You don't want to complicate your pipeline by building extra Helm chart so you use universal-helm-chart

* ... or whatever your reason is

# Usage

```
echo 'resources:
  - apiVersion: v1
    kind: Pod
    metadata:
      name: universal-helm-chart-pod
    spec:
      containers:
        - name: sleep-container
          image: busybox
          args: ["sleep", "infinity"]
  - apiVersion: v1
    kind: Pod
    metadata:
      name: universal-helm-chart-pod-2
    spec:
      containers:
        - name: sleep-container
          image: busybox
          args: ["sleep", "infinity"]
' > /tmp/values.yaml

helm repo add universal-helm-chart https://laimison.github.io/universal-helm-chart

helm install universal-helm-chart universal-helm-chart/universal-helm-chart --version 1.0.0 -n default -f /tmp/values.yaml

kubectl -n default get pods
```

# Helm Chart Link

[https://laimison.github.io/universal-helm-chart](https://laimison.github.io/universal-helm-chart)

# Github Repo Link

[https://github.com/laimison/universal-helm-chart](https://github.com/laimison/universal-helm-chart)