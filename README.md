# Simple DevOps Project

A simple DevOps project demonstrating Flask API deployment to Kubernetes.

## Project Structure
```
the-devops-project/
├── app/
│   ├── app.py          # Simple Flask API
│   └── requirements.txt # Python dependencies
├── k8s/
│   ├── namespace.yaml   # Kubernetes namespace
│   ├── deployment.yaml  # App deployment + service
│   └── service.yaml     # LoadBalancer service
├── scripts/
│   └── create-cluster.sh # EKS cluster creation
├── terraform/
│   └── jenkins/         # Jenkins server setup
├── Dockerfile           # Docker container config
└── README.md

```

## Quick Start

### 1. Create EKS Cluster
```bash
./scripts/create-cluster.sh
```

### 2. Build and Push Docker Image
```bash
docker build -t atuljkamble/the-docker-project:latest .
docker push atuljkamble/the-docker-project:latest
```

### 3. Deploy to Kubernetes
```bash
kubectl apply -f k8s/
```

### 4. Access the App
```bash
kubectl get services -n flask-app
# Visit the LoadBalancer external IP
```

## API Endpoints
- `GET /` - Main API info
- `GET /health` - Health check

## Components
- **Flask API**: Simple Python web service
- **Docker**: Containerized application
- **Kubernetes**: Orchestration with EKS
- **LoadBalancer**: External access via AWS NLB