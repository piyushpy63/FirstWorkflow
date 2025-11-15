🚀 CI/CD Pipeline: Python Flask → Docker → GitHub Actions (Shared Runner) → Minikube Kubernetes

This project demonstrates an end-to-end CI/CD workflow that deploys a Python Flask web application to a Kubernetes cluster running locally on Minikube, triggered automatically using GitHub Actions shared runners.

When you push new code to GitHub:

GitHub Actions builds the Docker image
Pushes it to Docker Hub
Uses your Minikube kubeconfig (base64 encoded)
Updates the Kubernetes Deployment
Performs a rolling update
Exposes the app through a Kubernetes Service

📁 Project Structure
.
├── app/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
│
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
│
└── .github/
    └── workflows/
        └── ci-cd.yml
