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

## Features

- Server-side rendering / Static generation via Next.js  
- TypeScript support  
- PostCSS / CSS configuration  
- Dockerfile included  
- Kubernetes / YAML manifests for deployment  
- Environment-based configuration  
- Modular folder structure  

---

## Tech Stack

| Layer           | Technology / Tool           |
|----------------|------------------------------|
| Framework       | Next.js (TypeScript)         |
| Styling         | CSS / PostCSS                |
| Containerization| Docker                       |
| Deployment       | Kubernetes / YAML manifests |
| Config & Env     | `next.config.ts`, `.env.*` |

---

## Getting Started

### Prerequisites

Make sure you have the following installed:

- Node.js (v16 or newer preferred)  
- npm / yarn / pnpm  
- Docker (if you plan to containerize)  
- Kubernetes / `kubectl` (optional, for deployment)  

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

### Docker Setup:
### Build Docker image
- docker build -t nextjs-app:latest .

### Run container
- docker run -p 3000:3000 nextjs-app:latest

### Kubernetes / YAML Manifests:
### The repo includes deployment.yaml (and possibly service.yaml) for deploying in a k8s cluster. You can:

- kubectl apply -f deployment.yaml
- kubectl apply -f service.yaml

### Check the logs of the pods:
- kubectl logs podname

### Localtest application:
- curl localhost:3000

### port-forwarding the application to acess  it in the browser:
- kubectl port-forward svc/my-service 5000:3000 --address 0.0.0.0 &
