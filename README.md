# ☸️ OKE GitOps with ArgoCD

This repository demonstrates a **GitOps pipeline** for deploying applications on **Oracle Kubernetes Engine (OKE)** using **ArgoCD**.  
The goal is to show how cloud-native workloads can be continuously deployed and automatically synchronized with the Git source.

---

## 🧱 Architecture

Git Repo (Source of Truth) → ArgoCD → OKE Cluster → Application Pods + Ingress


---

## ⚙️ Prerequisites
- Oracle Cloud Infrastructure tenancy  
- OKE cluster (Kubernetes ≥ 1.27)  
- ArgoCD installed (`kubectl apply -n argocd -f install.yaml`)
- OCI CLI and kubeconfig configured  

---

## 🪜 Deployment Steps
```bash
git clone https://github.com/bulentack/oke-gitops-argocd
cd oke-gitops-argocd

# Apply Application manifest to ArgoCD
kubectl apply -f application.yaml -n argocd

# Monitor deployment
kubectl get pods -n demo
kubectl get ingress -n demo

🌐 Access Application

Once the Ingress is created, access your app via:
http://demo.oke.local or your OCI LoadBalancer public IP.

🧰 Stack

Oracle Cloud Infrastructure • OKE • Kubernetes • ArgoCD • GitOps

