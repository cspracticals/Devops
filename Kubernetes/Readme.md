# 🚀 Kubernetes Notes – Beginner Friendly (Windows / macOS / Linux)

> Clean, practical notes for learning Kubernetes step-by-step, with **installation guidance**, **manifest basics**, and **common mistakes to avoid**.

---

## 📌 What is Kubernetes?

**Kubernetes (K8s)** is an **open-source container orchestration platform** used to:
- Deploy containerized applications
- Scale applications automatically
- Manage failures and self-heal containers
- Handle networking and storage at scale

👉 In simple words:  
**Docker runs containers, Kubernetes manages containers.**

---

## 🧠 Why Kubernetes is Needed?

Problems without Kubernetes:
- Manual container management
- No auto-scaling
- No self-healing
- No built-in load balancing

Kubernetes solves this by:
- Restarting failed containers
- Scaling pods up/down
- Distributing traffic
- Managing configuration centrally

---

## 🏗️ Kubernetes Architecture (High Level)

Kubernetes has **two main parts**:

### 🔹 Control Plane (Master Node)
Responsible for managing the cluster.

- **API Server** – Entry point for all commands (`kubectl`)
- **Scheduler** – Decides where pods should run
- **Controller Manager** – Maintains desired state
- **etcd** – Key-value store for cluster state

---

### 🔹 Worker Node
Runs application workloads.

- **Kubelet** – Talks to control plane, runs pods
- **Kube-proxy** – Handles networking & services
- **Pods** – Smallest deployable unit

---

## 📦 What is a Pod?

- A **Pod** is the **smallest unit in Kubernetes**
- It can contain **one or more containers**
- Containers in a pod:
  - Share network
  - Share storage
  - Run together

---

## 📄 Pod Manifest File (YAML)

A **manifest file** describes the desired state of a Kubernetes object.

### ✅ Example: nginx Pod manifest

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  labels:
    app: nginx
    tier: dev
spec:
  containers:
    - name: nginx-container
      image: nginx
```
###🔍 Explanation

apiVersion → Kubernetes API version

kind → Type of object (Pod)

metadata → Name, labels

spec → Desired configuration

containers → What runs inside the pod

### 💻 What to Install (OS-wise)
##🪟 Windows (Recommended Setup)

Docker Desktop

WSL 2 (Ubuntu)

kubectl

Minikube or kind (choose one)

👉 Run Kubernetes tools inside WSL, not PowerShell.

##🍎 macOS

Docker Desktop

kubectl

Minikube or kind

##🐧 Linux

Docker / containerd

kubectl

Minikube / kind / kubeadm

###▶️ Deploy the Pod
```
kubectl apply -f nginx-pod.yaml
```

Check status:
```
kubectl get pods
```
###🛠️ kubectl – Kubernetes CLI

kubectl is the command-line tool to interact with Kubernetes.

Common commands:
```
kubectl get nodes
kubectl get pods
kubectl describe pod <pod-name>
kubectl logs <pod-name>
kubectl delete pod <pod-name>
```


#⚠️ kubectl does NOT create clusters.
It only controls existing clusters.

###🧰 Ways to Create a Kubernetes Cluster
##🟢 1. Minikube (Best for Beginners)

Single-node cluster

Easy to start

Good for learning

minikube start

##🔵 2. kind (Kubernetes in Docker)

Runs Kubernetes inside Docker containers

Fast and lightweight

Great for CI/CD and local practice

kind create cluster

##🔴 3. kubeadm (Production Style)

Used on Linux servers

Real multi-node clusters

Not recommended for beginners on Windows/macOS

##☁️ 4. Cloud Kubernetes

AWS EKS

Azure AKS

Google GKE

Used in real production environments.
