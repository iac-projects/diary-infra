# Diary Infrastructure
[![Project Diary](https://img.shields.io/badge/project-diary-blue?style=flat-square&logo=git)](https://github.com/users/rasouza/projects/2)
[![Build status](https://img.shields.io/buildkite/a8cf2d43ca14c00c118b574c073f6e0f4e799af56f82a6f836/master?label=deploy&logo=kubernetes&logoColor=white&style=flat-square)](https://buildkite.com/rasouza/diary-deploy)

This repository holds all k8s YAML necessary to run [Diary](https://github.com/users/rasouza/projects/2) microservices

## Features
- Istio 1.4.3
- Argo CD 1.4.2
- EFK (Elasticsearch, Fluentd and Kibana)
- [PostgreSQL 11.7](postgres/README.md)

## URLs
- Grafana - [http://grafana.local](http://grafana.local)
- Kiali - [http://kiali.local](http://kiali.local)
- Prometheus - [http://prometheus.local](http://prometheus.local)
- Jaeger - [http://jaeger.local](http://jaeger.local)
- Argo CD - [https://argocd.local](https://argocd.local)
- Logs - [https://logs.local](https://logs.local)


## How to install
It requires a k8s cluster with `LoadBalancer` enabled. See [Getting Started](https://kubernetes.io/docs/setup/) section on Kubernetes documentation for more info.

After you have a Kubernetes cluster ready:
```
git clone git@github.com:rasouza/diary-infra.git
diary-infra/install.sh
```

---

## Credentials

### Kiali
- Username: `admin`
- Password: `admin`

### Argo CD
The initial password is autogenerated to be the pod name of the Argo CD API server. This can be retrieved with the command:

```
kubectl get pods -n argocd -l app.kubernetes.io/name=argocd-server -o name | cut -d'/' -f 2
``` 

Using the username admin and the password from above, login to [Argo CD](https://argocd.local)

---

## Troubleshooting
- Bash installer framework: https://github.com/projectivetech/bash-installer-framework