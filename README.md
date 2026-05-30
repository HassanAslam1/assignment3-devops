# Assignment 3: Kubernetes Orchestration & Full DevOps Pipeline

## Overview
A 3-tier microservice application deployed on Kubernetes using Minikube.

## Architecture
- **Nginx**: Reverse proxy (Port 80 / NodePort 30080)
- **Flask API**: Python REST API (Port 5000)
- **MySQL**: Database (Port 3306)

## Quick Start
```bash
./start.sh
```

## Testing the API
```bash
# Health check
curl http://$(minikube ip):30080/health

# Create item
curl -X POST http://$(minikube ip):30080/api/items \
  -H "Content-Type: application/json" \
  -d '{"name": "Test", "description": "Hello"}'

# List items
curl http://$(minikube ip):30080/api/items
```

## Directory Structure
- `app/` — Application code and Docker files
- `k8s/` — Kubernetes manifests
- `.github/workflows/` — GitHub Actions CI/CD
