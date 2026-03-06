# 🚀 Kubernetes Observability with Prometheus & Grafana

![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes\&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus\&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?logo=grafana\&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-0F1689?logo=helm\&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?logo=amazonaws\&logoColor=white)

---

## 📌 Overview

This project demonstrates how to implement **Kubernetes observability** using **Prometheus and Grafana**.

The monitoring stack collects real-time metrics from Kubernetes nodes and pods and visualizes them through powerful dashboards.

This repository is part of a **complete DevOps workflow** including:

* ⚙️ Infrastructure provisioning with Terraform
* ☸️ Kubernetes cluster deployment
* 🔄 GitOps deployment using ArgoCD
* 📊 Monitoring using Prometheus & Grafana

---

## 🏗 Architecture

![Architecture Diagram](./screenshots/architecture.png)

---

## 🧰 Tech Stack

| Tool          | Purpose                    |
| ------------- | -------------------------- |
| ☸️ Kubernetes | Container orchestration    |
| 🔥 Prometheus | Metrics collection         |
| 📊 Grafana    | Monitoring dashboards      |
| 📦 Helm       | Kubernetes package manager |
| 🐳 Docker     | Containerized applications |
| ☁️ AWS EC2    | Cloud infrastructure       |

---

## 🔍 Observability Components

### 🔥 Prometheus

Prometheus is a **time-series database and monitoring system** used to collect metrics from Kubernetes components.

Features:

* 📡 Metrics scraping
* ⏱ Time-series database
* 🧠 PromQL query language
* 🔎 Kubernetes service discovery

Example PromQL query:

```
sum(rate(container_cpu_usage_seconds_total{namespace="default"}[1m])) / sum(machine_cpu_cores) * 100
```

---

### 📊 Grafana

Grafana is used for **visualizing metrics collected by Prometheus**.

Dashboards used in this project:

* 📈 Node Exporter Dashboard
* ☸️ Kubernetes Cluster Dashboard

These dashboards show:

* CPU usage
* Memory usage
* Disk usage
* Network traffic
* Running pods
* Cluster resource utilization

---

## 📷 Screenshots

### Prometheus Metrics Query

![Prometheus](screenshots/prometheus-dashboard.png)

### Grafana Node Exporter Dashboard

![Grafana Node Exporter](screenshots/node-exporter-dashboard.png)

### Kubernetes Cluster Monitoring Dashboard

![Grafana Kubernetes Dashboard](screenshots/kubernetes-dashboard.png)

### Voting Application

![Voting App](screenshots/voting-app.png)

---

## 🧠 Learning Outcomes

Through this project I learned:

* Kubernetes observability principles
* Prometheus metrics scraping
* Writing PromQL queries
* Grafana dashboard creation
* Kubernetes cluster monitoring

---

## 🚀 Future Improvements

* 🔔 Alerting with Alertmanager
* 📜 Log monitoring with Loki
* 🔍 Distributed tracing with Jaeger
* 📊 Application-level metrics

---

## 👨‍💻 Author

**Mohammed Abdul Faizan**
DevOps & Cloud Enthusiast
