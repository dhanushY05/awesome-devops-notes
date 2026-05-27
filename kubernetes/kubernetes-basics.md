# ☸️ Kubernetes Basics

## 📌 What is Kubernetes?

Kubernetes (K8s) is a container orchestration platform used to:
- automate deployment
- scale applications
- manage containers

It is mainly used with Docker containers.

---

## 🚀 Why Kubernetes?

Kubernetes helps to:

- manage multiple containers
- auto-scale applications
- recover failed containers
- load balance traffic
- automate deployments

---

## 🏗 Kubernetes Architecture

```txt
Master Node
 ├── API Server
 ├── Scheduler
 ├── Controller Manager
 └── ETCD

Worker Node
 ├── Kubelet
 ├── Kube Proxy
 └── Pods
```

---

## 📦 Important Components

### Pod
Smallest unit in Kubernetes.

Example:
```txt
1 Pod = 1 or more containers
```

### Node
A machine that runs pods.

### Cluster
Group of nodes.

### Deployment
Used to manage pods and replicas.

### Service
Exposes application to users.

---

## 🔥 Basic Kubernetes Commands

### Check cluster info

```bash
kubectl cluster-info
```

### Get nodes

```bash
kubectl get nodes
```

### Get pods

```bash
kubectl get pods
```

### Create deployment

```bash
kubectl create deployment nginx --image=nginx
```

### Check deployments

```bash
kubectl get deployments
```

### Expose deployment

```bash
kubectl expose deployment nginx --port=80 --type=NodePort
```

---

## 📄 Simple Deployment YAML

```yaml
apiVersion: apps/v1
kind: Deployment

metadata:
  name: nginx-deployment

spec:
  replicas: 2

  selector:
    matchLabels:
      app: nginx

  template:
    metadata:
      labels:
        app: nginx

    spec:
      containers:
      - name: nginx
        image: nginx
        ports:
        - containerPort: 80
```

Apply YAML:

```bash
kubectl apply -f deployment.yaml
```

---

## ⚙️ Real DevOps Workflow

```txt
Developer → Docker → Kubernetes → Deployment
```

---

## 🎯 Advantages of Kubernetes

- High availability
- Auto healing
- Auto scaling
- Easy deployment
- Container management

---

## 📚 Summary

Kubernetes is a powerful container orchestration tool widely used in DevOps and cloud environments.