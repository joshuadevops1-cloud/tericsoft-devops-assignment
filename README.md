# Tericsoft DevOps Assignment

## Project Overview
This project demonstrates the deployment of a containerized web application using AWS and Docker.

## Architecture
- Amazon EC2 – Ubuntu environment
- Docker – Application containerization
- Amazon ECR – Docker image repository
- Amazon ECS – Container orchestration
- AWS Fargate – Serverless container deployment
- IAM – Secure AWS service access

## Deployment Workflow
1. Launch and configure an Ubuntu EC2 instance.
2. Install Docker and build the application image.
3. Create an Amazon ECR repository.
4. Push the Docker image to ECR.
5. Create an ECS Fargate cluster.
6. Register an ECS task definition.
7. Configure networking and security groups.
8. Deploy the application through an ECS service.
9. Verify application accessibility through its public IP.

## Docker Commands

Build:
```bash
docker build -t tericsoft-web:v1 .# Tericsoft DevOps Assignment

## Project Overview
This project demonstrates the deployment of a containerized web application using AWS and Docker.

## Architecture
- Amazon EC2 – Ubuntu environment
- Docker – Application containerization
- Amazon ECR – Docker image repository
- Amazon ECS – Container orchestration
- AWS Fargate – Serverless container deployment
- IAM – Secure AWS service access

## Deployment Workflow
1. Launch and configure an Ubuntu EC2 instance.
2. Install Docker and build the application image.
3. Create an Amazon ECR repository.
4. Push the Docker image to ECR.
5. Create an ECS Fargate cluster.
6. Register an ECS task definition.
7. Configure networking and security groups.
8. Deploy the application through an ECS service.
9. Verify application accessibility through its public IP.

## Docker Commands

Build:
```bash
docker build -t tericsoft-web:v1 .
