# Kubernetes Observability with Prometheus & Grafana

## Overview

This project demonstrates how to implement **observability in a Kubernetes cluster** using **Prometheus and Grafana**.

The monitoring stack collects real-time metrics from Kubernetes nodes and pods, and visualizes them using Grafana dashboards.

This repository is part of a **complete DevOps workflow** that includes:

* Infrastructure provisioning using Terraform
* Kubernetes cluster deployment
* GitOps deployment using ArgoCD
* Monitoring using Prometheus and Grafana

---

## Architecture

```
Users
  │
  ▼
Voting Application (Kubernetes)
  │
  ▼
Prometheus (Metrics Collection)
  │
  ▼
Grafana (Visualization Dashboards)
```

---

## Tech Stack

| Tool       | Purpose                    |
| ---------- | -------------------------- |
| Kubernetes | Container orchestration    |
| Prometheus | Metrics collection         |
| Grafana    | Monitoring dashboards      |
| Helm       | Kubernetes package manager |
| Docker     | Containerized applications |
| AWS EC2    | Cloud infrastructure       |

---

## Observability Components

### Prometheus

Prometheus is a **time-series database and monitoring system** used to collect metrics from Kubernetes components.

Features:

* Metrics scraping
* Time-series database
* PromQL query language
* Kubernetes service discovery

Example PromQL Query:

```
sum(rate(container_cpu_usage_seconds_total{namespace="default"}[1m])) / sum(machine_cpu_cores) * 100
```

---

### Grafana

Grafana is used for **visualizing metrics collected by Prometheus**.

Dashboards created in this project:

1. **Node Exporter Dashboard**
2. **Kubernetes Cluster Dashboard**

These dashboards display:

* CPU usage
* Memory usage
* Disk usage
* Network traffic
* Running pods
* Cluster resource utilization

---

## Grafana Dashboards

### Node Exporter Dashboard

Displays infrastructure metrics such as:

* Node CPU usage
* Memory usage
* Disk usage
* Network statistics
* System uptime

---

### Kubernetes Cluster Dashboard

Provides an overview of the Kubernetes cluster:

* Number of running pods
* Number of nodes
* Cluster CPU utilization
* Cluster memory usage
* Resource counts

---

## Screenshots

### Prometheus Metrics Query

![Prometheus Dashboard](screenshots/prometheus-dashboard.png)

---

### Grafana Node Exporter Dashboard

![Node Exporter Dashboard](screenshots/node-exporter-dashboard.png)

---

### Grafana Kubernetes Cluster Dashboard

![Kubernetes Dashboard](screenshots/kubernetes-dashboard.png)

---

### Voting Application

![Voting App](screenshots/voting-app.png)

---

## Installation Steps

### 1 Install Helm

```
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
```

---

### 2 Create Monitoring Namespace

```
kubectl create namespace monitoring
```

---

### 3 Add Helm Repository

```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
```

---

### 4 Install Prometheus & Grafana

```
helm install kind-prometheus prometheus-community/kube-prometheus-stack \
--namespace monitoring
```

---

### 5 Access Prometheus

```
kubectl port-forward svc/kind-prometheus-kube-prome-prometheus -n monitoring 9090:9090
```

Open:

```
http://localhost:9090
```

---

### 6 Access Grafana

```
kubectl port-forward svc/kind-prometheus-grafana -n monitoring 3000:80
```

Open:

```
http://localhost:3000
```

Default credentials:

```
username: admin
password: prom-operator
```

---

## Learning Outcomes

Through this project, I learned:

* Kubernetes observability principles
* Prometheus metrics scraping
* Writing PromQL queries
* Grafana dashboard creation
* Kubernetes cluster monitoring

---

## Future Improvements

* Add alerting using Alertmanager
* Integrate log monitoring with Loki
* Implement distributed tracing with Jaeger
* Add application-level metrics

---

## Author

Faizan

DevOps & Cloud Enthusiast
