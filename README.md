# Kubernetes Namespaces, Deployments, Services & ResourceQuota

![Kubernetes](https://img.shields.io/badge/Kubernetes-v1.34-blue?logo=kubernetes)
![Platform](https://img.shields.io/badge/Platform-Minikube-orange)
![OS](https://img.shields.io/badge/OS-Ubuntu%2022.04-E95420?logo=ubuntu)

## 📖 Overview

This repository contains Kubernetes Lab 03 demonstrating the deployment and management of applications using Kubernetes resources.

The lab covers:

- Creating and managing namespaces
- Deploying applications using Deployments
- Exposing applications using Services
- Scaling Deployments
- Applying ResourceQuota
- Managing MySQL environment variables
- Verifying Kubernetes resources

---

# 📌 Lab Objectives

- Create Kubernetes Namespaces
- Deploy Nginx Web Application
- Expose applications using NodePort Service
- Scale Deployments
- Apply ResourceQuota
- Deploy MySQL Database
- Configure Environment Variables
- Verify Kubernetes Resources

---

# 🛠 Technologies Used

- Kubernetes
- Minikube
- kubectl
- YAML
- Nginx
- MySQL

---

# 📂 Project Structure

```text
Kubernetes-Namespaces-Deployments-Services-ResourceQuota/
│
├── README.md
│
├── manifests/
│   ├── nginx-deployment.yaml
│   ├── nginx-service.yaml
│   ├── quota.yaml
│   └── mysql-deployment.yaml
│
├── commands/
│   ├── web-app-commands.md
│   └── db-app-commands.md
│
└── screenshots/
```

---

# 🚀 Lab 1 – Web Application

## Create Namespace

```bash
kubectl create namespace web-app
```

## Deploy Nginx

```bash
kubectl apply -f manifests/nginx-deployment.yaml
```

## Create Service

```bash
kubectl apply -f manifests/nginx-service.yaml
```

## Scale Deployment

```bash
kubectl scale deployment nginx-deployment --replicas=4 -n web-app
```

## Apply ResourceQuota

```bash
kubectl apply -f manifests/quota.yaml
```

---

# 🗄 Lab 2 – MySQL Deployment

## Create Namespace

```bash
kubectl create namespace db-app
```

## Deploy MySQL

```bash
kubectl apply -f manifests/mysql-deployment.yaml
```

## Configure Environment Variables

```bash
kubectl set env deployment/mysql-deployment \
MYSQL_ROOT_PASSWORD=root123 \
MYSQL_DATABASE=mydb \
-n db-app
```

---

# 🔍 Verification Commands

```bash
kubectl get namespaces

kubectl get deployments --all-namespaces

kubectl get pods --all-namespaces -o wide

kubectl get services --all-namespaces

kubectl get resourcequota --all-namespaces

kubectl get all -n web-app

kubectl get all -n db-app
```

---

# 📸 Deployment Screenshots

## 1. Create Web Namespace

<img width="1920" height="1080" alt="1-create-web-namespace" src="https://github.com/user-attachments/assets/a9c5b335-0c48-4bd1-97a0-f3b97da549f3" />

---

## 2. Deploy Nginx Application

<img width="1920" height="1080" alt="2-nginx-deployment" src="https://github.com/user-attachments/assets/16615490-462b-4296-8379-1793d39eba97" />

---

## 3. Create NodePort Service

<img width="1920" height="1080" alt="3-nginx-service" src="https://github.com/user-attachments/assets/77817fa4-d6b0-49e8-91e6-8a39eab8cf7f" />

---

## 4. Scale Deployment

<img width="1920" height="1080" alt="4-scale-deployment" src="https://github.com/user-attachments/assets/ed814591-4dfc-4a30-b427-edcee1c5d651" />

---

## 5. Apply ResourceQuota

<img width="1920" height="1080" alt="5-resource-quota" src="https://github.com/user-attachments/assets/af7d8fce-9a57-49a4-92a2-6b9e6f298805" />

---

## 6. Verify ResourceQuota

<img width="1920" height="1080" alt="6-quota-verification" src="https://github.com/user-attachments/assets/0ce3364c-72f1-4581-aa35-51b4fa7d7efd" />


---

## 7. Create Database Namespace

<img width="1920" height="1080" alt="7-create-db-namespace" src="https://github.com/user-attachments/assets/7e60b1b6-23cb-46e6-9102-40919f2c469b" />


---

## 8. Deploy MySQL

<img width="1920" height="1080" alt="8-mysql-deployment" src="https://github.com/user-attachments/assets/c8269ad4-47c4-43f7-95b9-9a4d247610c0" />

---

## 9. Configure Environment Variables

<img width="1920" height="1080" alt="9-set-environment-variables" src="https://github.com/user-attachments/assets/f14c7e69-7189-49b9-b761-44a37de52ecd" />

---

## 10. Verify Rollout Status

<img width="1920" height="1080" alt="10-rollout-status" src="https://github.com/user-attachments/assets/34a20f75-656a-43bf-8221-22a50156fa46" />


---

## 11. Final Verification

<img width="1920" height="1080" alt="11-final-verification" src="https://github.com/user-attachments/assets/1a6c8845-9519-45eb-bf15-4802eb78a246" />

---

# 📚 Key Learnings

- Kubernetes Namespace Isolation
- Deployment Management
- Service Exposure
- Deployment Scaling
- ResourceQuota Management
- Environment Variable Configuration
- Kubernetes Resource Verification
- YAML Manifest Deployment

---

# 👨‍💻 Author

**Mohamed Mosad Fahmy**

- GitHub: https://github.com/Mohamed-Mosad-98
- LinkedIn: https://www.linkedin.com/in/mohamed-mosad-516aa717b/

---

⭐ If you found this repository useful, don't forget to star it.
