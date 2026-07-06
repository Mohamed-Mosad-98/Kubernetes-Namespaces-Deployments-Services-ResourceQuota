
# Web Application Commands

This document contains all commands used to deploy and manage the Nginx web application in Kubernetes.

---

## 1. Create Namespace

```bash
kubectl create namespace web-app
```

---

## 2. Verify Namespace

```bash
kubectl get namespaces
```

---

## 3. Apply Nginx Deployment

```bash
kubectl apply -f manifests/nginx-deployment.yaml
```

---

## 4. Verify Deployment

```bash
kubectl get deployment -n web-app
```

---

## 5. Verify Pods

```bash
kubectl get pods -n web-app -o wide
```

---

## 6. Create Service

```bash
kubectl apply -f manifests/nginx-service.yaml
```

---

## 7. Verify Service

```bash
kubectl get svc -n web-app
```

---

## 8. Scale Deployment

```bash
kubectl scale deployment nginx-deployment \
--replicas=4 \
-n web-app
```

---

## 9. Verify Scaling

```bash
kubectl get deployment -n web-app
```

```bash
kubectl get pods -n web-app
```

---

## 10. Create ResourceQuota

```bash
kubectl apply -f manifests/quota.yaml
```

---

## 11. Verify ResourceQuota

```bash
kubectl get resourcequota -n web-app
```

---

## 12. Display ResourceQuota Details

```bash
kubectl describe resourcequota web-quota -n web-app
```

---

## 13. Test ResourceQuota

```bash
kubectl scale deployment nginx-deployment \
--replicas=6 \
-n web-app
```

---

## 14. Display All Resources

```bash
kubectl get all -n web-app
```
