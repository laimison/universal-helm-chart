# Universal Helm Chart

A Helm chart to deploy any Kubernetes resource dynamically.

There are multiple use cases where one of them is to deploy extra resources on top of another chart eg Prometheus, ArgoCD, etc.

So you can use universal-helm-chart to extend any other chart using just values.yaml file (no need to use templates/ directory) at https://argo-cd.readthedocs.io/en/stable/user-guide/multiple_sources/#helm-value-files-from-external-git-repository . Might be handy if you don't find required functionality right now in target chart, you are waiting for PR to be merged into that chart, you don't want to complicate your pipeline with extra chart building or whatever your reason is.
