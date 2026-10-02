# 📝 Notes App - Complete DevOps Pipeline

![CI Passed](https://img.shields.io/badge/CI-Passed-brightgreen)
![Docker](https://img.shields.io/badge/Docker-dockmee001%2Fnotes--app-blue)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Running-326CE5)
![K3s](https://img.shields.io/badge/k3s-2%20Replicas-orange)

Live DevOps project deployed on K3s Kubernetes cluster.

### ✅ Live Status
- **App:** http://localhost:8080 - Notes App Complete - CI Passed
- **Kubernetes:** 2 pods Running - `kubectl get pods`
- **Service:** LoadBalancer 10.43.46.96:80 -> 30985

### Tech Stack
- Docker: `dockmee001/notes-app-complete-devops:latest`
- CI/CD: GitHub Actions
- Orchestration: K3s Kubernetes
- Web Server: Nginx

### Quick Deploy
```bash
docker save dockmee001/notes-app-complete-devops:latest | sudo k3s ctr images import -
kubectl apply -f k8s/
kubectl get pods
kubectl port-forward svc/notes-app-service 8080:80
