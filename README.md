# DevOps Lab 2 – Containerization & Kubernetes Orchestration

## Overview

This project demonstrates the process of containerizing an application using Docker and deploying it on a Kubernetes cluster using Minikube.

The lab focuses on building Docker images, managing containers, creating Kubernetes resources, and implementing application deployment, scaling, and updating strategies.

## Objectives

- Understand the fundamentals of containerization and Kubernetes orchestration.
- Containerize an application using Docker.
- Build and manage Docker images and containers.
- Use Docker Compose to manage multi-container applications.
- Set up a local Kubernetes cluster using Minikube.
- Deploy applications using Kubernetes Deployments and Services.
- Configure applications using ConfigMaps.
- Scale applications using Kubernetes.
- Perform rolling updates and deployment strategies.
- Verify application deployment through kubectl commands.

## Technologies Used

| Technology | Purpose |
|---|---|
| Docker | Application containerization |
| Docker Compose | Multi-container application management |
| Kubernetes | Container orchestration |
| Minikube | Local Kubernetes cluster |
| kubectl | Kubernetes command-line tool |
| YAML | Kubernetes configuration manifests |
| Git & GitHub | Version control and source code management |

## Project Structure

```text
devops-lab2/
│
├── app/
│   ├── app.py
│   └── requirements.txt
│
├── Dockerfile
├── docker-compose.yml
│
├── kubernetes/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── configmap.yaml
│
├── screenshots/
│
└── README.md
```

*Note: The directory structure can be modified according to the actual application and experiment performed.*

## Application

A sample application is used to demonstrate Docker containerization and Kubernetes deployment.

The application is packaged into a Docker image and executed inside a container.

**Expected Application Output:**

```text
Hello from Docker and Kubernetes!
Application is running successfully.
```

## Implementation

### 1. Docker Containerization

- Create a Dockerfile to define the application environment.
- Build a Docker image using the `docker build` command.
- Run the application inside a Docker container.
- Verify running containers and available images.

**Commands:**

```bash
docker build -t devops-lab2 .
docker images
docker run -d -p 5000:5000 --name lab2-container devops-lab2
docker ps
docker logs lab2-container
```

### 2. Docker Compose

- Create a `docker-compose.yml` file.
- Define application services and their configurations.
- Start and manage containers using Docker Compose.

**Commands:**

```bash
docker compose up -d
docker compose ps
docker compose logs
docker compose down
```

### 3. Minikube Setup

- Start a local Kubernetes cluster using Minikube.
- Verify cluster status.
- Configure kubectl to communicate with the cluster.

**Commands:**

```bash
minikube start
minikube status
kubectl cluster-info
kubectl get nodes
```

### 4. Kubernetes Deployment

Create a Kubernetes Deployment manifest to manage application Pods.

- Define the Docker image.
- Configure the number of replicas.
- Deploy the application using kubectl.

**Commands:**

```bash
kubectl apply -f kubernetes/deployment.yaml
kubectl get deployments
kubectl get pods
```

### 5. Kubernetes Service

Create a Service manifest to expose the application.

- Configure the Service type.
- Define the target port and application port.
- Access the application through Minikube.

**Commands:**

```bash
kubectl apply -f kubernetes/service.yaml
kubectl get services
minikube service <service-name>
```

### 6. ConfigMap Configuration

Use Kubernetes ConfigMaps to manage application configuration separately from the container image.

**Commands:**

```bash
kubectl apply -f kubernetes/configmap.yaml
kubectl get configmaps
kubectl describe configmap <configmap-name>
```

### 7. Application Scaling

Scale the application by increasing or decreasing the number of Pod replicas.

**Commands:**

```bash
kubectl scale deployment <deployment-name> --replicas=3
kubectl get pods
kubectl get deployments
```

### 8. Rolling Updates

Update the application image and perform a rolling update to deploy the new version.

**Commands:**

```bash
kubectl set image deployment/<deployment-name> <container-name>=<new-image>
kubectl rollout status deployment/<deployment-name>
kubectl rollout history deployment/<deployment-name>
```

To roll back a deployment:

```bash
kubectl rollout undo deployment/<deployment-name>
```

## Execution Results

The following results are expected after successfully completing the lab:

- Docker image created successfully.
- Application container running successfully.
- Docker Compose services started successfully.
- Minikube cluster running.
- Kubernetes Deployment created successfully.
- Application Pods running.
- Kubernetes Service exposing the application.
- ConfigMap created and applied.
- Application scaled successfully.
- Rolling update completed successfully.

## Screenshots

Execution evidence is maintained in the `screenshots/` directory.

The screenshots demonstrate Docker image creation, container execution, Docker Compose, Minikube cluster status, Kubernetes Deployment, Service, application scaling, and rolling updates.

## GitHub Repository

**Repository:** [DevOps Lab 2 – Containerization & Kubernetes Orchestration](YOUR_GITHUB_REPOSITORY_LINK)

## Conclusion

This lab demonstrates the fundamentals of containerization and container orchestration using Docker and Kubernetes.

The application is containerized using Docker, managed through Docker Compose, and deployed on a local Kubernetes cluster using Minikube.

It provides practical experience with Docker image management, Kubernetes Deployments, Services, ConfigMaps, application scaling, and rolling updates.

---

**Lab:** 02 – Containerization & Kubernetes Orchestration

**Status:** Implementation in Progress
