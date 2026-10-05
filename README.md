# 🌐 Kubernetes Services (ClusterIP & LoadBalancer)

[![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)](https://kubernetes.io/)
[![Azure LoadBalancer](https://img.shields.io/badge/Azure-Load%20Balancer-0089D6?style=flat-square&logo=microsoft-azure&logoColor=white)](https://azure.microsoft.com/)

Declarative Kubernetes **Service** specifications for internal microservice service discovery (`ClusterIP`) and public internet exposure (`LoadBalancer`) on Azure Cloud Load Balancer.

---

## 📌 Service Types & Architecture

| Service Name | Type | Target Port | Description |
| :--- | :--- | :--- | :--- |
| `nginx-clusterip-service` | `ClusterIP` | `80` | Internal pod-to-pod communication endpoint |
| `nginx-loadbalancer-service` | `LoadBalancer` | `80` | External internet endpoint exposing Azure Public IP |

---

## 📂 Repository Structure

```text
k8s-services/
├── service.yaml        # Combined ClusterIP and LoadBalancer manifest
└── README.md           # Repository Documentation
```

---

## 🚀 Usage Guide

### Prerequisites
- Active Kubernetes cluster connected to cloud provider (e.g., Azure AKS for Public IP allocation).

### Apply Service Manifests

```bash
# Apply ClusterIP & LoadBalancer Services
kubectl apply -f service.yaml

# Verify Service creation and External IP assignment
kubectl get svc -w
```

### Inspect Endpoints & Load Balancer

```bash
# Check registered pod IP endpoints bound to the Service
kubectl get endpoints nginx-loadbalancer-service

# Retrieve details of the LoadBalancer Service
kubectl describe service nginx-loadbalancer-service
```

### Cleanup

```bash
kubectl delete -f service.yaml
```

---

## 👩‍💻 Author

**Priya Jaiswal**  
[GitHub Profile](https://github.com/Pjaisw1103)
