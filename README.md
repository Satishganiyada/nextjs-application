# Next.js Application

A modern, production-ready Next.js application scaffolded using `create-next-app`.  

---

## 🔍 Table of Contents

- [About](#about)  
- [Features](#features)  
- [Tech Stack](#tech-stack)  
- [Getting Started](#getting-started)  
- [Configuration](#configuration)  
- [Running Locally](#running-locally)  
- [Building & Deployment](#building--deployment)  
- [Docker Setup](#docker-setup)  
- [Kubernetes / YAML Manifests](#kubernetes--yaml-manifests)  
 

---

## About

This project demonstrates a Next.js application built with TypeScript, ready for production deployment. It includes configuration for containerization, orchestration, and environment-based settings.  

It’s structured to be extended — you can slot in pages, APIs, state management, or UI libraries easily.

---
## Tech Stack

| Layer           | Technology / Tool           |
|----------------|------------------------------|
| Framework       | Next.js (TypeScript)         |
| Styling         | CSS / PostCSS                |
| Containerization| Docker                       |
| Deployment       | Kubernetes / YAML manifests /minikube |

---

## Getting Started

### Prerequisites

Make sure you have the following installed:

- Node.js (v16 or newer preferred)  
- npm
- Docker  
- Kubernetes / minikube (for deployment)  

### Clone the repository

- git clone https://github.com/Satishganiyada/nextjs-application.git
- cd nextjs-application

###  Install dependencies
- npm install

### Running Locally
### Start the development server:
- npm run dev
### To make a production build locally and preview:
- npm run build
- npm start

# Minikube Setup
`sudo apt update` <br>
`sudo apt upgrade -y` <br>
`sudo apt install ca-certificates curl gnupg` <br>

`sudo install -m 0755 -d /etc/apt/keyrings` <br>
`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg` <br>
`sudo chmod a+r /etc/apt/keyrings/docker.gpg` <br>

`echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`<br>

`sudo apt update` <br>
`sudo apt install docker-ce docker-ce-cli containerd.io ` <br>
`docker-compose-plugin -y` <br>
`sudo docker --version` <br>
`sudo usermod -aG docker $USER` <br>

`curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64` <br>
`chmod +x minikube-linux-amd64` <br>

`sudo mv minikube-linux-amd64 /usr/local/bin/minikube` <br>
`minikube version` <br>

`sudo usermod -aG docker $USER` <br>
`newgrp docker` <br>

`minikube start --driver=docker` <br>
`minikube status` <br>

`echo 'alias kubectl="minikube kubectl --"' >> ~/.bashrc` <br>
`source ~/.bashrc` <br>

`kubectl get nodes` <br>

### Kubernetes / YAML Manifests:
The repo includes deployment.yaml, service.yaml for deploying application in a minikube. Run the below commands to create deployment and service:

- kubectl create secret docker-registry ghcr-secret --docker-server=ghcr.io --docker-username=<GHCR_USERNAME> --docker-password=<GHCR_TOKEN> --docker-email=email

- kubectl apply -f deployment.yaml
- kubectl apply -f service.yaml

### Check the logs of the pods:
- kubectl logs <podname>

### port-forwarding the application to acess  it in the browser:
- kubectl port-forward svc/my-service 5000:3000 --address 0.0.0.0 &

### Access the application from browser using ec2 public IP
- http://EC2_PUBLIC_IP:5000
