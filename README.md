# Cloud Resume Project (DevOps + AWS + CI/CD + Containers)

A production-style cloud deployment project demonstrating multiple DevOps strategies:
- EC2 + Nginx + HTTPS deployment
- CI/CD automation with GitHub Actions (self-hosted runner)
- Containerization with Docker
- AWS ECR + ECS Fargate deployment (on-demand demo)

## Architecture

This project demonstrates three deployment patterns:

### 1. Traditional Deployment (Live)
GitHub → EC2 → Nginx → HTTPS (Certbot)

### 2. CI/CD Automation
GitHub Actions → Self-hosted Runner (EC2) → rsync → Nginx

### 3. Containerized Deployment (Demo)
Docker → Amazon ECR → ECS Fargate → Public IP

## Key Features

- Deployed a secure web application on AWS EC2 using Nginx and SSL (Certbot)
- Built a CI/CD pipeline using GitHub Actions with a self-hosted runner
- Automated deployments using rsync and Git-based workflows
- Containerized the application using Docker
- Pushed container images to Amazon ECR
- Deployed containers using AWS ECS Fargate (serverless containers)
- Implemented security best practices (SSH hardening, key-based access)
- Designed cost-efficient deployment strategy (on-demand ECS demo)

## Tech Stack

- AWS EC2
- AWS ECS (Fargate)
- AWS ECR
- Nginx
- GitHub Actions
- Docker
- Linux (Ubuntu)
- SSH / Networking / Security Groups

## CI/CD Pipeline

1. Code pushed to GitHub
2. GitHub Actions triggers deployment
3. Self-hosted runner executes on EC2
4. Repository updates pulled
5. Files synced to /var/www/html via rsync
6. Nginx reloads automatically

For container deployment:
- Docker image built locally
- Pushed to Amazon ECR
- ECS service created for demo deployment

## Security

- Disabled password-based SSH authentication
- Disabled root login
- Restricted SSH access to a single IP
- Used key-based authentication
- Scoped sudo permissions for deployment automation

## Screenshots

- EC2 Deployment (Nginx + HTTPS)
- GitHub Actions Pipeline
- ECR Repository with Image
- ECS Running Task (Fargate)
- Application running via public IP

## Lessons Learned

- Difference between push-based and pull-based deployments
- Trade-offs between EC2 and Fargate (cost vs scalability)
- Importance of security hardening (SSH, IAM, network access)
- Managing CI/CD pipelines across multiple deployment strategies
- Handling real-world debugging (SSH, permissions, networking)

## Future Improvements

- Automate Docker build and push using GitHub Actions
- Deploy ECS via CI/CD pipeline (OIDC + IAM roles)
- Add monitoring with CloudWatch
- Implement Infrastructure as Code using Terraform
