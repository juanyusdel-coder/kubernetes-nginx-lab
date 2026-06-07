# Kubernetes NGINX Lab

![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestration-blue)
![NGINX](https://img.shields.io/badge/NGINX-Web_Server-green)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI-orange)

## Project Overview

This project demonstrates the deployment of a containerized NGINX application on Kubernetes using declarative manifests and Infrastructure as Code principles.

The objective is to showcase core Kubernetes concepts such as:

- Namespaces
- Deployments
- Services
- ConfigMaps
- Container orchestration
- Declarative infrastructure
- CI validation using GitHub Actions

This repository is part of my Cloud & DevOps portfolio and demonstrates practical Kubernetes administration and application deployment skills.

---

## Architecture

```text
+--------------------+
| Kubernetes Cluster |
+--------------------+
          |
          ▼
+--------------------+
| Namespace          |
| nginx-lab          |
+--------------------+
          |
          ▼
+--------------------+
| Deployment         |
| nginx-deployment   |
| Replicas: 2        |
+--------------------+
          |
          ▼
+--------------------+
| Pods               |
| NGINX Containers   |
+--------------------+
          |
          ▼
+--------------------+
| Service            |
| ClusterIP          |
+--------------------+
          |
          ▼
+--------------------+
| Internal Access    |
+--------------------+
```

---

## Technologies Used

| Technology | Purpose |
|------------|----------|
| Kubernetes | Container orchestration |
| NGINX | Web server |
| YAML | Kubernetes manifests |
| GitHub Actions | Continuous Integration |
| Linux | Operating system |
| kubectl | Kubernetes CLI |

---

## Repository Structure

```text
kubernetes-nginx-lab/
│
├── .github/
│   └── workflows/
│       └── kubernetes-ci.yml
│
├── manifests/
│   ├── namespace.yaml
│   ├── configmap.yaml
│   ├── deployment.yaml
│   └── service.yaml
│
├── docs/
│   ├── architecture.md
│   ├── deployment.md
│   └── kubernetes-concepts.md
│
├── README.md
└── .gitignore
```

---

## Kubernetes Resources

### Namespace

Provides logical isolation for project resources.

```yaml
kind: Namespace
```

### ConfigMap

Stores application configuration separately from the container image.

```yaml
kind: ConfigMap
```

### Deployment

Manages the desired state of application pods.

```yaml
kind: Deployment
```

Features:

- 2 replicas
- Self-healing
- Rolling updates
- Declarative management

### Service

Exposes application pods within the cluster.

```yaml
kind: Service
```

Type:

```text
ClusterIP
```

---

## Deployment Instructions

### Create Namespace

```bash
kubectl apply -f manifests/namespace.yaml
```

### Create ConfigMap

```bash
kubectl apply -f manifests/configmap.yaml
```

### Deploy Application

```bash
kubectl apply -f manifests/deployment.yaml
```

### Create Service

```bash
kubectl apply -f manifests/service.yaml
```

---

## Verification

Check resources:

```bash
kubectl get all -n nginx-lab
```

Expected output:

```text
Pods Running
Deployment Available
Service Created
```

Verify deployment:

```bash
kubectl get deployments -n nginx-lab
```

Check pods:

```bash
kubectl get pods -n nginx-lab
```

---

## CI Pipeline

GitHub Actions automatically validates Kubernetes manifests on every push and pull request.

Validation includes:

- YAML syntax validation
- Kubernetes resource validation
- Repository integrity checks

Workflow:

```text
.github/workflows/kubernetes-ci.yml
```

---

## Skills Demonstrated

This project demonstrates practical experience with:

- Kubernetes Administration
- Container Orchestration
- Deployments
- Services
- Namespaces
- ConfigMaps
- GitHub Actions
- CI/CD
- Infrastructure as Code
- Linux Operations

---

## Future Enhancements

Planned improvements:

- Ingress Controller
- Horizontal Pod Autoscaler
- Persistent Volumes
- Secrets Management
- Helm Charts
- Monitoring with Prometheus
- Grafana Integration
- Kubernetes Dashboard
- AWS EKS Deployment

---

## Learning Outcomes

Through this project I gained hands-on experience with:

- Kubernetes object management
- Declarative application deployment
- Containerized workloads
- Service discovery
- Configuration management
- CI automation

---

## Author

### Yusdel Concepcion

Infrastructure & Cloud Engineer
