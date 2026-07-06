# MySQL Deployment Commands

This document contains all commands used to deploy and manage the MySQL application in Kubernetes.

---

## 1. Create Namespace

```bash
kubectl create namespace db-app
```

---

## 2. Verify Namespace

```bash
kubectl get namespaces
```

---

## 3. Create MySQL Deployment

```bash
kubectl create deployment mysql-deployment \
--image=mysql:latest \
-n db-app
```

---

## 4. Verify Deployment

```bash
kubectl get deployment -n db-app
```

---

## 5. Verify Pods

```bash
kubectl get pods -n db-app
```

---

## 6. Configure Environment Variables

```bash
kubectl set env deployment/mysql-deployment \
MYSQL_ROOT_PASSWORD=root123 \
MYSQL_DATABASE=mydb \
-n db-app
```

---

## 7. Verify Rollout Status

```bash
kubectl rollout status deployment/mysql-deployment \
-n db-app
```

---

## 8. Restart Deployment

```bash
kubectl rollout restart deployment/mysql-deployment \
-n db-app
```

---

## 9. Verify Deployment

```bash
kubectl get deployment -n db-app
```

---

## 10. Verify Pods

```bash
kubectl get pods -n db-app
```

---

## 11. Display Deployment Details

```bash
kubectl describe deployment mysql-deployment \
-n db-app
```

---

## 12. Display All Resources

```bash
kubectl get all -n db-app
```
