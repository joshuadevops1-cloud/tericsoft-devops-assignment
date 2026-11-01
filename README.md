
# Tericsoft DevOps Internship Assignment

## 1. Project Overview

This project demonstrates the end-to-end deployment of a containerized web application using AWS cloud services and Docker.

The application is packaged into a Docker image, stored in Amazon Elastic Container Registry (ECR), and deployed using Amazon Elastic Container Service (ECS) with AWS Fargate.

## 2. Architecture

The deployment uses the following AWS services and tools:

| Component | Purpose |
|---|---|
| Amazon EC2 | Ubuntu environment for building and testing |
| Docker | Containerization of the web application |
| Amazon ECR | Storage for Docker images |
| Amazon ECS | Container orchestration |
| AWS Fargate | Serverless container execution |
| AWS IAM | Secure permissions for AWS services |
| GitHub | Source code version control |

## 3. Application Structure

```text
tericsoft-devops-assignment/
├── Dockerfile
├── .dockerignore
├── index.html
└── README.md
```

## 4. Deployment Workflow

1. Launched an Ubuntu EC2 instance.
2. Connected to the EC2 instance using SSH.
3. Installed and configured Docker.
4. Created a Dockerfile for the web application.
5. Built the Docker image locally.
6. Created an Amazon ECR repository.
7. Authenticated Docker with Amazon ECR using AWS CLI.
8. Tagged and pushed the Docker image to ECR.
9. Created an ECS cluster.
10. Registered an ECS Fargate task definition.
11. Configured the ECS security group to allow HTTP traffic.
12. Created an ECS service using Fargate.
13. Enabled public IP assignment for the task.
14. Verified application accessibility through the public IP.

## 5. Docker Commands

### Build Docker Image

```bash
docker build -t tericsoft-web:v1 .
```

### Run Container Locally

```bash
docker run -d -p 8081:80 tericsoft-web:v1
```

### View Running Containers

```bash
docker ps
```

### Stop a Container

```bash
docker stop <container-id>
```

## 6. Amazon ECR Configuration

**AWS Region:** `ap-southeast-2`

**ECR Repository:** `tericsoft`

**Image Tag:** `v1`

**Image URI:**

```text
272380902654.dkr.ecr.ap-southeast-2.amazonaws.com/tericsoft:v1
```

### Authenticate with ECR

```bash
aws ecr get-login-password --region ap-southeast-2 | docker login --username AWS --password-stdin 272380902654.dkr.ecr.ap-southeast-2.amazonaws.com
```

### Tag the Image

```bash
docker tag tericsoft-web:v1 272380902654.dkr.ecr.ap-southeast-2.amazonaws.com/tericsoft:v1
```

### Push the Image

```bash
docker push 272380902654.dkr.ecr.ap-southeast-2.amazonaws.com/tericsoft:v1
```

## 7. Amazon ECS Configuration

| Setting | Value |
|---|---|
| ECS Cluster | tericsoft-cluster |
| Task Definition | tericsoft-web-task |
| Launch Type | AWS Fargate |
| Operating System | Linux |
| Architecture | x86_64 |
| CPU | 1 vCPU |
| Memory | 2 GB |
| Container Port | 80 |
| Protocol | TCP |
| Security Group | tericsoft-ecs-sg |
| ECS Service | tericsoft-web-service |
| Desired Task Count | 1 |

## 8. Networking and Security

- Configured an ECS security group.
- Allowed inbound HTTP traffic on TCP port 80.
- Enabled public IP assignment for the Fargate task.
- Used IAM roles to provide AWS service permissions.
- Used Amazon ECR authentication through AWS CLI instead of hardcoding credentials.

## 9. Verification

The deployment was tested through the following checks:

- Docker image built successfully.
- Docker container ran successfully on EC2.
- Docker image pushed successfully to Amazon ECR.
- ECS task definition registered successfully.
- ECS service created using AWS Fargate.
- Application accessibility tested using the task's public IP.

## 10. Skills Demonstrated

- Linux administration
- SSH connectivity
- Git and GitHub
- Docker image creation and container management
- AWS CLI
- AWS IAM roles and permissions
- Amazon ECR
- Amazon ECS
- AWS Fargate
- Container networking
- Application deployment and verification

## 11. Project Status

**Deployment:** Completed

**Containerization:** Successful

**Image Registry:** Amazon ECR

**Orchestration:** Amazon ECS

**Compute Platform:** AWS Fargate

**Region:** ap-southeast-2

---

This project was completed as part of the Tericsoft DevOps Internship Assignment.
